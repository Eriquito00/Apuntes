# Collections Java
## ArrayList
Es similar a una array pero que no te una longitud limitada, per tant podem utilitzarla per emmagatzemar dades sense limit.

- add("pos",element): insereix una dada a la arraylist a la posicio determinada.
- set("pos",element): canvia l'element en la posicio determinada per l'element.
- get("pos"): retorna l'element a la posicio determinada.
- indexOf(element): retorna la primera posicio on es troba l'element.

## HashSet
S'utilitza per emmagatzema objectes NO REPETITS.

- add(element): afegeix l'element si no hi es.
- remove(element): elimina l'element si hi es.
- clear(): elimina tots els elements.
- contains(element): comprova si conte o no l'element.
- isEmpty(): comprova si esta buit.
- size(): retorna la longitud.
- toArray(): retorna un array amb tots els objectes.

## HashMap
Es similar a un diccionari que serveix per emmagatzemar objectes identificats per una clau. Totes les claus han de ser diferent i nomes pot haver-hi una que sigui nula.

- put(key,value): afegeix una clau i l'element associat.
- get(key): obté l'element que te aquesta clau.
- remove(key): elimina l'element que te aquesta clau.
- clear(): elimina tots els elements.
- containsKey(key): comprova si existeix la clau.
- containsValue(value): comprova si existeix el valor.
- isEmpty(): comprova si esta buit.
- size(): retorna la longitud.
- keySet(): retorna un Set amb les claus del HashMap.
- values(): retorna un Set amb els valors del HashMap.