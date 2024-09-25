Quan es decideix que cal fer un programa per resoldre una tasca determinada, s'ha tenir en compte que no es tracta de posar-se a programar immediatament.  
Cal seguir uns passos per què es pugui dur a terme de manera exitosa:
1. **Definir el problema**: obtenir els requisits del programa, parlar amb el client i els usuaris, proposar diferents solucions i decidir quina és la més adequada.
2. **Dissenyar l'algorisme**: pensar quines dades es necessitaran, quins resultats el volen obtenir i quines instruccions cal donar a l'ordinador.
3. **Implementar el programa, verificar el funcionament i documentar-lo**: escriure el codi, provar el programa i explicar les característiques i la forma d'utilitzar-lo.
4. **Posar-lo en marxa i fer el manteniment** (fase d'explotació): instal·lar-lo en les màquines adequades, comprovar el funcionament _in-situ_, formar l'usuari, corregir els errors que es detectin durant la seva utilització i implementar els canvis o millores que demani el client.
Només el 3r apartat és feina del programador, però de vegades també li pot tocar fer algun dels altres.
## Estructura d'un programa
La majoria de programes estan composats per cinc grans blocs funcionals:
1. Definició i inicialització de les constants i variables que necessitarà el programa.
2. Introducció de dades (demanar o agafar les dades que necessita i guardar-les en variables).
3. Processament de les dades.
4. Mostrar els resultats (per pantalla, impressora...)
5. Finalitzar el programa (alliberar la memòria que ja no necessita).
No s'ha d'agafar aquesta estructura al peu de la lletra però l'ordre sí que s'ha de respectar: abans de poder processar les dades, s'han d'haver introduït; i abans de poder mostrar un resultat s'han d'haver processat les dades que porten a aquest resultat.
## Estructures bàsiques

Al principi, no hi havia un mètode per programar.  
Cada programador feia els programes com millor li semblava: alguns escrivien codi força ben endreçat i comprensible mentre que altres feien codi difícil d'entendre.
El primer mètode proposat per fer el codi més comprensible i fàcil de depurar va ser la **programació estructurada**.
Aquest mètode consisteix en un conjunt d'estructures formades per blocs de codi, cada una d'elles amb una funció ben diferenciada. Al fer els programes només es pot triar entre aquestes estructures estàndard:
- **Estructura seqüencial**: les instruccions del bloc de codi s'executen una darrera de l'altra. És el tipus de codi que hem estat fent fins ara.
- **Estructura condicional**: hi ha diferents blocs de codi i, depenent de certes condicions, es triarà quin d'ells s'executarà.
- **Estructura iterativa (de repetició)**: un bloc de codi que s'executa un nombre determinat de vegades o fins que es compleixi una condició.
## Diagrames de flux
Una forma de especificar què ha de fer un programa, és crear un diagrama de flux. Aquests diagrames donaran una idea del quins blocs s'han de programar i ajudaran a preveure casos que potser no s'havien contemplat en un principi. Per fer un diagrama de flux s'utilitzen figures geomètriques i text. A continuació hi ha un diagrama genèric (dins de les figures caldria especificar què ha de fer cada bloc). I a sota un programa en JavaScript que podria ser l'equivalent a aquest diagrama.
![[Pasted image 20240923091048.png]]
![[Pasted image 20240923091137.png]]
