# RRHH
## 1.2 Base de dades Recursos Humans (RRHH)
Aqui tens la [Base de dades de RRHH](BBDD/bbdd_rrhh.sql)
### 1.2.3 Consultes sobre una taula amb funcions

1. Llista totes les columnes de la taula empleats.
```mysql
SELECT *
	FROM empleats;
```

2. Llista els cognoms de tots els empleats.
```mysql
SELECT cognoms
	FROM empleats;
```

3. Llista els cognoms dels empleats eliminant els cognoms que estiguin repetits.
```mysql
SELECT DISTINCT cognoms
	FROM empleats;
```

4. Llista el nom i els cognoms de tots els empleats.
```mysql
SELECT nom, cognoms
	FROM empleats;
```

5. Mostra els cognoms i nom dels empleats concatenats amb una coma i un espai en blanc.
```mysql
SELECT CONCAT(nom, ', ', cognoms) AS nomcomplet
	FROM empleats;
```

6. Volem una columna on estigui tot en majúscules i l’altre tot en minúscules. Anomena les columnes com a "nom_majuscules" i "nom_minuscules" respectivament.
```mysql
SELECT UPPER(nom) AS  nom_majuscules, LOWER(nom) AS nom_minuscules
	FROM empleats;
```

7. Mostra les 6 primeres lletres dels cognoms dels empleats
```mysql
SELECT LEFT(cognoms, 6)
	FROM empleats;
```

8. Quins són els empleats que tenen la longitud del cognoms major a 6? (Mostra els cognoms i la longitud)
```mysql
SELECT cognoms, LENGTH(cognoms) AS longitud
	FROM empleats
WHERE LENGTH(cognoms) > 6;
```

9. Substitueix totes les 'a' dels cognoms dels empleats per 'e'. Ordena pel nou valor dels cognoms
```mysql
SELECT REPLACE(REPLACE(cognoms,'a','e'),'A','E')
	FROM empleats
    ORDER BY cognoms;
```

10. Mostra tots els empleats que tenen en la segona posició dels cognoms una 'a'. (Sense utilitzar l’operador LIKE, ni REGEXP)
```mysql
SELECT cognoms
	FROM empleats
WHERE LOCATE('a', cognoms, 2) = 2;
```

11. Per cada empleat mostra el codi d’empleat, cognom i el salari amb un augment del 15% expressat com un número enter, etiqueta la columna amb el nom "nou_salari".
```mysql
SELECT empleat_id, cognoms, FLOOR(salari * 1.15) AS nou_salari
	FROM empleats;
```

12. Partint de la consulta anterior, afegeix una nova columna que mostri la diferencia salarial entre el nou salari i l’antic. Etiqueta la columna com a "increment"
```mysql
SELECT empleat_id, cognoms, FLOOR(salari * 1.15) AS nou_salari, FLOOR(salari * 1.15) - salari AS increment
	FROM empleats;
```

13. Fes una consulta on mostri el cognom de l’empleat en majúscules i la longitud del cognom dels empleats on el seu cognom comenci per J, A o M. Ordena els resultats per cognom d’empleat.
```mysql
SELECT UPPER(cognoms)
	FROM empleats
WHERE LEFT(UPPER(cognoms),1) = 'J' OR LEFT(UPPER(cognoms),1) = 'A' OR LEFT(UPPER(cognoms),1) = 'M';
```

14. Fes una consulta on mostri el codi, nom i cognoms dels empleats que van ser contractats un dilluns o un divendres.
```mysql
SELECT empleat_id, nom, cognoms
	FROM empleats
WHERE DAYOFWEEK(data_contractacio) IN (2,6);
```

15. Mostra l’import de comissió dels empleats. Etiqueta la columna com a "import_comissio" i arrodoneix el valor a 2 decimals. Si un empleat no té assignada comissió fes el que calgui per tal que el resultat de l’operació surti zero en comptes de NULL. Mostra també el cognom i el salari en Ptes despreciant els decimals (truncar)
```mysql
SELECT cognoms, TRUNCATE(salari, 0), IFNULL(ROUND(salari * pct_comissio, 2),0) AS import_comisio, cognoms, TRUNCATE(salari * 166.386, 0) AS salari_ptes
	FROM empleats;
```

