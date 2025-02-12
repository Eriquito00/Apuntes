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

