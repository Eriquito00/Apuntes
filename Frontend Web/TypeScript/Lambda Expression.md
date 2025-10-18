# Lambda Expression
Per fer funcions lambda podem ferles de la seguent forma.
```TS
(valor) => 2 * valor;
```

Les funcions lambda es poden fer tambe amb les funcions de [Metodes de Arrays](Metodes%20de%20Arrays.md). Aqui tenim un exemple amb sort per ordenar de gran a petit alfabeticament per nom els objectes.

```TS
const alumnes = [
	{nom: "Eric", edat: 19}, 
	{nom: "David", edat: 19}, 
	{nom: "Iker", edat: 18}
];

alumnes.sort((a1, a2) => a1.nom.localeCompare(a2.nom));
```

Tambe podem aplicar per numeros, ja que es just el que la funcio sort no pot ordenar correctament.

```TS
const numeros = [15, 2, 18, 40, 50, 36];

numeros.sort((n1, n2) => n1 - n2);
```