16. Utilitzant alguna de les funcions de dates, obté el nom, cognom i data de contractació dels empleats contractats durant el 1997.
```mysql
SELECT nom, cognoms, data_contractacio
	FROM empleats
WHERE YEAR(data_contractacio) = 1997;
```

17. Utilitzant alguna de les funcions de data, mostra tots els empleats que van ser contractats entre els mesos de juny i novembre, independentment de l’any.
```mysql
SELECT nom, cognoms, data_contractacio
	FROM empleats
WHERE MONTH(data_contractacio) BETWEEN 6 AND 11;
```

18. El nostre departament de recursos humans s’aborreix molt i per justificar el seu sou està elaborant tot d’estadístiques extranyes. Ara volen saber quins empleats varen ser contractats en un dia parell.
```mysql
SELECT nom, cognoms, data_contractacio
	FROM empleats
WHERE DAY(data_contractacio) % 2 = 0;
```

19. Mostra el cognom, la data de contractació i el dia de la setmana en el que va començar l’empleat a treballar. Etiqueta la columna com a dia. Ordena els resultats per dia de la setmana.
```mysql
SELECT cognoms, data_contractacio, DAYOFWEEK(data_contractacio) AS dia
	FROM empleats
    ORDER BY DAYOFWEEK(data_contractacio);
```

20. Mostra el codi d’empleat, cognoms i la data de contractació en format AAAAMM. El dia no ens interessa ara en el nostre estudi estadístic. Ordena per aquest nou format de data.
```mysql
SELECT empleat_id, cognoms, DATE_FORMAT(data_contractacio,"%Y%m")
	FROM empleats
	ORDER BY CONCAT(YEAR(data_contractacio),MONTH(data_contractacio));
```

21. Per cada empleat, mostra el cognom, la data de contractació i el número de mesos entre el dia d’avui i la data de contractació. Etiqueta la columna com a "mesos_treballats" i arrodoneix sense decimals. Ordena el resultat segons els mesos treballats de més a menys.
```mysql
SELECT cognoms, data_contractacio, ROUND(TIMESTAMPDIFF(MONTH,data_contractacio,CURDATE()), 0) AS mesos_treballats
	FROM empleats;
```

22. Mostra el nom, cognom i anys d’antiguitat dels empleats que tenen una antiguitat superior o igual a 20 anys a l’empresa.
```mysql
SELECT nom, cognoms, YEAR(CURDATE()) - YEAR(data_contractacio)
	FROM empleats
WHERE YEAR(CURDATE()) - YEAR(data_contractacio) > 20 OR 
		YEAR(CURDATE()) - YEAR(data_contractacio) = 20 AND
        MONTH(CURDATE()) >= MONTH(data_contractacio) AND
        DAY(CURDATE()) >= DAY(data_contractacio);
```

23. Crea una consulta per mostrar el cognom i salari de tots els empleats que guanyen més de 10.000 a l’any. Dona format al camp salari per a que tingui 15 caràcters de longitud, omplint per l’esquerra amb $. Etiqueta la columna com a salari.
```mysql
SELECT cognoms, LPAD(salari,14,"$") AS salari
	FROM empleats
WHERE salari > 10000;
```

24. Mostra el cognom, salari i percentatge de comissió dels empleats. Afegeix una nova columna en que si un empleat no té assignada comissió, posi "SenseComissió". Etiqueta la columna amb nom "no_comissio"
```mysql
SELECT cognoms, salari, IFNULL(pct_comissio, "SenseComissió") AS no_comissio
	FROM empleats;
```

25. Mostra el cognom, salari i utilitzant la funció CASE, mostra el següent enfunció del valor del salari
  - Si el salari està entre 0 i 3000 -> "Mig"
  - Si el salari està entre 12000 i 24000 -> "Alt"
  - Qualsevol altre valor posa "Altres"
  - Anomena la columna com a "poder_adquisitiu" i ordena per salari de menor a major
```mysql
SELECT cognoms, salari,
	CASE 
		WHEN salari BETWEEN 0 AND 3000 THEN "Mig"
		WHEN salari BETWEEN 12000 AND 24000 THEN "Alt"
		ELSE "Altres"
    END AS poder_adquisitiu
    FROM empleats;
```

