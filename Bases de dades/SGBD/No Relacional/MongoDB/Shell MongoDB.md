# Shell MongoDB
MongoDB te una shell, basada en JavaScript que permet la estructura de JavaScript, ara mirarem unes comandes amb la shell de mongodb per utilitzar la base de dades.

## Comandes senzilles amb Mongosh

- Crear una collection

```SHELL
db.createCollection("nombre")
```

- Mostrar les bases de dades o collections

```SHELL
//BBDD
show databases

//Collections
show collections
```

- Mostrar un fitxer o varis fitxers d'una collection

```SHELL
//Un fitxer
db.(collection).findOne()

//Els fitxers que trobi
db.(collection).find()
```

- Insertar un json con valores clave valor o varios

```SHELL
//Un insert de json
db.(collection).insertOne({"clau": "valor"})

//Un insert de varios json
db.alumnes.insertMany([{"name":"David", "surname":"Catalan", "mitja":8.5}, {"name":"Eric", "surname":"Mejias", "mitja": 7.2}])
```

- Conta el numero de documents que te la collection, aquest es pot fer de dues formes pero el resultat es el mateix

```SHELL
db.(collection).countDocuments()

db.(collection).find().count()
```

- Obte els resultats limitant nomes a cert numero de resultats.

```SHELL
db.departaments.find().limit(limite)
```

- Mostrar els resultats de una forma mas ordenada i estructurada.

```SHELL
db.departaments.find().pretty()
```
## Find
Tenim per exemple els seguents operadors per poder obtenir alguns valors amb algunes condicions.
- $or: un valor o altre

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]})
```

- $lt: mes petit que o $lte mes petit que o igual

```JSON
db.alumnes.find({"edad": {"$lt": 18}})
```

- $gt: mes gran que o $gte mes gran o igual

```JSON
db.alumnes.find({"edad": {"$gt": 18}})
```

- $eq: igual que

```JSON
db.alumnes.find({"edad": {"$eq": 20}})
```

- $ne: no igual que

```JSON
db.alumnes.find({"edad": {"$ne": 18}})
```

Tambe tenim alguns parametres per nomes mostrar alguns de les dades dels json que volem, nomes haurem de fer una modificacio al find. Podem posar 1 per les claus que volem mostrar i 0 per les que no volem mostrar.

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]}, {"name":1,"_id":0})
```