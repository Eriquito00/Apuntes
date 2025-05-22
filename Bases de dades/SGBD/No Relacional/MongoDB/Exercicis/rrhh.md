# RRHH

1. Obtenir de tots els empleats, el nom, cognoms i salari. Mostrar només 4 registres

```JSON
db.empleats.find({},{"nom":1,"cognoms":1,"salari":1}).limit(4)
```

2. Mostra la quantitat de departaments que hi ha

```JSON
db.departaments.find().count()
```

3. Recupera l’empleat “emplat_id=100”

```JSON
db.empleats.find({"empleat_id": {"$eq": "100"}})
```

4. Recupera els empleats amb el càrrec de “President”

```JSON
db.empleats.find({"feina.nom": {"$eq": "President"}})
```

5. Recupera els empleats que treballen al departament de “IT”

```JSON
db.empleats.find({"departament.nom": {"$eq": "IT"}})
```

6. Recupera els empleats que van ser contractats a partir de l’1 de gener de 1985

```JSON
db.empleats.find({"data_contractacio": {"$gt": new Date("1985-01-01")}})
```

7. Recupera els empleats amb un salari superior a 2000

```JSON
db.empleats.find({"salari": {"$gt": 2000}})
```

8. Recupera els empleats amb un salari entre 2000 i 6000

```JSON
db.empleats.find({"salari": {"$gt": 2000,"$lt": 6000}})
```

9. Recupera els empleats que el seu número de telèfon comença per 515

```JSON
db.empleats.find({"telefon": /^515/})
```

10. Recupera els empleats que no treballin de Vice President. Utilitza el codi de la feina "AD_VP"

```JSON
db.empleats.find({"feina.codi": {"$ne": "AD_VP"}})
```

11. Recupera els empleats que tenen pct_comissio.

```JSON
db.empleats.find({"pct_comissio": {"$exists": true}})
```

12. Recupera els empleats que tenen pct_comissio i hagi treballat o treballin
actualment de "Cap de Vendes" . Utilitza el codi de feina "SA_MAN".

```JSON
db.empleats.find({"$and": [{"pct_comissio": {"$exists": true}}, {"feina.codi": "SA_MAN"}]})
```

13. Recupera els empleats que han tingut 2 feines. No tinguis en compte la feina
actual.

```JSON
db.empleats.find({"historial_feines": {"$size": 2}})
```