26. Llista el codi dels departaments dels empleats que apareixen a la taula empleats.
```mysql
SELECT departament_id
	FROM empleats
    ORDER BY departament_id;
```

27. Partint de la consulta anterior elimina els codis de departament repetits.
```mysql
SELECT DISTINCT departament_id
	FROM empleats
WHERE departament_id IS NOT NULL;
```

28. Calcula el nombre d'empleats que **no tenen** comissió assignada. 
```mysql
SELECT COUNT(empleat_id) AS SenseComissio
	FROM empleats
WHERE pct_comissio IS NULL;
```

### 1.2.4 Consultes sobre una taula utilitzant agrupaments

1. Quants empleats van ser contractats l'any passat.
```mysql
SELECT COUNT(*)
	FROM empleats
WHERE YEAR(data_contractacio) = YEAR(CURDATE()) - 1;
```

2. Quin és el treballador (nº d’anys no el nom del treballador) amb més anys d'antiguitat.
```mysql
SELECT MAX(YEAR(NOW()) - YEAR(data_contractacio))
	FROM empleats;
```

3. Quin és el treballador(nº d’anys no el nom del treballador) amb menys anys d'antiguitat.
```mysql
SELECT MIN(YEAR(NOW()) - YEAR(data_contractacio))
	FROM empleats;
```

4. Quin és el salari mig de l'empresa
```mysql
SELECT AVG(salari)
	FROM empleats;
```

5. Mostra el salari més alt i el més baix dels empleats. Anomena les columnes com a "salari_max" i "salari_min" respectivament.
```mysql
SELECT MAX(salari) AS salari_max, MIN(salari) AS salari_min
	FROM empleats;
```

6. Mostra la mitjana dels salaris i el número d’empleats que tenim. Arrodoneix la mitjana al número enter més pròxim i anomena les columnes com a salari_mig i num_empleats respectivament.
```mysql
SELECT ROUND(AVG(salari),0) AS salari_mig, COUNT(empleat_id) AS num_empleats
	FROM empleats;
```

7. Mostra, per cada tipus de treball, la mitjana dels salaris. Ordena la informació per tipus de treball.
```mysql
SELECT AVG(salari), feina_codi
	FROM empleats
GROUP BY feina_codi
ORDER BY feina_codi;
```

8. Quants empleats tenim assignats a cada tipus de treball? Ordena la informació per número d’empleats.
```mysql
SELECT feina_codi, COUNT(empleat_id) AS num_empleats
	FROM empleats
GROUP BY feina_codi
ORDER BY num_empleats;
```

9. Quants empleats tenim assignats a cada departament? Mostra el  codi de departament i el número d’empleats que té. Ordena la informació per número d’empleats.
```mysql
SELECT departament_id, COUNT(empleat_id) AS empleats
	FROM empleats
GROUP BY departament_id
ORDER BY empleats;
```

10. Partint de la consulta anterior, volem saber també quants empleats no tenen departament assignat. Mostra el text "No assignat" com a identificador del departament.
```mysql
SELECT IFNULL(departament_id, "No assignat"), COUNT(empleat_id) AS empleats
	FROM empleats
WHERE departament_id IS NULL
GROUP BY departament_id
ORDER BY empleats;
```

11. Quants directors (caps) diferents tenim? Anomena la columna com a "numero_de_directors"
```mysql
SELECT  COUNT(DISTINCT id_cap)
	FROM empleats;
```

12. Fes una consulta per calcular la diferència que hi  ha entre el salari màxim i el mínim dels empleats. Anomena la columna com a "diferencia".
```mysql
SELECT MAX(salari) - MIN(salari) AS diferencia
	FROM empleats;
```

13. Mostra, per cada cap, el número identificador de l’empleat (com a cap) i el salari de l’empleat pitjor pagat per a aquest cap. Exclou els empleats  que no tinguin assignat cap.
```mysql
SELECT DISTINCT id_cap, MIN(salari)
	FROM empleats
WHERE id_cap IS NOT NULL
GROUP BY id_cap;
```

