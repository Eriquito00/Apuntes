# Tipus de dades i Estructura MongoDB
## Tipus de dades
Els tipus de dades que podem utilitzar al JSON de MongoDB són les següents:
- int
- float
- boolean
- date
- string
- array
- null (o nan)
- objectes
- JSON
## Estructura
MongoDB treballa amb JSON, per tant, utilitza la seva mateixa estructura utilitzant clau - valor, per tant, podem utilitzar una estructura com el següent JSON.

```JSON
{
	"clau": "valor",
	"clau": 2,
	"clau": 2.2,
	"clau": [
		{
			"a": "valor"
		},
		{
			"b": "valor"
		}
	]
}
```