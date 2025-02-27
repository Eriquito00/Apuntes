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
Basicament que la subconsulta que fem pot crear nomes una sola columa amb el numero de files que sigui.
#### IN

```SQL
SELECT e.nom
	FROM empleats e
WHERE e.departament_id IN (SELECT d.departament_id
								FROM departaments d
							WHERE d.nom RLIKE '_H$');
```

La estructura simple es basica i es que la consulta mostrara els empleats que el id de departament que pertanyen estigui a la llista que crea aquesta subconsulta.

![](../../../../Imatges/Pasted%20image%2020250227143214.png)
![](../../../../Imatges/Pasted%20image%2020250227143318.png)

Aquests serien els id dels departaments dels quals el seu nom finalitzi amb \_H. I podem veure que el resultat de la consulta sencera es el nom dels empleats els quals pertanyen a aquests departaments.
#### ANY

```SQL
SELECT e.nom, e.salari
	FROM empleats e
WHERE e.salari < ANY (SELECT e2.salari
						FROM empleats e2
					WHERE e2.departament_id = 60);
```

```SQL
SELECT e.nom, e.salari
	FROM empleats e
WHERE e.salari < (SELECT MAX(e2.salari)
						FROM empleats e2
					WHERE e2.departament_id = 60);
```

Aqui podem veure que aquestes dues consultes ens donaran exactament el mateix resultat, aixo es perque podem fer-ho en format llista o ja agafar el salari mes gran d'una llista. ANY o el camp maxim d'una columna s'utilitza per agafar les dades de forma que si algun salari es mes petit que algun salari que te la subconsulta de ANY directament agafara aquesta dada.

![](../../../../Imatges/Pasted%20image%2020250227144241.png)
![](../../../../Imatges/Pasted%20image%2020250227144258.png)

Aqui podem veure el resultat de la subconsulta i el de la consulta, podem veure que tots els salaris son mes petits que el salari maxim de la subconsulta que en aquest cas es 9000. Pero per exemple el salari de "Diana" ja es mes petit que 6000 per tant aquest salari ja entra directament per el 9000 i per el 6000, pero aixo ens dona "igual" quan utilitzem el MAX ja que directament agafa el mes gran i sempre i quan sigui mes petit agafara la dada.
#### ALL

```SQL
SELECT e.nom, e.salari
	FROM empleats e
WHERE e.salari < ALL (SELECT e2.salari
						FROM empleats e2
					WHERE e2.departament_id = 60);
```

```SQL
SELECT e.nom, e.salari
	FROM empleats e
WHERE e.salari < (SELECT MIN(e2.salari)
						FROM empleats e2
					WHERE e2.departament_id = 60);
```

Aqui podem veure que aquestes dues consultes ens donaran exactament el mateix resultat, aixo es perque podem fer-ho en format llista o ja agafar el salari mes gran d'una llista. ALL o el camp minim d'una columna s'utilitza per agafar les dades de forma que si alguna dada es mes petita que absolutament totes les dades de la subconsulta, llavors l'agafa.

![](../../../../Imatges/Pasted%20image%2020250227144241.png)
![](../../../../Imatges/Pasted%20image%2020250227145200.png)

Aqui podem veure que nomes ens ha agafat les dades dels empleats dels quals el seu salari sigui mes petit que absolutament totes les dades de la subconsulta, per tant podriem agafar el MIN i sempre i quan sigui mes petit que el minim hauriem d'agafar aquella dada.
### Tipus multi-columna

```SQL
SELECT a.nom, a.salari
	FROM (SELECT e.nom, e.salari, e.data_contractacio
		FROM empleats e) AS a
WHERE YEAR(a.data_contractacio) = 1999;
```

Aqui podem veure una consulta amb una consulta com a taula, aquesta subconsulta pot tenir un o mes columnes i una o mes files.

![](../../../../Imatges/Pasted%20image%2020250227152728.png)
![](../../../../Imatges/Pasted%20image%2020250227152740.png)

Aqui podem veure la subconsulta que hem utilitzat com a taula per fer la consulta i tenim el resultat com una consulta normal i corrent nomes que hem utilitzar en comptes de una taula real una taula feta a base de una subconsulta.

A mes a mes si no volem tenir aquesta taula a la nostre base de dades podem crear una VIEW per poder utilitzar aquesta consulta com a taula sense necesitat de tenir una taula a la nostre base de dades.
### Amb mes d'un atribut

```SQL
SELECT e.nom, e.salari
	FROM empleats e
WHERE (e.nom, e.salari) = (SELECT nom, salari
								FROM empleats
							ORDER BY salari DESC
							LIMIT 1);
```

Aqui podem veure que estem comparant dues dades a la vegada a una mateixa subconsulta, aixo ens serveix si volem trobar alguna dada a la qual es requereixi que concideixin les seves dades.

Com per exemple en aquest cas que volem sapiguer comparant el nom i el salari amb el nom i el salari del empleat que mes cobra, amb aixo podem obtenir totes les dades que concideixim amb els atributs que comparem de la consulta amb el resultat de la subconsulta.
### EXISTS

```SQL
SELECT e.nom, e.salari, e.data_contractacio
	FROM empleats e
WHERE EXISTS (SELECT *
				FROM empleats e2
			WHERE e.empleat_id = e2.id_cap);
```

Aqui podem veure que he utilitzat exists per comparar el id del empleat amb el id dels caps (jefes) de la mateixa taula empleats, basicament exists comprova que al camp que li diem dins de la subconsulta estigui al segon camp que es un camp de la consulta inicial.

Sempre compararem un camp de la mateixa subconsulta amb un camp de la consulta a la que pertany. Les columnes o dades que retornem al SELECT de la subconsulta son irrellevants, no serveixen per res.