14. Partint de la consulta anterior, exclou també aquells caps en què el salari mínim sigui inferior o igual a 6.000.
```mysql
SELECT DISTINCT id_cap, MIN(salari)
	FROM empleats
GROUP BY id_cap
HAVING id_cap IS NOT NULL AND MIN(salari) >= 6000;
```

15. Obté el número d’empleats contractats per cada any. Ordena la informació per any.
```mysql
SELECT YEAR(data_contractacio) AS any, COUNT(empleat_id) AS num_empleats
	FROM empleats
GROUP BY any;
```

16. Mostra els codis de departament que tenen 3 o més empleats. Mostra només el codi del departament.
```mysql
SELECT departament_id
	FROM empleats
GROUP BY departament_id
HAVING COUNT(empleat_id) >= 3;
```

17. Mostra el nombre d'empleats que cobren més de 9.000 euros.
```mysql
SELECT COUNT(empleat_id) AS cobra_mucho
	FROM empleats
WHERE salari > 9000;
```

### 1.2.5 Consultes multitaula (JOINs)

1. Mostra de cada empleat, el nom del departament, cognoms i nom de l’empleat. Ordena les dades per nom departament, cognoms i nom de forma ascendent.

```SQL
SELECT d.nom, e.cognoms, e.nom
	FROM empleats AS e INNER JOIN departaments AS d
	ON e.departament_id = d.departament_id
ORDER BY d.nom, e.cognoms, e.nom;
```

2. Mostra de cada departament, el codi, el nom de departament, l’adreça, el codi postal i el nomde la ciutat.

```SQL
SELECT d.departament_id, d.nom, l.adreca, l.codi_postal, l.ciutat
	FROM localitzacions AS l INNER JOIN departaments AS d
	ON l.localitzacio_id = d.localitzacio_id;
```

3. Mostra del departament de 'Marketing', el codi, el nom de departament, l'adreça, el codi postal i el nom de la ciutat. Per simplificar l'escriptura dona un alias a les taules (per exemple d per departaments i l per localitzacions).

```SQL
SELECT d.departament_id, d.nom, l.adreca, l.codi_postal, l.ciutat
	FROM localitzacions AS l INNER JOIN departaments AS d
	ON l.localitzacio_id = d.localitzacio_id
WHERE d.nom = "Marketing";
```

4. De les localitzacions amb codi 1400, 1700 i 2500, ens interessa saber el seu codi, el nom de la ciutat, el nom de l’estat/província, el nom del país i el nom de la regió. Ordena per codi localització.

```SQL
SELECT l.localitzacio_id, l.ciutat, l.estat_provincia, p.nom, r.nom
	FROM localitzacions AS l INNER JOIN paisos AS p
    ON l.pais_id = p.pais_id INNER JOIN regions AS r
    ON r.regio_id = p.regio_id
WHERE localitzacio_id IN(1400,1700,2500);
```

5. Escriu una consulta per mostrar el nom de cada departament, la ciutat on està localitzat el departament, el número d’empleats i el salari mig per tots els empleats d’aquell departament. Anomena les columnes com Nom, Ciutat, Num_Empleats i Salari_Mig respectivament. Arrodoneix el salari mig a dos decimals. Ordena la informació per nom de departament. Intenta de mostrar els punts de miler i la coma com a símbol separador dels valors decimals.

```SQL
SELECT d.nom AS Nom, l.ciutat AS Ciutat, COUNT(e.empleat_id) AS Num_Empleats, FORMAT(ROUND(AVG(e.salari), 2),2, 'es_ES') AS Salari_Mig
	FROM localitzacions AS l 
    INNER JOIN departaments AS d ON d.localitzacio_id = l.localitzacio_id
    INNER JOIN empleats AS e ON d.departament_id = e.departament_id
GROUP BY d.departament_id
ORDER BY Nom;
```

6. Partint de l’historial de treballs, volem saber els empleats que han treballat en més d’una feina. Volem saber el codi d’empleat, el seu nom i cognoms i el número de feines que ha tingut. Anomena la columna id_empleat com a CodiEmpl i el numero de feines com a Num_feines. Ordena la informació per nom i cognoms d’empleat.

