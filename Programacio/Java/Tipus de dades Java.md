# Tipus de dades Java
Java es keysensitive, aixo vol dir que ens detecta com que "nom" "Nom" i "NOM" son diferents.
## Numeriques
### Enters
byte
- Aquest tipus pot guardar numeros enters entre 0 i 255.

short
- Aquest tipus pot guardar valors numerics entre -32000 i 32000

int
- Aquest tipus pot guardar valors numerics entre -2000000000 i 2000000000. Es el mes utilitzat.

long
- Aquest tipus pot guardar valors numerics encara mes grans que tots els anteriors.
### Decimals
float
- Aquest tipus pot guardar valors numerics amb decimals amb precicio de aproximadament 7 decimals.
IMPORTANT, si tenim una variable float declarada encara que sigui float al posar el punt decimal donara error per tant s'haura de fer el seguent:
`float a = 0.1f;` //la f es per confirmar que es float y que no sigui error
double
- Aquest tipus pot guardar valors numerics amb decimals amb precicio de aproximadament 15 decimals.
Si volem guardar un valor mes gran a un tipus de valor mes petit per exemple un long a un int o a altre mes petit, podem fer-ho de la seguent forma:
`int a = 2;`
`long b = 1;`
`a = (int) b;`
## Text
char
- Guarda un valor de text.

string
- Guarda un valor de tipus text.
Si volem comparar dos strings es ha dir comprovar si un string es igual a un altre utilitzarem ".equals()".
s1.equals(s2);
## Array
array
- int [] a = {1,2,3} //amb valors nomes declararla
- int [] a = new int [3] //amb la longitud que tindra
- si li diem que te 3 de longitud no podra tenir ni mes ni menys
- si li diem que tindra int han de ser tots els valors de tipus int
## Funcions
NO retorna valor
- crearem una funcio que contingui void, com aqui:

	![](/Imatges/Pasted%20image%2020241209113824.png)

retorna valor
- li direm el tipus de valor que retorna com aqui:

	![](/Imatges/Pasted%20image%2020241209114241.png)
## Precedència dels operadors
Si no es posen parèntesis, les operacions s'executen en el següent ordre:
1. Operadors unaris (signe -, increment ++, decrement --)
2. Multiplicació, divisió i residu (\*, /, %)
3. Suma i resta (+, -)
4. Relacionals (<, >, <=, >=, \== **PER STRINGS ".equals()"**, !=, 
5. Lògics (!, &&, ||)
## Conjunts de dades
### Set
#### HashSet
Serveix per emmagatzemar objectes no repetits. Pot contenir un objecte nul com a màxim.
Algunes de les operacions que es poden fer són:
- add(e): afegeix un element, si no hi és.
- remove(o): elimina l'objecte, si hi és.
- clear(): elimina tots els elements.
- contains(o): comprova si conté l'objecte.
- isEmpty(): comprova si no conté cap element.
- size(): obté el nombre d'elements que conté.
- toArray(): retorna un array amb tots els objectes.
### List
#### ArrayList
Permet emmagatzemar objectes repetits i nulls. Afegir i eliminar elements (especialment entre altres elements) és més costós que amb **LinkedList**.
A part de les operacions típiques de les col·leccions, es poden utilitzar les següents:
- add(ndx,e): insereix un elementen la posició ndx.
- set(ndx,e): canvia l'element de la posició ndx per l'elementen e.
- get(ndx): retorna l'element que es troba en la posició ndx.
- indexOf(e): retorna la primera posició en què es troba l'element e.
#### LinkedList
Implementa les interfícies **List** i **Queue** (de fet, implementa **Deque**, que permet afegir i eliminar elements tant al principi com al final de la cua).
Algunes operacions especials d'aquesta classe són:
- addFirst(e): afegeix l'element al principi de la llista.
- addLast(e): afegeix l'element al final de la llista.
- add(e): afegeix l'element al final de la llista.
- getFirst(): retorna el primer element de la llista.
- getLast(): retorna l'últim element de la llista.
- get(ndx): retorna l'element de la posició ndx.
- removeFirst(): retorna **i elimina** el primer element de la llista (genera excepció si llista buida).
- removeLast(): retorna **i elimina** l'últim element de la llista (genera excepció si llista buida).
- remove(ndx): retorna **i elimina** l'element de la posició ndx (genera excepció si llista buida).
### Map
#### HashMap
És similar a un diccionari: serveix per emmagatzemar objectes identificats per una clau. Totes les claus han de ser diferents i només pot haver-hi una que sigui nul·la.  
En canvi, els objectes de les diferents claus sí que poden ser nuls o estar repetits.
- put(key,value): afegeix una clau i l'element associat.
- get(key): obté l'element associat a la clau.
- remove(key): elimina la clau i l'element associat.
- clear(): elimina totes les claus i els elements associats.
- containsKey(key): comprova si existeix la clau.
- containsValue(value): comprova si existeix l'objecte.
- isEmpty(): comprova si no conté cap element.
- size(): obté el nombre d'elements que conté.
- keySet(): retorna un **Set** amb les claus del **HashMap**.
- values(): retorna un **Set** amb els elements del **HashMap**.