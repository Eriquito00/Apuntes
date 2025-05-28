# Shell MongoDB
MongoDB te una shell, basada en JavaScript que permet la estructura de JavaScript, ara mirarem unes comandes amb la shell de mongodb per utilitzar la base de dades.

## Crear bases de dades, collections i imports
Despres de descarregar les MongoDB tools command database line podem importar de la seguent manera.

- Executarem amb l'arxiu de import i posarem la bbdd, collection i primer insert a la bbdd amb la seguent comanda al CMD.

```JSON
(ruta a mongoimport.exe) --db=(nom bbdd) --collection=(nom collection) --file=(primer fitxer).json
```

- Crear una collection

```JSON
db.createCollection("nombre")
```
## Comandes senzilles amb Mongosh

- Mostrar les bases de dades o collections

```JSON
//BBDD
show databases

//Collections
show collections
```

- Mostrar un fitxer o varis fitxers d'una collection

```JSON
//Un fitxer
db.(collection).findOne()

//Els fitxers que trobi
db.(collection).find()
```

- Insertar un json con valores clave valor o varios

```JSON
//Un insert de json
db.(collection).insertOne({"clau": "valor"})

//Un insert de varios json
db.alumnes.insertMany([{"name":"David", "surname":"Catalan", "mitja":8.5}, {"name":"Eric", "surname":"Mejias", "mitja": 7.2}])
```

- Conta el numero de documents que te la collection, aquest es pot fer de dues formes pero el resultat es el mateix

```JSON
db.(collection).countDocuments()

db.(collection).find().count()
```

- Obte els resultats limitant nomes a cert numero de resultats.

```JSON
db.departaments.find().limit(limite)
```

- Mostrar els resultats de una forma mas ordenada i estructurada.

```JSON
db.departaments.find().pretty()
```
## Find
Tenim per exemple els seguents operadors per poder obtenir alguns valors amb algunes condicions.
- $or: un valor o altre

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]})
```

- $and: els dos valors

```JSON
db.alumnes.find({"$and":[{"name":"David"},{"salari":1300}]})
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

- $in: entre algun dels valors

```JSON
db.alumnes.find({"edad": {"$in": [18,21,25]}})
```

- $nin: no estigui en algun dels valors

```JSON
db.alumnes.find({"edad": {"$nin": [18,21,25]}})
```

- $exists: existeixi el camp o no

```JSON
db.alumnes.find({"edad": {"$exists": false | true}})
```

- $size: comprovar el numero de resultats 

```JSON
db.alumnes.find({"email": {"$size": 2}})
//retornaria els que tinguin 2 emails
```

- \$regex: permet posar regex. tambe podem posar despres del regex "i" \/@gmail.com$/i perque ignori majuscules i minuscules.

```JSON
//simplificat
db.alumnes.find({"email": /@gmail.com$/})

//sense simprificar
db.alumnes.find({"email": {"$regex": /@gmail.com$/}})
```

- $sort: ordena els resultats

```JSON
db.users.find({"edad": {$gt: 18}}).sort({"edad": 1})
```

- $toArray: transformar a array

```JSON
db.users.find({"edad": {$gt: 18}}).toArray()
```

Tambe tenim alguns parametres per nomes mostrar alguns de les dades dels json que volem, nomes haurem de fer una modificacio al find. Podem posar 1 per les claus que volem mostrar i 0 per les que no volem mostrar.

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]}, {"name":1,"_id":0})
```
## Aggregation Framework
### $match
Gracies a match podem utilitzar-ho com un where a mysql, basicament ens es util per poder fer un filtre sobre les dades del json.

```JSON
db.empleats.aggregate([
  {
		"$match": {
			"salari": {"$eq": 1300}
		}
	}
])
```

### \$project
Project es el que utilitzem per mostrar les dades que necesitem, es a dir si nomes volem veure el nom i cognoms per exemple.

```JSON
db.empleats.aggregate([
  {
		"$project": {
			"nom": 1,
			"cognoms": 1,
			"salari": 1,
			"salari_brut": {"$multiply": ["$salari", 2] }
		}
	}
])
```

### $addfields
Per mostrar totes les dades de cada fitxer i afegir algun camp que ens interesi o modificar algun camp nomes a l'hora de mostrar per mostrar els valors d'una forma mes clara.

```JSON
db.empleats.aggregate([
  {
		"$addFields": {
			"salari": {"$multiply": ["$salari", 2] }
		}
	}
])
```

En aquest exemple hem retornaria tota la informacio del JSON intercambiant el valor de salari per aquest valor que li dono a salari, pero nomes per mostrar no es cambiara als json.
### $skip
--
### $count
Ens donara un recompte dels resultats que compleixen les condicions anteriors com a l'exemple.

```JSON
db.empleats.aggregate([
	{
		"$match": {
    	"salari": {"$lt": 2000}
		}
	},
  {
		"$project": {
			"nom": 1,
			"salari_tot": {"$multiply": ["$salari", 1.1] }
		}
	},
  {
		"$count": "salaris_menors_2000"
	}
])
```

Aqui hem retornara un recompte dels empleats que cobren menys de 2000.
### $sort
Ens serveix per treure els nostres resultats ordenats mitjançant una condicio, es pot ordenar ascendent o descendent utilitzant 1 o -1.

```JSON
db.empleats.aggregate([
	{
		"$match": {
    	"salari": {"$lt": 2000}
		}
	},
  {
		"$project": {
			"nom": 1,
			"salari_tot": {"$multiply": ["$salari", 1.1] }
		}
	},
  {
		"$sort": {"salari_tot": 1}
	}
])
```

Aqui ens mostraran les persones amb el seu salari de forma ascendent.
### $sample
Ens serveix per obtenir un numero de documents com a resultat. Aixi podem obtenir nomes uns resultats.

```JSON
db.empleats.aggregate([
	{
		"$match": {
    	"salari": {"$lt": 2000}
		}
	},
  {
		"$project": {
			"nom": 1,
			"salari_tot": {"$multiply": ["$salari", 1.1] }
		}
	},
  {
		"$sample": {"size": 2}
	}
])
```
### $group
El group en serveix per fer agrupaments amb les nostres dades per poder obtenir certs resultats agrupats per un camp.

```JSON

```

### Operadors
- $multiply: multiplica dos valors.

```JSON

```

- $divide: divideix dos valors.

```JSON

```

- $avg: calcula una mitjana

```JSON

```

- $count: retorna el numero de documents d'un grup.

```JSON

```

- $max: retorna el maxim

```JSON

```

- $min: retorna el minim

```JSON

```

- $sum: retorna la suma d'unes dades

```JSON

```

### Condicional
Per poder afegir un condicional perque el programa faci una cosa o altre segons una condicio podem aplicar un condicional com el seguent.

```JSON

```