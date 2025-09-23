# Entitat Relació
## Entitat
Una **entitat** és qualsevol objecte o concepte del món real que pot ser identificat de manera única i sobre el qual es vol emmagatzemar informació en una base de dades. Sempre es posa en majúscula i en singular.
## Entitat Feble
Una entitat feble NO te atribut identificador, per tant com no te atribut identificador SEMPRE dependrà de una entitat normal i mai pot ser 1,N i 1,M ha de ser 1,1 i 1,N o 0,1 i 1,N.
## Atribut
Un **atribut** és una característica o propietat d'una entitat. Els atributs descriuen la entitat i contenen les dades específiques que volem emmagatzemar. En el cas de la entitat “ALUMNE”, els atributs són “nom”, “cognom 1", i “cognom 2”. Aquests atributs proporcionen detalls sobre cada estudiant.
## Dada calculada
Aquesta es una dada que per algun motiu no es rellevant per guardarla a la base de dades o només es necesari utilitzarla de forma temporal.
### Atribut compost
Un atribut compost es com el nom indica un atribut el qual esta format per altres atributs, per exemple podem veure que "nom complet" esta format per "nom", "cognom1" i "cognom2" però aquest atribut es el valor de aquests tres atributs, es a dir, no pot ser només per exemple "nom" i "cognom1" han de ser el tres.
## Relació
Una **relació** descriu com dues o més entitats estan connectades entre si. Per exemple, un estudiant pot estar matriculat en diverses assignatures, i aquesta connexió es representaria com una relació entre les entitats “ALUMNE” i “ASSIGNATURA”.
## N o M
Es un valor infinit que es posa quan es fa una relacio entre dos entitats i no tenim cap maxim, en cas de en una relacio siguin mes d'un valor que no te maxim es posa N i M i en cas de nomes necesitar un numero infinit en cas de no tenir cap maxim especificat es posa N.

![Pasted image 20240918113946.png](/Imatges/Pasted%20image%2020240918113946.png)

![Pasted image 20241002115133.png](/Imatges/Pasted%20image%2020241002115133.png)

## Relacio

![Pasted image 20240916203252.png](/Imatges/Pasted%20image%2020240916203252.png)

Aqui podem veure una relacio entre ALUMNE i ASSIGNATURA que basicament son els alumnes que estan matriculats a quines assignatures y a quines assignatures estan matriculats que alumnes.
## Relacio reflexiva

![Pasted image 20240916205522.png](/Imatges/Pasted%20image%2020240916205522.png)

Aixo es una relacio reflexiva que es basicament aquins empleats els dirigeix un empleat, en cas de que hi hagi un jefe que es un empleat, aquest empleat dirigeix a N empleats.
## Relacio amb valor

![Pasted image 20241003110239.png](/Imatges/Pasted%20image%2020241003110239.png)

Aqui podem veure que Alumne esta a 1 o M moduls i que 1 modul te 1 o N alumnes i que la relacio entre alumne i modul es la nota que te 1 alumne a 1 modul.
## Relacio ternaria

![Pasted image 20241003110453.png](/Imatges/Pasted%20image%2020241003110453.png)

Aqui podem veure que aquesta relacio te 3 entitats, en aquesta relacio podem veure que un alumne pot tenir diferents notes a diferents convocatories.
## Generalitzacio i especialitzacio

![](/Imatges/Pasted%20image%2020241017115106.png)

Aqui podem veure que les 3 entitats estan unides a persona perque els atributs que te persona els tenen totes les altres entitats, per aixo es fa aquesta generalitzacio per poder fer la base de dades millor, despres els atributs que son especifics d'una entitat es posen a la seva entitat respectiva, NO es una relacio.
Caracteristiques de la generalitzacio:
- Quan trobem "s" significa "solapada" i quan es veu a una generalitzacio significa que pertany a mes de una entitat, per exemple si trobem la "s" una persona podria ser ALUMNE i PROFESOR a la vegada.
- Quan trobem "d" significa "disjunta" i quan es veu a una generalitzacio significa que pertany a una unica entitat, per exemple si trobem la "d" una persona nomes podria ser ALUMNE, PROFESOR o PAS pero nomes una.
- Quan trobem una "t" significa "total" i quan es veu a una generalitzacio significa que pertany a una de les relacions que estan connectades, per exemple si posa "t" tota persona que estigui a la base de dades pertany a ALUMNE, PROFESOR o PAS pero ha d'estar a algun obligatoriament.
- Quan trobem "p" significa "parcial" i quan es veu a una generalitzacio significa que pot o no perteneixer a alguna de les entitats que connecta, per exemple si posa "p" una persona pot no perteneixer a ALUMNE, PROFESOR o PAS.

![](/Imatges/Pasted%20image%2020241017120855.png)

La forma que s'utilitza i la foma clasica

![](/Imatges/Pasted%20image%2020241017121142.png)

## Entitat asociativa

![](/Imatges/Pasted%20image%2020241017122320.png)

Una entitat asociativa es quan dues entitats relacionades es "transformen" en una entitat mes gran per donar mes sentit a una relacio. Per exemple un client te un prestec d'una casa i la relacio empleat es relaciona amb un empleat PERO el mateix client pot tenir un prestec tambe del seu coche amb un altre empleat.

[Exercicis Entitat Relacio](./Exercicis%20Entitat%20Relacio.md)