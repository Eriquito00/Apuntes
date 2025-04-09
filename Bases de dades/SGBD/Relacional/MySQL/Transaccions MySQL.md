# Transaccions MySQL
Una transaccio es un conjunt de sentencies DML que s'executen de forma atomica, es a dir, per poder finalitzar una transaccio s'han de executar totes les sentencies de la transaccio de forma satisfactoria per que es guardi, si falla no es guardara res i si s'executa tot de forma satisfactoria es guardara tot.

```MYSQL
BEGIN;

SELECT * FROM empleats;

UPDATE empleats
	SET salari = salari + 100;
    
ROLLBACK;
```

Per finalitzar la transaccio haurem de fer un COMMIT o un ROLLBACK.

Tal i com diuen les paraules el COMMIT es per guardar y finalitzar la transaccio amb tot el que hem cambiat a las sentencies executades entre BEGIN i COMMIT.

ROLLBACK per altre banda no ens guarda cap cosa que hagim fet entre el BEGIN i el ROLLBACK, ens torna a l'estat de la base de dades tal i com estaba abans del BEGIN, LES CONSULTES DDL EXECUTADES NO RETORNARAN.
## Bloqueig de taules
Per bloquejar una taula o varies podem fer-ho si hem de fer un cambi tan gran que seria perillos per la consistencia no bloquejarla. Podem bloquejar perque no es pugui escriure noves dades o per llegir les dades.

```MYSQL
LOCK TABLE (nom taula) WRITE | READ;
```

A MySQL quan desbloquejem una taula les desbloquejem totes, es a dir que si tenim varies taules bloquejades a l'hora de desbloquejar seran totes.

```MYSQL
UNLOCK TABLES;
```

Si estem fent una transaccio i estem utilitzant una fila fent un update, si altre persona utilitza aquesta mateixa fila aquesta sentencia es quedara "running" fins que la nostre transaccio finalitzi i si no ha pasat el temps maxim d'espera i despres s'executara.
## Nivells aillament
### Nivell 0
En cas de voler actualitzar i llegir a la vegada d'una mateixa taula, en cas de voler editar un nom a un empleat i despres voler consultar els usuaris amb el nivell d'aillament 0 veurem encara que el cambi no estigui fer amb COMMIT o ROLLBACK podem veure la dada ja editada.

```MYSQL
# Sesio 1
BEGIN;

SET SESSION TRANSACTION ISOLATION
	LEVEL READ UNCOMMITTED;

UPDATE empleats
	SET nom = "Juan"
WHERE empleat_id = 1; //NOM ORIGINAL MARTA

<-- EXECUTA SESIO 2

COMMIT;
```

```MYSQL
# Sesio 2
SELECT *
	FROM empleats;

//VEURA EL NOM JUAN ENCARA QUE NO HAGI FET COMMIT ENCARA
```

### Nivell 1
En cas de voler actualitzar i llegir a la vegada d'una mateixa taula, en cas de voler editar un nom a un empleat i despres voler consultar els usuaris amb el nivell d'aillament 1 veurem el cambi quan s'hagi fet el COMMIT.

```MYSQL
# Sesio 1
BEGIN;

SET SESSION TRANSACTION ISOLATION
	LEVEL READ COMMITTED;

UPDATE empleats
	SET nom = "Juan"
WHERE empleat_id = 1; //NOM ORIGINAL MARTA

<-- EXECUTA SESIO 2

COMMIT;

```

```MYSQL
# Sesio 2
SELECT *
	FROM empleats;

//VEURA MARTA JA QUE ENCARA NO ESTA FET EL COMMIT
```
### Nivell 2
Aquest nivell 2 nomes pasara quan usa sessio fa un insert mentres estas fent una transaccio i en aquesta transaccio afectes a aquesta a aquesta fila nova inserida. Si no es fa un update no pasara res, simplement quan acabi la transaccio ara si que hi sortira aquest nou insert.

```MYSQL
# Sesio 1
BEGIN;

SET SESSION TRANSACTION ISOLATION
	LEVEL REPEATABLE READ;

<-- EXECUTA SESIO 2

SELECT * 
	FROM empleats; //NO SORTIRA JUAN

UPDATE empleats
	SET nom = "Joaquin"
WHERE empleat_id = 2; //NOM ORIGINAL JUAN PERO AL SELECT NO SORTIRA

SELECT * 
	FROM empleats; //SI SORTIRA JUAN PERO ARA COM A JOAQUIN

COMMIT;
```

```MYSQL
# Sesio 2
BEGIN;

INSERT INTO empleats (nom, edat)
	VALUES("Juan", 30);

COMMIT;
```

### Nivell 3
En cas de voler actualitzar i llegir a la vegada d'una mateixa taula, en cas de voler editar un nom a un empleat i despres voler consultar els usuaris amb el nivell d'aillament SERIALIZABLE, no es podra fer la lectura fins que no acabi la transaccio amb COMMIT o ROLLBACK.

```MYSQL
# Sesio 1
BEGIN;

SET SESSION TRANSACTION ISOLATION
	LEVEL SERIALIZABLE READ;

SELECT *
	FROM empleats;

<-- EXECUTA SESIO 2 //NO SE EJECUTARA HASTA QUE ACABE ESTA TRANSACCION

SELECT *
	FROM empleats;

COMMIT;
```

```MYSQL
# Sesio 2
BEGIN;

INSERT INTO empleats (nom, edat)
VALUES ("Juan", 30);

COMMIT;
```