# Tipus de dades i Estructura MongoDB
## Tipus de dades
Els tipus de dades que podem utilitzar al json de MongoDB son les seguents:
- int
- float
- boolean
- date
- string
- array
- null (o nan)
- objectes
- json
## Estructura
MongoDB treballa amb JSONs per tant utilitza la seva mateixa estructura utilitzant clau - valor, per tant podem utilitzar una estructura com el seguent json.

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