```SQL
SELECT e.empleat_id AS CodiEmpl, e.nom, e.cognoms, COUNT(hf.feina_codi) AS Num_feines
	FROM historial_feines AS hf INNER JOIN empleats AS e ON hf.empleat_id = e.empleat_id
GROUP BY e.empleat_id
HAVING Num_feines > 1
ORDER BY e.nom ASC, e.cognoms ASC;
```

7. Obtenir el codi d’empleat, nom i cognoms, nom de departament i salari del primer empleat que té el salari més baix.

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, d.nom, MIN(e.salari) AS salari_min
	FROM empleats AS e 
    LEFT JOIN departaments AS d ON e.departament_id = d.departament_id
GROUP BY e.empleat_id
ORDER BY MIN(e.salari) ASC
LIMIT 1;
```

8. Volem saber, dels empleats que van ser contractats abans del 1999 i que tenen un salari entre 10000 i 20000, quins pertanyen al departament de Vendes o de Comptes. Mostrar el codi empleat, nom i cognoms, salari, l’any de la data de contractació i el nom de departament. 

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e.salari, e.data_contractacio, d.nom
	FROM empleats AS e
    INNER JOIN departaments AS d ON e.departament_id = d.departament_id
WHERE YEAR(e.data_contractacio) < 1999 AND e.salari BETWEEN 10000 AND 20000 AND (d.nom = "Vendes" OR d.nom = "Compres");
```

9. Mostra el nom del departament, cognoms i nom de tots els empleats ( encara que no tinguin assignat cap departament ). Ordena les dades per nom departament, cognom i nom. 

```SQL
SELECT d.nom, e.cognoms, e.nom
	FROM departaments AS d
    RIGHT JOIN empleats AS e ON e.departament_id = d.departament_id
ORDER BY d.nom, e.cognoms, e.nom;
```

10. Volem saber, de cada departament, els empleats que té assignats. Mostra el codi de departament, nom del departament, cognoms i nom de l’empleat ( mostra tots els departaments encara que no tinguin assignat cap empleat ). Ordena les dades per nom departament, cognoms i nom d’empleat. 

```SQL
SELECT d.departament_id, d.nom, e.cognoms, e.nom
	FROM departaments AS d
    LEFT JOIN empleats AS e ON e.departament_id = d.departament_id
ORDER BY d.nom, e.cognoms, e.nom;
```

11. Volem mostrar el nom del departament i el número d’empleats que té. Ordena la informació per nom de departament. 

```SQL
SELECT d.nom, COUNT(e.departament_id) AS qt
	FROM departaments AS d
    INNER JOIN empleats AS e ON e.departament_id = d.departament_id
GROUP BY d.departament_id;
```

12. Partint de la consulta anterior, volem incloure també en el llistat dels departaments que no tenen cap empleat assignat. 

```SQL
SELECT d.nom, COUNT(e.departament_id) AS qt
	FROM departaments AS d
    LEFT JOIN empleats AS e ON e.departament_id = d.departament_id
GROUP BY d.departament_id;
```

13. Mostra els empleats que treballen com a 'Programadors' o 'Venedors' . Volem saber el codi empleat, cognoms, el nom del treball el seu salari, i el salari mínim de la feina a la que estan assignats. 

```SQL
SELECT e.empleat_id, e.cognoms, f.nom_treball, e.salari, f.salari_min
	FROM departaments AS d
    INNER JOIN empleats AS e ON d.departament_id = e.departament_id
    INNER JOIN feines AS f ON e.feina_codi = f.feina_codi
WHERE f.nom_treball IN ("Programador", "Venedor");
```

14. Partint de la consulta anterior mostra només els que guanyen més de 1000 euros respecte el salari mínim. 

```SQL
SELECT e.empleat_id, e.cognoms, f.nom_treball, e.salari, f.salari_min
	FROM departaments AS d
    INNER JOIN empleats AS e ON d.departament_id = e.departament_id
    INNER JOIN feines AS f ON e.feina_codi = f.feina_codi
WHERE f.nom_treball IN ("Programador", "Venedor") AND (f.salari_min + 1000) < e.salari;
```

15. Partint de la taula historial de treballs, volem saber el nom i cognoms, la data inici i fi que va realitzar el treball, el nom del treball i el nom del departament on va estar assignat. 

