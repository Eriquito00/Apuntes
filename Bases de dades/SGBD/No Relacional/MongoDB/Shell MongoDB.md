# Shell MongoDB
MongoDB té una Shell, basada en JavaScript que permet l'estructura de JavaScript, ara mirarem unes comandes amb la Shell de MongoDB per utilitzar la base de dades.

## Crear bases de dades, collections i imports
Després de descarregar les MongoDB tools command database line podem importar de la següent manera.

- Executarem amb l'arxiu d'import i posarem la bbdd, collection i primer insert a la bbdd amb la següent comanda al CMD.

```JSON
(ruta a mongoimport.exe) --db=(nom bbdd) --collection=(nom collection) --file=(primer fitxer).json
```

- Crear una collection

```JSON
db.createCollection("nombre")
```
## Comandes senzilles amb Mongosh

- Canviar de bbdd

```JSON
use (nom bbdd)
```

- Mostrar les bases de dades o collections

```JSON
//BBDD
show databases

//Collections
show collections
```

- Mostrar un fitxer o diversos fitxers d'una collection

```JSON
//Un fitxer
db.(collection).findOne()

//Els fitxers que trobi
db.(collection).find()
```

- Inserir un JSON amb valors clau - valor o varis

```JSON
//Un insert de json
db.(collection).insertOne({"clau": "valor"})

//Un insert de varios json
db.alumnes.insertMany([{"name":"David", "surname":"Catalan", "mitja":8.5}, {"name":"Eric", "surname":"Mejias", "mitja": 7.2}])
```

- Conta el nombre de documents que té la collection, aquest es pot fer de dues formes, però el resultat és el mateix.

```JSON
db.(collection).countDocuments()

db.(collection).find().count()
```

- Obté els resultats limitant només a cert nombre de resultats.

```JSON
db.departaments.find().limit(limite)
```

- Mostrar els resultats d'una forma mas ordenada i estructurada.

```JSON
db.departaments.find().pretty()
```
## Find
Tenim per exemple els següents operadors per poder obtenir alguns valors amb algunes condicions.
- $or: un valor o altre

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]})
```

- $and: els dos valors

```JSON
db.alumnes.find({"$and":[{"name":"David"},{"salari":1300}]})
```

- $lt: més petit que o $lte més petit que o igual

```JSON
db.alumnes.find({"edad": {"$lt": 18}})
```

- $gt: més gran que o $gte més gran o igual

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

- $size: comprovar el nombre de resultats 

```JSON
db.alumnes.find({"email": {"$size": 2}})
//retornaria els que tinguin 2 emails
```

- \$regex: permet posar regex. També podem posar després del regex "i" \/@gmail.com$/i perquè ignori majúscules i minúscules.

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

També tenim alguns paràmetres per només mostrar alguna de les dades dels JSON que volem, només haurem de fer una modificació al find. En podem posar 1 per les claus que volem mostrar i 0 per les que no volem mostrar.

```JSON
db.alumnes.find({"$or":[{"name":"David"},{"name":"Eric"}]}, {"name":1,"_id":0})
```
## Aggregation Framework
### $match
Gràcies a match podem utilitzar-ho com un where a MySQL, bàsicament ens és útil per poder fer un filtre sobre les dades del JSON.

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
Project és el que utilitzem per mostrar les dades que necessitem, és a dir si només volem veure el nom i cognoms per exemple.

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

### $addFields
Per mostrar totes les dades de cada fitxer i afegir algun camp que ens interessi o modificar algun camp només a l'hora de mostrar per mostrar els valors d'una forma més clara.

```JSON
db.empleats.aggregate([
  {
		"$addFields": {
			"salari": {"$multiply": ["$salari", 2] }
		}
	}
])
```

En aquest exemple em retornaria tota la informació del JSON intercanviant el valor de salari per aquest valor que li dono a salari, però només per mostrar no es canviarà als JSON.
### $count
Ens donarà un recompte dels resultats que compleixen les condicions anteriors com a l'exemple.

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

Aquí em retornarà un recompte dels empleats que en cobren menys de 2000.
### $sort
Ens serveix per treure els nostres resultats ordenats mitjançant una condició, es pot ordenar ascendent o descendent utilitzant 1 o -1.

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

Aquí ens mostraran les persones amb el seu salari de forma ascendent.
### $sample
Ens serveix per obtenir un nombre de documents com a resultat. Així podem obtenir només uns resultats.

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

### $skip
Skip es pot utilitzar per treure cert nombre de resultats a l'inici, així podem treure resultats per inici.

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
		"$skip": 2
	}
])
```
### $group
El grup en serveix per fer agrupaments amb les nostres dades per poder obtenir certs resultats agrupats per un camp.

```JSON
db.empleats.aggregate([
{
  $group:{
  	"_id": "$departament.codi",
  	"salari_max": {$max: "$salari"}
  }
}
]).sort(
{
	"salari_max": -1
}
)
```

Aquí ens donarà una suma de salaris agrupat per cada departament.
### Operadors
- $multiply: multiplica dos valors.

```JSON
db.empleats.aggregate([
  {
		"$project": {
			"nom": 1,
			"cognoms": 1,
			"salari": 1,
			"salari_brut": {"$multiply": ["$salari",1.1]}
		}
	}
])
```

- $divide: divideix dos valors.

```JSON
db.empleats.aggregate([
	{
		"$project": {
			"nom": 1,
			"cognoms": 1,
			"salari": 1,
			"salari_brut": {"$divide": ["$salari",1.1]}
		}
	}
])
```

- $avg: calcula una mitjana

```JSON
db.empleats.aggregate([
  {
		"$group": {
			"_id": "$departament.nom",
			"mitjana": {$avg: "$salari"}
		}
	}
])
```

- $max: retorna el màxim

```JSON
db.empleats.aggregate([
  {
		"$group": {
			"_id": "$departament.nom",
			"max": {$max: "$salari"}
		}
	}
])
```

- $min: retorna el mínim

```JSON
db.empleats.aggregate([
  {
		"$group": {
			"_id": "$departament.nom",
			"min": {$min: "$salari"}
		}
	}
])
```

- $sum: retorna la suma d'unes dades

```JSON
db.empleats.aggregate([
  {
		"$group": {
			"_id": "$departament.nom",
			"sum": {$sum: "$salari"}
		}
	}
])
```

### Condicional
Per poder afegir un condicional perquè el programa faci una cosa o altra segons una condició podem aplicar un condicional com el següent.

```JSON
db.empleats.aggregate([
	{
	    "$project": {
		    "nom": 1,
		    "cognoms": 1,
		    "salari": 1,
		    "salari_modificat": {
		        "$cond": {
		          "if": { "$lt": ["$salari", 3000] },
		          "then": "baixa pasta",
		          "else": "alta pasta"
		        }
		    }
	    }
	}
])
```

Amb aquest condicional en cas que el salari sigui inferior a 3000 treure "baixa pasta" i si és superior o igual treure "alta pasta".