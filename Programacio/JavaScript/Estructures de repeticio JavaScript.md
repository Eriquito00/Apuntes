# Estructures de repetició JavaScript

## While

Aquestes estructures son estructures bucle o itinerades. Els bucles normalment no es necessita que siguin infinits per tant es posa una condició i fins que no es compleix no surt del bucle.

![](/Imatges/Pasted%20image%2020241001110558.png)

S'utilitza per executar el mateix codi diverses vegades però sense saber quantes seran, per exemple:

![](/Imatges/Pasted%20image%2020241001110821.png)

En cas de que la primera vegada que s'arriba a `while` la condició sigui falsa, no s'executarà.

## Bucle infinit

Si que hi ha casos que ens surt millor fer un bucle infinit com per exemple:

![](/Imatges/Pasted%20image%2020241001111006.png)

## do while

![](/Imatges/Pasted%20image%2020241001111054.png)

Aquest tipus de bucle sí que s'executarà mínim una vegada i després comprovarà si la condició es compleix. També podem veure un exemple:

![](/Imatges/Pasted%20image%2020241001111216.png)

### Com utilitzar `while`

Podem utilitzar `while` quan volem que una dada sigui correcta:

![](/Imatges/Pasted%20image%2020241001111501.png)

Però a vegades ens és més fàcil pensar quina condició necessitem per sortir del bucle i la posem invertida com per exemple aquí:

![](/Imatges/Pasted%20image%2020241001111612.png)

Introduir dades fins que s'introdueixi un valor determinat, com en aquest exemple:

![](/Imatges/Pasted%20image%2020241001111803.png)

## For

![](/Imatges/Pasted%20image%2020241004110654.png)

Aquesta estructura de `for` és molt semblant a la estructura anterior `while`, de fet qualsevol bucle `for` es pot substituir per `while`. Per tant quan utilitzarem `for` i quan `while`:
- Utilitzarem **for** quan el codi s'hagi de repetir un nombre determinat de vegades.
- Utilitzarem **while** quan no sapiguem quantes vegades hem de repetir el codi.

## Modificar la seqüència d'un bucle

Per modificar la seqüència d'un bucle podem utilitzar diferents mètodes. Per exemple, podem utilitzar `break` per trencar el bucle i sortir de forma immediata, i s'utilitza normalment per trencar un bucle aparentment infinit.

![](/Imatges/Pasted%20image%2020241007113425.png)

També tenim `continue`, que si es compleix la condició deixa continuar el codi però si no, no es fa. Aquí podem veure un exemple:

![](/Imatges/Pasted%20image%2020241007113818.png)

## For of

`For of` és una estructura de repetició que és per simplificar la forma en què es recorren les arrays. Aquests dos codis següents fan el mateix:

```javascript
for (let i of array) {}
for (let i = 0; i < array.length; i++) {}
```