```SQL
SELECT e.nom, e.cognoms, hf.data_inici, hf.data_fi, f.nom_treball, d.nom
	FROM empleats AS e
    INNER JOIN historial_feines AS hf ON e.empleat_id = hf.empleat_id
    INNER JOIN feines AS f ON hf.feina_codi = f.feina_codi
    INNER JOIN departaments AS d ON d.departament_id = hf.departament_id;
```

16. Volem saber, de cada empleat, el codi d'empleat, el nom i cognoms, el seu salari, el nom del treball que tenen assignat, el nom del departament, la ciutat del departament, el nom de país i el nom de la regió. No cal que mostrar els empleats que no tinguin cap departament o feina

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e.salari, f.nom_treball, d.nom, l.ciutat, p.nom, r.nom
	FROM feines AS f
    INNER JOIN empleats AS e ON e.feina_codi = f.feina_codi
    INNER JOIN departaments AS d ON e.departament_id = d.departament_id
    INNER JOIN localitzacions AS l ON d.localitzacio_id = l.localitzacio_id
    INNER JOIN paisos AS p ON l.pais_id = p.pais_id
    INNER JOIN regions AS r ON p.regio_id = r.regio_id;
```

17. De la consulta anterior mostra també aquells que no tenen cap departament assignat.

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e.salari, f.nom_treball, d.nom, l.ciutat, p.nom, r.nom
	FROM feines AS f
    INNER JOIN empleats AS e ON e.feina_codi = f.feina_codi
    LEFT JOIN departaments AS d ON e.departament_id = d.departament_id
    LEFT JOIN localitzacions AS l ON d.localitzacio_id = l.localitzacio_id
    LEFT JOIN paisos AS p ON l.pais_id = p.pais_id
    LEFT JOIN regions AS r ON p.regio_id = r.regio_id;
```

18. De la consulta anterior mostra també aquelles que no tenen cap feina assignada.

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e.salari, f.nom_treball, d.nom, l.ciutat, p.nom, r.nom
	FROM feines AS f
    LEFT JOIN empleats AS e ON e.feina_codi = f.feina_codi
    LEFT JOIN departaments AS d ON e.departament_id = d.departament_id
    LEFT JOIN localitzacions AS l ON d.localitzacio_id = l.localitzacio_id
    LEFT JOIN paisos AS p ON l.pais_id = p.pais_id
    LEFT JOIN regions AS r ON p.regio_id = r.regio_id;
```

19. Volem saber, dels empleats que tenen assignat cap ( jefe ), el codi d’empleat, nom i cognoms i les dades del seu cap ( codi empleat, nom i cognoms ).

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e2.nom, e2.cognoms
	FROM empleats AS e
	INNER JOIN empleats AS e2 ON e.id_cap = e2.empleat_id;
```

20. Partint de la consulta anterior, ens agradaria afegir la data de contractació tant de l’empleat com la del seu cap, però només volem saber la informació dels empleats que han estat contractats abans que els seus caps.

```SQL
SELECT e.empleat_id, e.nom, e.cognoms, e.data_contractacio, e2.nom, e2.cognoms, e2.data_contractacio
	FROM empleats AS e
	INNER JOIN empleats AS e2 ON e.id_cap = e2.empleat_id
WHERE e.data_contractacio < e2.data_contractacio ;
```

21. Volem saber el número total d’empleats contractats durant el 1996, 1997 i 1998 i el total d’empleats contractats durant aquests anys. Cal mostrar la informació tal com s’indica en la figura.

![](../../../../../Imatges/Pasted%20image%2020250220153441.png)

```SQL
SELECT (SELECT COUNT(empleat_id) FROM empleats WHERE YEAR(data_contractacio) = 1996) AS Any_1996,
	(SELECT COUNT(empleat_id) FROM empleats WHERE YEAR(data_contractacio) = 1997) AS Any_1997,
    (SELECT COUNT(empleat_id) FROM empleats WHERE YEAR(data_contractacio) = 1998) AS Any_1998,
    (SELECT COUNT(empleat_id) FROM empleats WHERE YEAR(data_contractacio) IN(1996,1997,1998)) AS Total
	FROM empleats
LIMIT 1;
```
