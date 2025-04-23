# Finestra MySQL
## Tipus agregat
Les funcions d'agregat son principalment AVG, SUM, COUNT... Per tant podem utilitzar finestra per ajudarnos a fer mes senzilles les consultes utilitzant aquestes funcions d'agregat.

Les funcions de finestra s'utilitzen per fer consultes mes optimitzades y a mes a mes tenen una estructura mes llegible. Podem aplicar les funcions de finestra com al seguent exemple per sapiguer el salari i la diferencia de salari d'un empleat respectivament al seu departament.

```MYSQL
SELECT e.empleat_id, e.nom, e.salari, e.departament_id,
	ROUND(AVG(e.salari) OVER (PARTITION BY e.departament_id),2) AS avg_salari,
    ROUND(ABS(AVG(e.salari) OVER (PARTITION BY e.departament_id) - e.salari),2) AS diferencia
	FROM empleats e
WHERE e.departament_id IS NOT NULL;
```

Tambe podem complementar les funcions de finestra amb les CTE com al seguent exemple fent la consulta encara mes optimitzada:

```MYSQL
WITH cte_avg_salari AS (
	SELECT e.empleat_id, e.nom, e.departament_id, e.salari,
		ROUND(AVG(e.salari) OVER (PARTITION BY e.departament_id),2) AS avg_salari    
		FROM empleats e
	WHERE e.departament_id IS NOT NULL
)
SELECT *, ROUND(ABS(avg_salari - salari),2) AS diferencia
	FROM cte_avg_salari;
```
## Ranquing
### RANK
Asigna un numero per classificar les dades segons el ORDER BY que posem. Pero quan hi ha un valor repetit assigna a aquests dos un el mateix numero classificatori i al seguent per exemple li assigna a aquests dos valors repetits "1" i al seguent directament li assigna "3".

```MYSQL
SELECT e.nom, e.departament_id, e.salari,
	RANK() OVER (PARTITION BY departament_id ORDER BY salari) AS ranking
	FROM empleats e;
```

RESULTAT:

| nom      | salari | departament_id | ranquing |
| -------- | ------ | -------------- | -------- |
| Fernando | 3000   | 2              | 1        |
| David    | 5000   | 1              | 1        |
| Steven   | 5000   | 1              | 1        |
| Adrian   | 6000   | 1              | 3        |
| Bob      | 6000   | 2              | 2        |

### DENSE_RANK
DENSE_RANK funciona exactament com RANK pero amb un petit cambi. Asigna un numero per classificar les dades segons el ORDER BY que posem. Pero quan hi ha un valor repetit assigna a aquests dos un el mateix numero classificatori i al seguent per exemple li assigna a aquests dos valors repetits "1" i al seguent directament li assigna "2" en comptes de "3" com faria RANK.

```MYSQL
SELECT e.nom, e.departament_id, e.salari,
	DENSE_RANK() OVER (PARTITION BY departament_id ORDER BY salari) AS ranking
	FROM empleat e;
```

RESULTAT:

| nom      | salari | departament_id | ranquing |
| -------- | ------ | -------------- | -------- |
| Fernando | 3000   | 2              | 1        |
| David    | 5000   | 1              | 1        |
| Steven   | 5000   | 1              | 1        |
| Adrian   | 6000   | 1              | 2        |
| Bob      | 6000   | 2              | 2        |

### ROW_NUMBER
ROW_NUMBER simplement anira enumerant per cada fila segons el ORDER BY que posem per establir com li van arribant les files, en aquest exemple com el particiona per departament doncs ens el numera mitjançant el departament.

```MYSQL
SELECT e.nom, e.departament_id, e.salari,
	ROW_NUMBER() OVER (PARTITION BY departament_id ORDER BY salari) AS ranking
	FROM empleat e;
```

RESULTAT:

| nom      | salari | departament_id | ranquing |
| -------- | ------ | -------------- | -------- |
| Fernando | 3000   | 2              | 1        |
| David    | 5000   | 1              | 1        |
| Steven   | 5000   | 1              | 2        |
| Adrian   | 6000   | 1              | 3        |
| Bob      | 6000   | 2              | 2        |

### PERCENT_RANK
Aqui podem veure que PERCENT_RANK basicament el que fa en aquest cas es agafar el numero de files que estan agrupades segons el que posem al PARTITION BY i ens dona el recorregut com els empleats del departament 1, podem veure que son 5 per tant divideix 1 entre cinc y reparteix entre ells el percentatge de forma que hi hagi la mateixa distancia entre ells.

```MYSQL
SELECT e.nom, e.departament_id, e.salari,
	PERCENT_RANK() OVER (PARTITION BY departament_id ORDER BY salari) AS percent
	FROM empleat e;
```

RESULTAT:

| nom      | salari | departament_id | percent |
| -------- | ------ | -------------- | ------- |
| Fernando | 3000   | 2              | 0       |
| David    | 5000   | 1              | 0       |
| Steven   | 5000   | 1              | 0.25    |
| Sandra   | 5500   | 1              | 0.5     |
| Joel     | 6000   | 1              | 0.75    |
| Adrian   | 6000   | 1              | 1       |
| Bob      | 6000   | 2              | 1       |

### NTILE
NTILE es pot utilitzar per exemple per fer separar segons un requisit una mateixa consulta de forma que la podem crear x trosos, no mes de les files que retorna.

Aqui al seguent exemple podem veure que li diem que fraccioni entre 2, com son un total de 7 files no podem deixar-ho en 3.5 per tant el que fa es afegir una al primer o depenent el cas al primer i al segon y la resta deixarlos amb grups de la mateixa quantitat de files.

```MYSQL
SELECT e.nom, e.salari, e.departament_id,
       NTILE(2) OVER (ORDER BY e.salari) AS fraccio
FROM empleats e;
```

RESULTAT:

| nom      | salari | departament_id | fraccio |
| -------- | ------ | -------------- | ------- |
| Fernando | 3000   | 2              | 1       |
| David    | 5000   | 1              | 1       |
| Steven   | 5000   | 1              | 1       |
| Sandra   | 5500   | 1              | 1       |
| Joel     | 6000   | 1              | 2       |
| Adrian   | 6000   | 1              | 2       |
| Bob      | 6000   | 2              | 2       |
