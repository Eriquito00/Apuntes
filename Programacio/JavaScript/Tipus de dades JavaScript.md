# Simples
#### Valors simples
- **Números**: enters o decimals.
- **Text**: caràcters, dígits, altres símbols, paraules i frases.
- **Booleans**: si/no, vertader/fals...
#### Valors compostos
- **Dates**: 
- **Llistes**: 
- **Objectes**: 
### Literals
Els **literals** representen un valor que ja es coneix en el moment d'escriure el programa.  
No es guarden en memòria sinò que formen part del codi del programa.
- **Literals numèrics**: 2768, 12.59 o 3.45e3.
- **Literals de text**: "Hola", '74' o '@'.
- **Literals booleans**: true o false.

### Constants i variables
Les dades que necessita un programa es guarden a la memòria. Per reservar espai a la memòria, cal definir **constants** i **variables**. La diferència és que el valor que es guarda en una constant no es pot modificar posteriorment.
Els noms de les constants i variables han de seguir unes regles:
- Ha de ser una paraula (no pot contenir espais entre mig)
- Pot contenir números però no pot començar amb un número
- Pot començar amb guió baix (\_) o $ però, de moment, millor no utilitzar-los
- No pot ser una paraula reservada de JavaScript
- No pot contenir caràcters especials, excepte el guió baix
- Les majúscules i minúscules es consideren diferents (_case-sensitive_)
- Els noms de constants i variables han de ser significatius
##### Exemple de constant
Els noms de les constants es posaran en majúscules i, si contenen més d'una paraula, separades per guió baix.
const MAX_NOTA = 10;
##### Exemple de variable
Els noms de les variables el posaran en minúscules i, si contenen més d'una paraula, cada nova paraula es posarà amb la primera lletra majúscula (_camelCase_)
let notaAlumne = 7;
## Les constants
Normalment quan es comença a programar no s'utilitzen constants ja que normalment es posa el valor literal al codi encara que una constant seria mes util en cas de que en un futur canvï seria molt mes facil i rapid que hi hagues una constant.
El que normalment es fa:
![[Pasted image 20240923084131.png]]
El que s'hauria de fer:
![[Pasted image 20240923084159.png]]
### Avantatges d'utilitzar constants
- Utilitzar un nom ens dona mes informacio que un valor directament com "NOTA_MAX" i "10".
- Si cal canviar el valor nomes s'ha de fer alla on s'hagi declarat la constant, si es un valor s'haura de canviar a tots llocs on estigui.
- Pot ser que mes endavant s'hagi de canviar el valor o canviar per una variable, en cas d'utilitzar constant sera mes rapid i facil.
# Conversio i format de dades
## Conversio entre text i numeros
### De numero a text
Podem convertit tant fent:
- "" + valor
- variable.toString()
![[Pasted image 20240920084507.png]]
### De text a numero
Podem utilitzar un o altre segons per a que utilitzem el valor:
- parseInt()
- parseFloat()
Int sera per a numeros enters; 1, 2, 3.
Float per a numeros decimals; 1.1, 2.3 3.1.
![[Pasted image 20240920084723.png]]
**Si el text no conté un valor numèric, retorna el valor especial NaN (Not a Number).**
### Formatar numeros
Per mostrar resultats es habitual demanar un nombre de decimals per separar decimals o milers. Per fer-ho es pot fer com en el seguent exemple pero hem de tenir en compte que ho pasara a **string**:
![[Pasted image 20240920085055.png]]
Si es vol separar milers i decimals amb els caracters correctes podem fer-ho de la seguent manera:
![[Pasted image 20240920085246.png]]
Aixi segons del pais desde on es faci es veure d'una o d'altre forma, podem veure que en un separa per comes els milers i l'altre els decimals.
# Compostes
## Array
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
## Arrays constants
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
## Arrays bidimensionals
Podem imaginar una array bidimensional com una taula de files i columnes. Podem dir que una array bidimensional es una array de arrays.
### Definir i inicialitzar arrays bidimensionals
Les arrays bidimensionals es veuen de la seguent forma:
![[{E1DD1D3C-9F78-4924-B1F8-1BEC7FF16880}.png]]
Amb files i columnes, per exemple podem veure que "22" esta a la fila 2 columna 2.
![[{1A23622E-4FE5-4904-825B-D48E2A0A2F9E}.png]]
Per poder donar o assignar una valor d'una array bidimensional podem fer-ho de les seguents formes, donant el valor amb la estructura de nom de la array, el nº de la fila i el nº de la columna, i de la mateixa forma podem donarli aquest valor a una variable.
![[{386F820B-D0D0-459C-A937-A06D2BB05D34}.png]]
Per poder analitzar una array bidimensional en comptes de per files y despres columnes, podem fer-ho de la seguent forma començant per columnes y despres files.
Si volem agafar valors en diagonal nomes necesitem un "for", si volem diagonal de esquerra a dreta haurem de sumar, si es de dreta a esquerra fara falta restar.
## Objectes
Un objecte es per guardar dades de diferents tipus. Per definir un objecte i els seus atributs posem "{}", i dins podem posar els seus atributs. Per cridar algun atribut d'un objecte podem posar el nom de la variable del objecte, un punt i el nom del valor, de la seguent exemple "alumne.curs".
![[Pasted image 20241029120933.png]]
