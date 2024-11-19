# Diseny descendent
Aquest mètode consisteix en dividir el problema en parts més petites, i si aquestes parts encara són massa grans o complicades, es tornen a subdividir.
Gran part dels exercicis de programacio segueixen la seguent estructura:
- Introducció de dades.
	- Introduir les dades del client.
	- Introduir les dades de la comanda.
	- Comprovar les dades introduïdes.
- Processament de dades.
	- Calcular subtotals.
	- Calcular descompte, IVA i import total.
- Visualització de resultats.
	- Mostrar la factura detallada.
	- Demanar confirmació de la compra.
	- Realizar el procés de pagament.
# Funcions
Una forma de fer aquest diseny es fer les funcions de forma que ens serveixin cada funcio per un proces diferent dins del codi, com en aquest exemple:
![[Pasted image 20241108105852.png]]
Al treballar amb funcions per dividir els procesos hem de tenir en compte quines variables son globals, que es poden utilitzar a qualsevol part del codi, i les variables locals, que son variables declarades dins de funcions y que per tant nomes es poden utilitzar en aquella funcio. Com en aquest exemple:
![[Pasted image 20241108110032.png]]
Aqui podem veure que "radi" i "area" son variables globals i que "radi2" es una variable local de la funcio "processarDades". Tambe podem pasar arguments dins de la funcio per pasar valors de variables y poder calcular en base a aquestes variables, pero la variable original no es modifica.
## Modificacions
Quan agafem dades a una funcio com per exemple:
![[Pasted image 20241118082753.png]]
En aquesta funcio "a" es una array, "separador" es una variable simple i "oneline" es un bolea, en aquest cas "separador" i "oneline" basicament son dades que en cas de ser modificades dins de la funcio, la variable que al declarar la funcio tenia el valor, no es modificara a la variable, nomes a la funcio. Pero en cas de "a" es una array per tant si no li donem el valor de aquesta array a un altre array dins de la funcio al modificar l'array "a" si que es modificara el valor fora de la funcio, perque es una dada mes complexa y en veritat el que es pasa en aquesta funcio es la direccio on es guarden el valors no els valors directament.
Els valors simples no es modificaran a la variable real, pero els valors mes complexes com arrays y objectes si es modificaran.
![[Pasted image 20241119110749.png]]
A mes a mes tambe podem donarli valors per defecte, es a dir, si ens donen l'array pero no ens donen el separador o si ho volen en 1 linea doncs a la mateixa declaracio de la funcio podem donarli un valor per defecte per si decas l'usuari no introdueix els valors.