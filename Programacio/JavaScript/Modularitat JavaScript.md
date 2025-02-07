# Modularitat JavaScript

## Disseny descendent

Aquest mètode consisteix en dividir el problema en parts més petites, i si aquestes parts encara són massa grans o complicades, es tornen a subdividir.  
Gran part dels exercicis de programació segueixen la següent estructura:
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
	- Realitzar el procés de pagament.

## Funcions

Una forma de fer aquest disseny és fer les funcions de forma que ens serveixin cada funció per un procés diferent dins del codi, com en aquest exemple:

![](/Imatges/Pasted%20image%2020241108105852.png)

Al treballar amb funcions per dividir els processos hem de tenir en compte quines variables són globals, que es poden utilitzar a qualsevol part del codi, i les variables locals, que són variables declarades dins de funcions i que per tant només es poden utilitzar en aquella funció. Com en aquest exemple:

![](/Imatges/Pasted%20image%2020241108110032.png)

Aquí podem veure que "radi" i "area" són variables globals i que "radi2" és una variable local de la funció "processarDades". També podem passar arguments dins de la funció per passar valors de variables i poder calcular en base a aquestes variables, però la variable original no es modifica.

### Modificacions

Quan agafem dades a una funció com per exemple:

![](/Imatges/Pasted%20image%2020241118082753.png)

En aquesta funció, "a" és una array, "separador" és una variable simple i "oneline" és un booleà. En aquest cas, "separador" i "oneline" bàsicament són dades que, en cas de ser modificades dins de la funció, la variable que al declarar la funció tenia el valor, no es modificarà a la variable, només a la funció. Però en cas de "a" és una array, per tant, si no li donem el valor d'aquesta array a un altre array dins de la funció, al modificar l'array "a" sí que es modificarà el valor fora de la funció, perquè és una dada més complexa i, en realitat, el que es passa en aquesta funció és la direcció on es guarden els valors, no els valors directament.  
Els valors simples no es modificaran a la variable real, però els valors més complexes com arrays i objectes sí es modificaran.

![](/Imatges/Pasted%20image%2020241119110749.png)

A més a més, també podem donar-li valors per defecte, és a dir, si ens donen l'array però no ens donen el separador o si ho volen en 1 línia, doncs a la mateixa declaració de la funció podem donar-li un valor per defecte per si de cas l'usuari no introdueix els valors.
