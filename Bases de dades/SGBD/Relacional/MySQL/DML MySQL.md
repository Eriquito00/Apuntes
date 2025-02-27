# DML MySQL
Data Manipulation Language.
## Parametres MySQL DML
INSERT:
- Insereix nova informacio a una taula sobre diferents columnes que podem seleccionar.

![](/Imatges/Pasted%20image%2020250116164449.png)

DELETE:
- Si fem un delete sol eliminarem totes les dades la taula. Pero tambe podem eliminar files si compleixen alguna condicio com la que estan a l'exemple.

![](/Imatges/Pasted%20image%2020250116164516.png)

UPDATE:
- El UPDATE serveix per editar les dades d'alguna columna de la taula, per exemple aqui podem veure que si el id de localitzacio es 1700 afegirem un "\_H", el CONCAT() es equiparable a un +=, i tambe podem veure si es NULL utilitzant IS o si no es null IS NOT.

![](/Imatges/Pasted%20image%2020250116164657.png)

![](/Imatges/Pasted%20image%2020250116170207.png)

## Consultes a una sola taula (Nivell 1)
SELECT:
- Un select es compon per els atributs de la taula que volem veure, en aquest exemple s'agafen dades de la taula empleats i s'agafaran les dades dels camps nom, cognoms i deparatment_id sempre i quan el departament_id de l'empleat sigui 60, tambe tenim el ORDER BY per dir per quin camp volem ordenar i podem utilitzar DESC per que sigui descendent i ASC perque sigui ascendent.

	![](/Imatges/Pasted%20image%2020250116170308.png)

	FROM: 
	- S'utilitza per indicar de quina taula provenen les dades de les columnes indicades.
	
		![](/Imatges/Pasted%20image%2020250123112816.png)
	
	- Si tenim algun valor repetit i no volem els repetits podem utilitzar DISTINCT.
	
		![](/Imatges/Pasted%20image%2020250123113007.png)
	
	- Tambe podem crear una columna que no es guardara amb alguna operacio aritmetica i tambe podem fer-li que mostri un nom personalitzar a la columna.
	
		![](/Imatges/Pasted%20image%2020250123113135.png)
	
		INNER JOIN:
		- Amb INNER JOIN podem juntar informacio de diferents columnes de 2 o mes taules.
		
		![](../../../../Imatges/Pasted%20image%2020250212113443.png)
		
		LEFT JOIN i RIGHT JOIN:
		- Amb LEFT i RIGHT podem relacionar la taula de l'esquerra amb la taula de la dreta o al reves, es a dir, amb LEFT ens combina totes les dades de les columnes de la esquerra amb les dades de la taula de la columna de la dreta.
		- Exemple LEFT JOIN (Compara tots els empleats amb tots els departaments i retorna el departament al que pertany)
		
		![](../../../../Imatges/Pasted%20image%2020250212113816.png)
		
		![](../../../../Imatges/Pasted%20image%2020250212113850.png)
		
		- Exemple RIGHT JOIN (Compara tots els departaments amb tots els empleats i retorna el departament al que pertany)
		
		![](../../../../Imatges/Pasted%20image%2020250212114009.png)
		
		![](../../../../Imatges/Pasted%20image%2020250212114448.png)
		
		- Tambe podem fer el que es coneix com a FULL JOIN utilitzant RIGHT i LEFT a la vegada.
		
		![](../../../../Imatges/Pasted%20image%2020250212115224.png)
		
		![](../../../../Imatges/Pasted%20image%2020250212115238.png)

	WHERE:
	- Tant al inici del SELECT com al WHERE podem utilitzar operadors aritmetics com el '<', '>', '=', '!=', entre altres.
	
		![](/Imatges/Pasted%20image%2020250123113423.png)

	GROUP BY:
	- S'utilitza per crear un grup segons la columna que li diem i les dades que volem mostrar, per exemple si volem mostrar la mitjana de salari segons un codi de feina com a la consulta que podem veure.
	
		![](../../../../Imatges/Pasted%20image%2020250211151344.png)

	ORDER BY:
	- S'utilitza per ordenar els resultats que donem a la consulta en un format ascendent o descendent segons el camp que li diguem.
	
		![](../../../../Imatges/Pasted%20image%2020250211151100.png)

	HAVING:
	- Despres tenim el HAVING que seria com un "WHERE" del nostre GROUP BY, s'utilitza per posar condicions logiques com al WHERE pero aquest s'executa mes tard per tant el podem utilitzar amb algunes funcions que requereixen fer algun calcul y despres comprovar el calcul, cosa que amb el WHERE no podriem o seria menys eficient.
	
		![](../../../../Imatges/Pasted%20image%2020250211151602.png)
## Consultes de varies taules (Nivell 2)
Per fer consultes de varies taules podem utilitzar exactament la mateixa estructura pero amb algunes variacions per aclarar quina columna es de quina taula, quan fem combinacions entre dues taules tots els valors d'una taula es combinen amb un altre taula.

```SQL
SELECT empleats.nom, empleats.cognoms, empleats.departament_id
	departaments.nom, departaments.departament_id
	FROM empleats, departaments;
```

Amb aquesta consulta agafarem tots els empleats i ens ho comparara amb tots els departaments pero tambe poderm filtrar per no tenir tota la informacio ineficient ja que un empleat que te com a departament 1 sortira sent comparat em el departament 1,2,3... Per que no pasi aixo podem fer el seguent:

```SQL
SELECT empleats.nom, empleats.cognoms, empleats.departament_id,
	departaments.nom, departaments.departament_id
	FROM empleats, departaments
WHERE empleats.departament_id = departaments.departament_id;
```

D'aquesta forma nomes ens mostrara els empleats amb el departament al que pertanyen, per no crear tant de text i tants noms de taules podem fer aquesta modificacio.

```SQL
SELECT e.nom, e.cognoms, e.departament_id,
	d.nom, d.departament_id
	FROM empleats e, departaments d
WHERE e.departament_id = d.departament_id;
```

D'aquesta forma simplifiquem el nom de la taula a una unica lletra o al que nosaltres volguem. A LA NOSTRE NORMATIVA S'UTILITZARA LA PRIMERA LLETRA DEL NOM DE LA TAULA. Per estalviar feina existeix "INNER JOIN".

```SQL
SELECT e.nom, e.cognoms, e.departament_id,
	d.nom, d.departament_id
	FROM empleats e INNER JOIN departaments d ON e.departament_id = d.departament_id;
```

## Subconsultes (Nivell 3)
Les subconsultes son consultes exactament normals pero que ens permeten substituir valors literals (fixes) o valors dinamics per una consulta dins de la consulta inicial.
### Tipus escalat

```SQL
SELECT *
	FROM empleats
WHERE salari < (SELECT AVG(salari) FROM empleats);
```

Aqui podem veure que la subconsulta esta entre parentesis i substitueix a un valor dinamic que podria ser calculat a la mateixa consulta o a un valor fixe pel resultat d'aquesta subconsulta. Podem veure que es de tipus escalat ja que la subconsulta que ens calcula la mitjana nomes retorna una columna i una fila.
### Tipus llista
#### IN
#### ANY
#### ALL
### Tipus multi-columna
### Amb mes d'un atribut
### EXISTS