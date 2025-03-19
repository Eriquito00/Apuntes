# CTE MySQL
Gracies a les CTE podem posar nom com si fosin una "taula temporal" a les nostres subconsultes i poder utilitzarles despres a una consulta.
## WITH
Gracies a WITH podem utilitzarlo per crear una taula a una "variable", com al seguent exemple:
```MYSQL
WITH empleatsIT AS (SELECT *
		FROM empleats e
		INNER JOIN departaments d ON d.departament_id = e.departament_id
	WHERE d.nom = "IT_PROG")
SELECT *
	FROM empeatsIT
```

A mes a mes podem crear diferents subconsultes com a petites "taules temporals".

```MYSQL
WITH empleatsIT AS (SELECT *
		FROM empleats e),
	departamentIT AS (SELECT *
		FROM departaments d
	WHERE d.nom = "IT_PROG")
SELECT *
	FROM empeatsIT eIT
	INNER JOIN departamentIT dIT ON dIT.departament_id = eIT.departament_id;
```
## WITH RECURSIVE
Amb WITH RECURSIVE podem fer funcions recursives com la seguent:

```MYSQL
WITH RECURSIVE qn(cont) AS (
	SELECT 20 AS cont
	UNION
	SELECT 1 + cont
		FROM qn
	WHERE cont < 25
)
SELECT cont
	FROM qn;
```

Aqui podem veure que el primer SELECT es el valor minim que asignem, per tant la "variable" cont tindra el valor de 20. Una vegada aixo el segon select ens dona el valor de count + 1, per tant ens aniria donant les dades, 20 - 21 - 22 - 23 - 24 i una vegada arriba al 25 es l'ultim que agafa, ja que al WHERE li diem que sigui mes petit que 25, com 25 es igual a 25 es l'ultim que agafem i alla finalitza.

Tambe tenim un us mes real al seguent exemple:

```MYSQL
WITH RECURSIVE begudesEnsucrades AS (
	SELECT categoria_id, nom, cat_pare_id, 0 nivell
		FROM categories
	WHERE cat_pare_id IS NULL
    UNION ALL
    SELECT c.categoria_id, c.nom, c.cat_pare_id, nivell + 1
		FROM categories c
        INNER JOIN begudesEnsucrades be ON c.cat_pare_id = be.categoria_id
)
SELECT *
	FROM begudesEnsucrades;
```