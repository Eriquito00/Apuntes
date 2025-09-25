# RRHH
## Base de dades Recursos Humans (RRHH)
Aquí tens la [collection de empleats](BBDD/empleats.json) i [collection de departaments](BBDD/departaments.json).

## Nivell 1

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

12. Recupera els empleats que tenen pct_comissio i hagi treballat o treballin actualment de "Cap de Vendes". Utilitza el codi de feina "SA_MAN".

```JSON
db.empleats.find({"$and": [{"pct_comissio": {"$exists": true}}, {"feina.codi": "SA_MAN"}]})
```

13. Recupera els empleats que han tingut 2 feines. No tinguis en compte la feina actual.

```JSON
db.empleats.find({"historial_feines": {"$size": 2}})
```

## Nivell 2

1. Mostra la quantitat d’empleats per cada departament. Mostra ID de departament i la quantitat.

```JSON
db.empleats.aggregate([
{
  $group:{
  	"_id": "$departament.nom",
  	"total": {$sum: 1}
  }
}
])
```

2. Si no ho has tingut en compte en l’exercici anterior. Només tingues en compte aquells empleats que estiguin en un departament.

```JSON
db.empleats.aggregate([
{
	$match:{
		"departament.nom": {$ne:null}
	}
},
{
	$group:{
		"_id": "$departament.nom",
		"total": {$sum: 1}
	}
}
])
```

3. Ordena el resultat anterior per els departament de més a menys nombre d’empleats.

```JSON
db.empleats.aggregate([
{
	$match:{
		"departament.nom": {$ne:null}
	}
},
{
  $group:{
  	"_id": "$departament.nom",
  	"total": {$sum: 1}
  }
}
]).sort(
{
	"total": -1
}
)
```

4. De cada departament mostra el salari més alt. Mostra ID de departament i el salari més alt.

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

5. Quina és la massa salarial de cada departament? Mostra ID de departament i la massa salarial.

```JSON
db.empleats.aggregate([
{
  $group:{
  	"_id": "$departament.codi",
  	"salaris": {$sum: "$salari"}
  }
}
]).sort(
{
	"salari_max": -1
}
)
```

6. Només mostra aquells departaments que tinguin una massa salarial igual o superior a 19000

```JSON
db.empleats.aggregate([
{
  $group:{
  	"_id": "$departament.codi",
  	"salaris": {$sum: "$salari"}
  }
},
{
	$match:{
		"salaris": {$gte: 19000}
	}
}
]).sort(
{
	"salari_max": -1
}
)
```

7. Volem comparar l'alçada dels dos germans Gasol. Els noms curts són "Pau Gasol" i "Marc Gasol".

```JSON
db.jugadors.find({"nom_curt": {$regex: "Gasol"}},{"nom_curt":1,"alcada":1})
```

8. L’entrenador “Pedro Martínez” és un dels entrenadors més veterans. Quants partits ha participat com a entrenador. Independentment de si ho ha fet com a local o com a visitant. Restringeix la consulta als partits de la Lliga Regular de la temporada 2023-2024.

```JSON
db.partits.aggregate([
{
	"$match": {
		"$and":[
		    {"competicio": {"$eq": "Lliga Regular"}},
		    {
				"$and": [
					{"temporada": {"$eq": "2023-2024"}},
					{
						"$or": [
							{"equip_local.entrenadors.nom": "Pedro Martínez"},
							{"equip_visitant.entrenadors.nom": "Pedro Martínez"}
						]
					}
				]
			}
		]
	}
},
{
	"$project": {
		"equip_visitant.entrenadors.nom":1,
		"equip_local.entrenadors.nom":1,
		"competicio":1,
		"temporada":1
	}
},
{
	"$count": "Pedros martinez"
}
])
```

9. La llicència "JFL" indica que és un jugador de formació. Quants jugadors tenim amb aquesta llicència?

```JSON
db.jugadors.find({"llicencia": {$eq: "JFL"}}).count()
```

10. Quins jugadors tenim el compte d'Instagram? Mostra el nom_curt del jugador i l'usuari d'Instagram

```JSON
db.jugadors.aggregate([
	{
		$unwind: "$xarxes_socials"
	},
	{
		$match: {
			"xarxes_socials.nom": "instagram"
		}
	},
	{
		$project: {
	      _id: 0,
	      nom_curt: 1,
	      usuari: "$xarxes_socials.usuari"
	    }
	}
])
```

11. Dona el nombre total de punts de l'equip local del partit amb codi_acb :"103778"

```JSON
db.partits.aggregate([
	{
		$match: {
			"codi_acb": "103778"
		}
	},
    {
		$project:{
			"punts": {$sum: "$equip_local.jugadors.estadistics.punts"}
		}
	}
])
```

12. Obtenir els punts de cada equip (local i visitant) del partit amb codi_acb: "103778"

```JSON
db.partits.aggregate([
    {
		$match: {
			"codi_acb": "103778"
		}
	},
    {
		$project:{
			"punts_local": {$sum: "$equip_local.jugadors.estadistics.punts"},
			"punts_visitant": {$sum: "$equip_visitant.jugadors.estadistics.punts"}
		}
	}
])
```