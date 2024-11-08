## While
Aquestes estructures son estructures bucle o itinerades. Els bucles normalment no es necesita que siguin infinits per tant es posa una condicio i fins que no es compleix no surt del bucle.
![[Pasted image 20241001110558.png]]
S'utilitza per executar el mateix codi varies vegades pero sense sapiguer cuantes seran, per exemple:
![[Pasted image 20241001110821.png]]
En cas de que la primera vegada que s'arriba a while la condicio es falsa, no s'executara.
## Bucle infinit
Si que hi ha casos que ens surt millor fer un bucle infinit com per exemple:
![[Pasted image 20241001111006.png]]
## do while
![[Pasted image 20241001111054.png]]
Aques tipus de bucle si que s'executara minim una vegada i despres comprovara si la condicio es cumpleix. Tambe podem veure un exemple:
![[Pasted image 20241001111216.png]]
### Com utilitzar while
Podem utilitzar while quan volem que una dada sigui correcte:
![[Pasted image 20241001111501.png]]
Pero avegades ens es mes facil pensar quina condicio necesitem per sortir del bulce i la posem invertida com per exemple aqui:
![[Pasted image 20241001111612.png]]
Introduir dades fins que s'introdueixi un valor determinat, com en aquest exemple:
![[Pasted image 20241001111803.png]]
## For
![[Pasted image 20241004110654.png]]
Aquesta estructura de for es molt semblant a la estructura anterior while, de fet qualsevol bucle for es pot substituir per while. Per tant quan utilitzarem for i quan while:
- Utilitzarem **for** quan el codi s'hagi de repetir un numero determinat de vegades.
- Utilitzarem __while__ quan no sapiguem quantes vegades hem de repetir el codi.
## Modificar la sequencia d'un bucle
Per modificar la sequencia d'un bucle podem utilitzar diferents metodes.
Per exemple podem utilitzar break per trencar el bucle i sortir de forma inmediata, i s'utilitza normalment per trencar un bucle aparentment infinit.
![[Pasted image 20241007113425.png]]
Tambe tenim continue, que si es compleix la condicio deixa continuar el codi pero si no no es fa, aqui podem veure un exemple.
![[Pasted image 20241007113818.png]]
## For of
For of es una estructura de repeticio que es per simplificar la forma en la que es recorren les array. Aquests dos codis seguents fan el mateix:
for (let i of array){}
for (let i = 0; i < array.length; i++){}
Pero quan hem de fer coses dins d'una array es mes senzill y millor utilitzar for of de forma que cada vegada que es recorreix la array i es el valor de la posicio en la que es recorreix, es a dir, la primera vegada tindra el valor de la posicio 0 de la array, la segona tindra el valor de la posicio 1 y aixi fins l'ultim valor de l'array.