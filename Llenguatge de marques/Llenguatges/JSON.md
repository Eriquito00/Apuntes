# JSON
JavaScript Object Notation. Format molt senzill basat en JavaScript, funciona per clau - valor i podem crear claus de format array que contingui varis valors, boleans, objectes...

```JSON
{
	"alumnes": [
		{
			"nom": "Iker",
			"edat": 18,
			"beca": true,
			"notes":[8,7,7,9,8]
		},
		{
			"nom": "David",
			"edat": 18,
			"beca": true,
			"notes":[9,6,8,9,10]
		}
	]
}
```

Aqui podem veure que tenim dades dels seguents tipus:
- String: Amb el nom del alumne.
- Int: Amb la edad del alumne
- Bolea: Amb si te o no te beca l'alumne.
- Array: Amb totes les notes del nostre alumne.
- Objectes: Que com podem veure cada alumne es un objecte.
- Array d'Objectes: L'array Alumnes es una array amb la informacio de varis alumnes.

Tambe igual que XML tenim validadors de JSON com per exemple el [JSD](./Validadors%20JSON/JSD.md).