# Tipus de dades de TS

TypeScript es resumidament JavaScript tipat per tant te tipus de dades que podem posar a les variables o constants, podem utilitzar els seguents:
- String
- Number
- Boolean
- Any (qualsevol)
- null
- undefined

Y se declaren de la seguent manera:
```TS
let variable: number = 2;

const CONSTANT:string = "Hello World!";
```

Pero TS tambe ens permet un us encara mes utilitari que es poder tenir una variable que pugui contenir valors de dos tipus de dades, obviament no a l'hora, que es pot fer de la seguent manera:

```TS
type strnum = string | number;

let variable: strnum;
```

D'aquesta manera podem fer que a qualsevol variable o constant que li posem aquest "type" pugui contenir tant "string" com "number".

## GetElementById
Com TS es tipat no ens permet agafar les dades com es fa a JS si no que canvia una mica perque ens permeti per exemple agafar un "value", en JS es fa de la seguent forma i dona igual si tenim un "div" un "input" o la etiqueta que sigui.

```JS
const div = document.getElementById("soydiv");

const input = document.getElementById("soyinput");
```

Amb TS si que importa si es un "div" o un "input" per tant ens exigeix, depenent del us que fem, el seguent:

```TS
const div = document.getElementById("soydiv") as HTMLDivElement;

const input = document.getElementById("soyinput") as HTMLInputElement;
```
## Operadors ! i ?
Aquests operadors fan una mica la mateixa funcio que quan els utilitzem de normal, basicament aseguren o posen en dubte el fet de que la variable sigui null o undefined, en un cas practic seria:

### !
Aqui podem veure un exemple utilitzant el operador "!" el qual asegura a TS que aquesta variable no es ni null ni undefined.

```TS
// Interpreta que "h" podria ser null i ens dona error
let h = document.getElementById("hello");  
h.innerHTML = "Hola";

// Asegurem que "h" no es null i no dona error
h!.innerHTML = "Hola";
```

### ?
Amb aquest operador podem fer dues coses, una seria per treure un valor o altre en cas de que sigui null o undefined, creant el fet com a que si es null o undefined "no pasa res" i podem treure altre valor, un exemple seria:

```TS
type Direccio {
  carrer: string;
  ciutat: string;
}

type Usuari {
  nom: string;
  direccio?: Direccio;
}

const usuari1: Usuari = { nom: "Anna" };
const usuari2: Usuari = { nom: "Lluis", direccio: { carrer: "Major 10", ciutat: "Barcelona" } };

console.log(usuari1.direccio?.carrer);
console.log(usuari2.direccio?.carrer);
```

Tambe podem aplicar-ho a permitir que algun parametre de la funcio sigui opcional i que no salti error. Un exemple seria:

```TS
type Usuari {
	nom: string;
	edad: number;
	direccio?: string;
}

function crearUsuari(nom: string, edad: number, direccio?: string){
	return {nom, edad, direccio}
}

const u1 = crearUsuari("Anna", 25);
const u2 = crearUsuari("Pau", 30, "Carrer Major 5");
```