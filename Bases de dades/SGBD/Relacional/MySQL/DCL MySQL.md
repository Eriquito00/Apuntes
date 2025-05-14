# DCL MySQL
## Functions i Procedures
S'utilitza per a que el propi gestor de base de dades faci certs calculs amb les dades per no haber de enviar les dades a un programari per fer els calculs.

Hi han dos tipus, procediments i funcions, els procediments no retornen cap valor i les funcions retornen valors de diferents tipus. Els procediments tenen la seguent sintaxi:

```MYSQL
DELIMITER //
CREATE PROCEDURE (nom funcio) ((argument1), (argument2))
BEGIN
	Declaracio de variables
	Declaracio de cursors
	Declaracio de handlers
	Instruccions acabades amb ";"
END
//
DELIMITER;
```

I la funcio es de la seguent forma:

```MYSQL
DELIMITER //
CREATE FUNCTION (nom funcio) ((argument1), (argument2)) RETURNS (tipus de valor)
BEGIN
	Declaracio de variables
	Declaracio de cursors
	Declaracio de handlers
	Instruccions acabades amb ";"
	RETURN (valor que retorna);
END
//
DELIMITER;
```

Per trucar un procediment podem fer-ho de la seguent forma:

```MYSQL
CALL (nom procediment);
```
### Declaracio de variables
Per crear variables farem un DECLARE i sempre y quan siguin del mateix tipus i valor podem definirles a la mateixa linea si no li donarem un nom i un tipus.

```MYSQL
DECLARE (variable1), (variable2)... (tipus)
```
### Assignacio de valors
Per modificar una variable podem assignarli un valor com al seguent exemple:

```MYSQL
SET (variable) = (valor);
```

Pero tambe podem assignarli el valor que ens retorna una consulta com al seguent exemple.

```MYSQL
SET (variable) = (sentencia dml);
```

### Condicionals
Com a condicionals tenim els seguents, si la primera condicio del IF es compleix executara les sentencies i si no comprovara si compleix la condicio de ELSIF i si no compleix tampoc executara les que hi han a ELSE i finalitzara.

```MYSQL
IF (condicio) THEN
	(instruccions)
ELSIF (condicio) THEN
	(instruccions)
ELSE
	(instruccions)
END IF;
```

El CASE son varies condicions que si es compleixen s'executen les instruccions de dins de cada cas, seria com un SWITCH.

```MYSQL
CASE
	WHEN (condicio) THEN (instruccio)
	WHEN (condicio) THEN (instruccio)
END CASE;
```

### Bucles
Els bucles funcionen com a programacio, sempre i quan es compleixi la condicio s'executaran les instruccions, pero si desde un inici no es compleix no s'executaran les instruccions.

```MYSQL
WHILE (condicio) DO
	(instruccions)
END WHILE;
```

Amb repeat es exactament igual que while pero les instruccions s'executaran sempre minim una vegada i despres comprovara si la condicio es compleix, una vegada deixi de complirse deixara de fer el bucle.

```MYSQL
REPEAT
	(instruccions)
UNTIL (condicio)
END REPEAT;
```

### Delimiter
Delimiter serveix per definir quan s'acaba d'executar una sentencia, com les funcions i procediments poden contenir sentencies la funcio o procediment finalitzaria despres de la primera sentencia, per tant gracies a delimiter podem posar com a parametre altre simbol, jo utilitzare // per tant podem crear la funcio o procediment amb varies sentencies.
### IN OUT i INOUT
#### IN
Amb IN li pasem un parametre quan truquem una funcio o procediment i encara que dins de la funcio cambiem el valor quan finalitzi la variable tindra el mateix valor que abans de trucar a la funcio o procediment.

```MYSQL
SET @v = 10;

CALL cambia(@v);
(funcio cambia valor de @v a 20)

SELECT @v;
(seguira tenint el valor de 10)
```
#### INOUT
Amb INOUT el valor que li introduim a una funcio si es modifica dins de la funcio o procediment el valor de la variable una vegada acabi la funcio el valor de la variable sera el nou valor que s'ha assignat a la funcio.

```MYSQL
SET @v = 10;

CALL cambia(@v);
(funcio cambia valor de @v a 20)

SELECT @v;
(el valor de @v sera 20)
```
#### OUT
Amb OUT basicament inicialitzarem una variable amb un valor i quan li pasem a la funcio aquest valor sera null i durant la funcio se li donara algun valor, al finalitzar la funcio la variable tindra el valor que se li ha donat dins de la funcio.

```MYSQL
SET @v = 10;

CALL cambia(@v);
(funcio inicialitza internament @v a null i cambia valor de @v a 20)

SELECT @v;
(la variable @v valdra 20)
```
## Events
Els events serveixen per executar certes funcions o procedures cada cert temps, com per exemple que cada dia comprobi si es l'aniversari d'un empleat per actualitzar la seva edad. Un event es fa de la seguent forma:

```MYSQL
CREATE EVENT (nom del event)
	ON SCHEDULE AT (quan executa)
	DO
		(sentencies executades o procedures cridats)
```

Podem posar un TIMESTAMPDIFF o una data i hora especifica o que es faci cada cert temps.

```MYSQL
CREATE EVENT evento
	ON SCHEDULE AT "2025-05-15 00:00:00" / CURRENT_TIMESTAMP + INTERVAL 1 HOUR / EVERY 1 HOUR
	DO
		UPDATE empleats SET salari = salari + 100;
```
## Cursors
Els cursors ens ajuden a recorrer les dades d'una select, la estructura d'un cursor seria la seguent:

```MYSQL
DELIMITER //
CREATE PROCEDURE spProcedureCursor()
BEGIN
	DECLARE fin_cursor = false;
	
	DECLARE cCursor CURSOR FOR SELECT empleat_id,nom,cognoms FROM empleats;
	
	DECLARE (CONTINUE / EXIT) HANDLER FOR NOT FOUND
		BEGIN
			SET fin_cursor = true;
		END;
	
	OPEN cCursor;
	
	FETCH cCursor INTO temp_id,temp_nom,temp_cognoms
	
	WHILE(fin_cursor = false) DO
		(logica necesaria)
	END WHILE;
	
	CLOSE cCursor;
//
DELIMITER ;
```

Aqui podem veure que els procesos per utilitzar un cursor son:
1. DECLARAR el cursor amb la taula que utilitzarem.
2. OBRIR el cursor que utilitzarem.
3. AGAFAR les dades de la taula que consultem, cada lectura agafa una fila.
4. TANCAR el cursor.

Aqui podem veure que la gestio que es fa quan no hi han mes files es crear un valor bolea, y que quan salti la exepcio de NOT FOUND que es basicament que estem intentant accedir a una columna que no existeix perque ja s'han acabat, cambiar el valor bolea d'aquesta variable per aixi finalitzar el bucle el qual estabem utilitzant per obtenir les dades.
## Triggers
