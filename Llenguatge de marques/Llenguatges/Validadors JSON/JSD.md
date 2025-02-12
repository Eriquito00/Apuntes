# JSD
Igual que amb XML hem d'importar un "schema" de la seguent forma:

```JSD
{
	"$schema": "https://json-schema.org/draft/2020-12/schema",
	"type": "object"
}
```

Aqui tenim un exemple de JSON amb el seu respectiu JSD:

```JSON
{
	"$schema": "./esquema.jsd",
	"nom": "Iker",
	"edat": 18
}
```

```JSD
{
	"$schema": "https://json-schema.org/draft/2020-12/schema",
	"type": "object",
	"properties": {
		"nom": {"type": "string"},
		"edat": {"type": "integer", "minimum": 0}
	},
	"required": ["nom","edat"]
}
```

## Tipus de dades
- object: per objectes.
- string: per valors string.
- integer: per valors de tipus enter.
- boolean: per valors true o false.
- number: per valors de tipus numero amb decimals.
- array: per valors que son una array que conte valors.
## Altres tipus de valors
A part de dir si alguna clau - valor es d'algun tipus tambe podem establir limits de forma que siguin mes restrictius com el seguent:
- enum: s'utilitza per limitar les opcions.

```JSD
"enum": ["1","2","3",...]
```

- minimum i minItem: s'utilitza per establir un valor minim a una clau - valor o directament com a un atribut directament.

```JSD
// minimum
"valor": { "type": "integer", "minimum": 1 }
```

```JSD
// minItems
"habitacions": {
    "type":"array",
    "items": {
        "properties": {
            "tipus": {
	            "type": "string",
	            "enum": ["individual","doble","suite"]
            },
            "nombre_nits": {
                "type": "integer",
                "minimum": 1
            },
            "preu_per_nit": {
                "type": "number",
                "minimum": 1
            }
        }
    },
    "minItems": 1
}
```

- format: podem utilitzarlo per, per exemple que segueixi una estructura com un correu electronic.

```JSD
"email": {
    "type": "string",
    "format": "email"
}
```

- default: com la paraula diu es per establir un valor per defecte.

```JSD
"estat": {
    "type": "string",
    "enum": ["pendent","enviat","entregat","cancel·lat"],
    "default": "pendent"
}
```

- unique: perque aquest valor no es repeteixi amb els altres.

```JSD
"id_comanda": {
    "type": "integer",
    "minimum": 1,
    "unique": true
}
```

- pattern: per establir un regex.

```JSD
"data_registre": {
    "type": "string",
    "pattern": "^\\d{4}-\\d{2}-\\d{2}$"
}
```