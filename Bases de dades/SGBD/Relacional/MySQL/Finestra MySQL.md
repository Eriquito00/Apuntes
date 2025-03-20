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
### DENSE_RANK
### ROW_NUMBER
### PERCENT_RANK
### NTILE
