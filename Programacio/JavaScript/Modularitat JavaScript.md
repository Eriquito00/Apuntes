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