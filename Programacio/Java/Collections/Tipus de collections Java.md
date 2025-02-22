# Tipus de collections
Les collections serveixen per emmagatzemar un grup d'objectes, hi n'hi han de varios tipus com els seguents:

![](../../../Imatges/Pasted%20image%2020250222125844.png)
## List
Permet emmagatzemar de forma sequencial, tal cual com a una array, aixi es com ho fa ArrayList i a mes a mes totes le funcions que podem aplicar a ArrayList podem aplicarli a LinkedList.
### ArrayList i LinkedList
Es similar a una array pero que no te una longitud limitada, per tant podem utilitzarla per emmagatzemar dades sense limit.

- add("pos",element): insereix una dada a la arraylist a la posicio determinada.
- set("pos",element): canvia l'element en la posicio determinada per l'element.
- get("pos"): retorna l'element a la posicio determinada.
- remove("pos"): Esborraria l'element a la posicio determinada.
- clear(): elimina tots els elements.
- size(): retorna la longitud.
- indexOf(element): retorna la primera posicio on es troba l'element si no el troba retorna -1.

Un exemple de arrayList seria la seguent:

```JAVA
//Importacio de la llibreria
import java.util.ArrayList;
ArrayList<String> cars = new ArrayList<String>();

//import java.util.LinkedList;
//LinkedList<String> cars = new LinkedList<String>();

//add
cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");
cars.add("Mazda");

//set
cars.set(0,"Opel"); //Cambiaria "Volvo" per "Opel"

//get
cars.get(2); //Retornaria "Ford"

//remove
cars.remove(3); //Eliminaria "Mazda"

//clear
cars.clear(); //Deixaria la ArrayList buida

//size
cars.size(); //Retornaria 4 que es la longitud de la ArrayList

//indexOf
cars.indexOf("Volvo"); //Retornaria 0 ja que esta a la posicio 0
```

---
## Dueque i Queue
A mes a mes de les Array list tenim Queue i Deque que permeten emmagatzemar en una llista objectes pero que funcionen com una cua, Tenim com a Deque i Queue a LinkedList que ens dona les dues utilitats:
### LinkedList com Queue
LinkedList funciona exactament igual que ArrayList pero te algunes funcions extres, tot i aixo ArrayList s'utilitza mes i es mes eficient, les seguents funcions son per poder utilitzar LinkedList com Queue.

- offer(): afegeix un element al final de la cua
- peek(): retorna el primer element de la cua sense eliminarlo.
- poll(): elimina i retorna el primer element de la cua

```JAVA
//Importacio de la llibreria
import java.util.LinkedList;
LinkedList<String> cars = new LinkedList<String>();

cars.offer("Volvo");
cars.offer("Mercedes");
cars.offer("Bmw");

cars.peek(); //Retorna "Volvo"

cars.poll(); //Elimina "Volvo"
```
### LinkedList com Deque
LinkedList funciona exactament igual que ArrayList pero te algunes funcions extres, tot i aixo ArrayList s'utilitza mes i es mes eficient, les seguents funcions son per poder utilitzar LinkedList com deque.

- addFirst(): afegeix el item al inici de la llista.
- addLast(): afegeix el item al final de la llista.
- removeFirst(): elimina el item al inici de la llista.
- removeLast(): elimina el item al final de la llista.
- getFirst(): retorna el item al inici de la llista.
- getLast: retorna el item al final de la llista.

```JAVA
//Importacio de la llibreria
import java.util.LinkedList;
LinkedList<String> cars = new LinkedList<String>();

//add
cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");
cars.add("Mazda");

//addFirst
cars.addFirst("Opel"); //Afegiria abans de "Volvo" "Opel"

//addLast
cars.addLast("Audi"); //Afegiria despres de "Mazda" "Audi"

//removeFirst
cars.removeFirst(); //Eliminaria "Volvo"

//removeLast
cars.removeLast(); //Eliminaria "Mazda"

//getFirst
cars.getFirst(); //Retornaria "Volvo"

//getLast
cars.getLast(); //Retornaria "Mazda"
```

---
## Set
Permet emmagatzemar una col·leccio d'objectes sense repeticions. Aquest nomes utilitzarem HashSet:
### HashSet
S'utilitza per emmagatzema objectes NO REPETITS.

- add(element): afegeix l'element si no hi es.
- remove(element): elimina l'element si hi es.
- clear(): elimina tots els elements.
- contains(element): comprova si conte o no l'element.
- isEmpty(): comprova si esta buit.
- size(): retorna la longitud.
- toArray(): retorna un array amb tots els objectes.

```JAVA
//Importacio de la llibreria
import java.util.HashSet;
HashSet<String> cars = new HashSet<String>();
//add
cars.add("Volvo");
cars.add("BMW");
cars.add("Ford");
cars.add("BMW");
cars.add("Mazda");

//remove
cars.remove("Volvo"); //esborrara "Volvo"

//clear
cars.clear(); //deixa el HashSet buit

//contains
cars.contains("Ford"); //True o False segons si esta o no esta

//isEmpty
cars.isEmpty(); //retorna True o False si esta buida o no

//size
cars.size()); //retorna la longitud

//toArray
Object[] array = cars.toArray(); //transforma el hashset a una array d'objectes
```

---
## Map
Permet emmagatzemar objecte amb format clau - valor per localitzarlos, la clau ha de ser unica per cada objecte. Per map nomes utilitzarem HashMap.
### HashMap
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

```JAVA
import java.util.HashMap;
HashMap<String, String> cars = new HashMap<String, String>(); 
//put
cars.put("1234ABC", "Volvo");
cars.put("5678DEF", "BMW");
cars.put("9101GHI", "Ford");
cars.put("1121JKL", "Mazda");

//get
cars.get("5678DEF"); //retonaria "BMW"

//remove
cars.remove("9101GHI"); //esborrara "Ford"

//containsKey
cars.containsKey("1234ABC"); //retornara True o False si existeix o no existeix

//containsValue
cars.containsValue("Mazda"); //retornara True o False si existeix o no existeix

//isEmpty
cars.isEmpty(); //retornara True o False si esta o no esta buit

//size
cars.size(); //Retornara la longitud

// keySet
Set<String> claus = cars.keySet(); //Retornara totes les claus

//values
Collection<String> valors = cars.values(); //Retornara tots els valors

//clear
cars.clear(); //deixara el HashMap buit
```

---