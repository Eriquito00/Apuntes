# Objectes de TypeScript
A TypeScript podem utiltzar Objectes igual que a altres llenguatges pero amb unes millores respecte a JavaScript. La creacio de Objectes a TS es fan de la seguent manera:

```TypeScript
const persona = {
	nom: "Manolo",
	edat: 19,
	casat: false
}
```

Tambe podem crear objectes amb dades predefinides, per aixi obligar a que les dades de la clau definida siguin d'un tipus especific.

```TypeScript
const persona: {nom:string, edat:number, casada:boolean} = {
	nom: "Manolo",
	edat: 19,
	casat: false
}
```

## Tipus de objectes
Per crear un tipus d'objecte com el tipus string o el tipus number podem crear un tipus de objecte com per exemple objecte Persona.

```TS
type Persona = {  
	nom: string,  
	edat: number,  
	casada: boolean
};  
  
const persona1: Persona = { nom: "Mary", edat: 25, casada: false };  
const persona2: Persona = { nom: "Peter", edat: 35, casada: true };
```

El fet de utilitzar type o interface va segons el programador de TypeScript pero si que es veritat que es solen utilitzar per:
- type: definicions de restriccions a objectes.
- interface: definicions a restriccions a funcions.

Tambe igual que les arrays podem crear objectes amb algun atribut nomes de lectura, molt util quan algun objecte conte alguna ID que no ens interesa que canvi mai.

```TS
type Persona = {  
	readonly nom: string,  
	edat: number,  
	casada: boolean  
};
```

Tambe com podem crear types posem el cas que tenim Persona i tenim Robot i una fusio entre els dos que seria un Cyborg ens interesa que tingui els atributs dels dos, aixo podem fer-ho a TS de la seguent manera.

```TS
type Persona = {  
	nom: string,  
	edat: number  
};  
  
type Robot = {  
	identificador: number,
	super: boolean
};  
  
type Cyborg = Persona & Robot;  
  
const franky: Cyborg = {  
	nom: "Franky",  
	edat: 199,  
	identificador: 74312630,  
	super: true
};
```