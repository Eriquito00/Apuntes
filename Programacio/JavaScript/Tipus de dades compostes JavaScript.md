# Array
### Crear, inicialitzar i eliminar
Les arrays son com uns trens de valors que contenen valors com les notes de 30 alumnes, en JS les arrays son dinamiques, es a dir, que podem definirla buida i anar omplenant de valors durant el codi.
\[] = array buida
\[DAW, DAM, ASIX] = array amb 3 valors
![[Pasted image 20241018083039.png]]
### Obtenir i modificar un element
Aqui podem veure un exemple utilitzant les arrays. Aqui podem veure que es defineix amb 2 valors i que el segon valor es modifica de DAW a DAM.
![[Pasted image 20241018082916.png]]
### Afegir i eliminar elements
Tambe podem afegir un valor a una posicio especifica de la array pero els valors anteriors quedaran buits. Empty no es el mateix que undefined
![[Pasted image 20241018083548.png]]
Algunes funcions que ens ajuden amb les arrays son els seguents:
- push(element): afegeix un element al final de la array.
- pop(): retorna l'ultim element de la llista i l'elimina.
- unshift(element): afegeix l'element al principi de la llista.
- shift(): retorna el primer element de la llista i l'elimina.
Tambe podem utilitzar concat() per juntar dues arrays com en el seguent exemple:
- contact(): podem juntar el valor d'una array a un altre.
![[Pasted image 20241018084017.png]]
# Arrays constants
El significant de const a una array evita que es modifiqui la array per una altre array pero si els valors que la contenen, podem donarli un nou valor a la posicio 2 de la array pero no podem assignarli un nou valor de una nova array, aqui podem veure un exemple:
![[Pasted image 20241018085308.png]]
### Assignacio d'arrays
Quan asignem un valor d'una array a una altre array en veritat no li estem donant directament el valor, es a dir, que si li cambiem un valor a la primera array el valor de la segona tambe es modifica, aqui podem veure un exemple:
![[Pasted image 20241018085953.png]]
## Metodes dels arrays
### Mostrar tots els elements de la array
Podem mostrar els valors per alert o console log i podem modificarho amb el join pero JS per defecte les separara nomes per una coma.
- join(): quan mostrem els valors per consola o per innerHTML els separa per l'element que li hem dit.
![[Pasted image 20241018091919.png]]
### Recorrer tots els elements d'un array
Podem recorrer una array podem buscar un valor i aqui podem veure un exemple buscant DAM a una array on estan tots els estudis del Sa Palomera.
![[Pasted image 20241018092143.png]]
### for ... of
Tambe podem utilitzar el for of que es per quan hem de recorrer tota la array per buscar un valor, per exemple per comptar tots els suspensos a una array de notes. O en aquest exemple que mostrem tots els estudis del Sa Palomera.
![[Pasted image 20241018092327.png]]
### Funcions per buscar elements dins d'un array
- includes(valor): retorna true si existeis el valor a la array.
- indexOf(valor): retorna l'index del primer element amb el valor valor. Tambe podem inicialitzar la posicio on volem que comenci.
- lastIndexOf(valor): igual que l'anterior per comença pel final.
- slice(inici, fi): genera una nova lista amb els elements entre inici (inclos) i fi (sense incloure).
- splice(): permet afegir o eliminar elements d'una array.
### Ordenar l'array
La comanda sort() ordena la array per ordre alfabetic de petit a gran. Amb els numeros els pasa a sting el que fa que faci que 30 sigui mes petit que 9 perque el 3 es mes petit que el 9.
- reverse(): inverteix la posicio de tots els elements, el primer a l'ultim, el segon al penultim i aixi amb tots.
- sort(): ordena la array alfabeticament de petit a gran.