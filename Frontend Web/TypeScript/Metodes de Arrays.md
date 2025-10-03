# Metodes de Arrays
Les array a TypeScript tenen metodes que podem utilitzar per reduir molt de codi o fer un codi mes eficient a l'hora de tractar dades de una array.
## ForEach
Foreach funciona com un for of pero foreach va enllaçat a una funcio, un exemple de foreach seria el seguent.

```TS
let cicles = ["SMX", "ASIX", "DAW"];

function escriu(valor, index, array){
	console.log(valor);
}

cicles.forEach(escriu);
```

## Map
Map basicament retorna una array "duplicada" de les dades de la array original pero despres de haber fer per exemple una operacio matematica.

```TS
let numeros = [1, 2, 3];  
  
function doble(valor, index, array) {
  return 2 * valor;  
}  
  
let n2 = cicles.map(doble); // valor actual de n2 = [2, 4, 6];
```

## Filter
Filter basicament com el nom indica ens aplica un filtre a la array de forma que podem obtenir nomes les dades que superin x condicio com al exemple seguent. Pero sempra haura de retornar true o false.

```TS
let edats = [10, 20, 30];
  
function major(valor, index, array) {
  return valor >= 18;  
}  
  
let m18 = edats.filter(major);   // el valor actual de m18 = [20, 30];
```

ForEach, map i filter podem passarli el mateix valor, el index al qual es trovaba el valor i la mateixa array sobre la que estem aplicant el metode.
## reduce i reduceRight
Reduce i reduceRight fan exactament el mateix nomes que un comença per l'inici de la array i l'altre del final.

```TS
let numeros = [1, 2, 3];  
  
function suma(anterior, actual) {
  return anterior + actual;
}

let t = numeros.reduce(suma, 0);   // t = 6
```

En aquest cas suma en ordre 1 + 2 + 3.

```TS
let numeros = [1, 2, 3];  
  
function suma(anterior, actual) {
  return anterior + actual;
}

let t = numeros.reduceRight(suma, 0);   // t = 6
```

En aquest cas sumaria al reves 3 + 2 + 1.
## every i some
Aquests dos funcionen com filter es per mirar si tots els valors d'una array compleixen una condicio o si alguns valors compleixen una condicio.

```TS
let numeros = [1, 2, 3];  
  
function imparell(valor) {
  return valor % 2;  
}  
  
let i = numeros.every(imparell);
i = numeros.some(imparell);
```