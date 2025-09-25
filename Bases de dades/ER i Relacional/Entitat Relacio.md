# Entitat Relació
## Entitat
Una **entitat** és qualsevol objecte o concepte del món real que pot ser identificat de manera única i sobre el qual es vol emmagatzemar informació en una base de dades. Sempre es posa en majúscula i en singular.
## Entitat Feble
Una entitat feble NO té atribut identificador, per tant, com no té atribut identificador SEMPRE dependrà d'una entitat normal i mai pot ser 1,N i 1,M ha de ser 1,1 i 1,N o 0,1 i 1,N.
## Atribut
Un **atribut** és una característica o propietat d'una entitat. Els atributs descriuen l'entitat i contenen les dades específiques que volem emmagatzemar. En el cas de l'entitat “ALUMNE”, els atributs són “nom”, “cognom 1", i “cognom 2”. Aquests atributs proporcionen detalls sobre cada estudiant.
## Dada calculada
Aquesta és una dada que per algun motiu no és rellevant per guardar-la a la base de dades o només és necessari utilitzar-la de forma temporal.
### Atribut compost
Un atribut compost és com el nom indica un atribut el qual està format per altres atributs, per exemple podem veure que "nom complet" està format per "nom", "cognom1" i "cognom2" però aquest atribut és el valor d'aquests tres atributs, és a dir, no pot ser només per exemple "nom" i "cognom1" han de ser el tres.
## Relació
Una **relació** descriu com dues o més entitats estan connectades entre si. Per exemple, un estudiant pot estar matriculat en diverses assignatures, i aquesta connexió es representaria com una relació entre les entitats “ALUMNE” i “ASSIGNATURA”.
## N o M
És un valor infinit que es posa quan es fa una relació entre dues entitats i no tenim cap màxim, en cas d'en una relació siguin més d'un valor que no te màxim es posa N i M i en cas de només necessitar un número infinit en cas de no tenir cap màxim especificat es posa N.

![Pasted image 20240918113946.png](/Imatges/Pasted%20image%2020240918113946.png)

![Pasted image 20241002115133.png](/Imatges/Pasted%20image%2020241002115133.png)

## Relació

![Pasted image 20240916203252.png](/Imatges/Pasted%20image%2020240916203252.png)

Aquí podem veure una relació entre ALUMNE i ASSIGNATURA que bàsicament són els alumnes que estan matriculats a quines assignatures i a quines assignatures estan matriculats que alumnes.
## Relació reflexiva

![Pasted image 20240916205522.png](/Imatges/Pasted%20image%2020240916205522.png)

Això és una relació reflexiva que és bàsicament a quins empleats els dirigeix un empleat, en cas que hi hagi un jefe que és un empleat, aquest empleat dirigeix a N empleats.
## Relació amb valor

![Pasted image 20241003110239.png](/Imatges/Pasted%20image%2020241003110239.png)

Aquí podem veure que Alumne està a 1 o M mòduls i que 1 mòdul té 1 o N alumnes i que la relació entre alumne i mòdul és la nota que té 1 alumne a 1 mòdul.
## Relació ternària

![Pasted image 20241003110453.png](/Imatges/Pasted%20image%2020241003110453.png)

Aquí podem veure que aquesta relació té 3 entitats, en aquesta relació podem veure que un alumne pot tenir diferents notes a diferents convocatòries.
## Generalització i especialització

![](/Imatges/Pasted%20image%2020241017115106.png)

Aquí podem veure que les 3 entitats estan unides a persona perquè els atributs que té persona en tenen totes les altres entitats, per això es fa aquesta generalització per poder fer la base de dades millor, després els atributs que són específics d'una entitat es posen a la seva entitat respectiva, NO és una relació.
Característiques de la generalització:
- Quan trobem "s" significa "solapada" i quan es veu a una generalització significa que pertany a més d'una entitat, per exemple si trobem la "s" una persona podria ser ALUMNE i PROFESSOR a la vegada.
- Quan trobem "d" significa "disjunta" i quan es veu a una generalització significa que pertany a una única entitat, per exemple si trobem la "d" una persona només podria ser ALUMNE, PROFESSOR o PAS però només una.
- Quan trobem una "t" significa "total" i quan es veu a una generalització significa que pertany a una de les relacions que estan connectades, per exemple si posa "t" tota persona que estigui a la base de dades pertany a ALUMNE, PROFESSOR o PAS, però ha d'estar a algun obligatòriament.
- Quan trobem "p" significa "parcial" i quan es veu a una generalització significa que pot o no pertànyer a alguna de les entitats que connecta, per exemple si posa "p" una persona pot no pertànyer a ALUMNE, PROFESSOR o PAS.

![](/Imatges/Pasted%20image%2020241017120855.png)

La forma que s'utilitza i la forma clàssica

![](/Imatges/Pasted%20image%2020241017121142.png)

## Entitat associativa

![](/Imatges/Pasted%20image%2020241017122320.png)

Una entitat associativa és quan dues entitats relacionades es "transformen" en una entitat més gran per donar més sentit a una relació. Per exemple un client té un préstec d'una casa i la relació empleat es relaciona amb un empleat PERÒ el mateix client pot tenir un préstec també del seu cotxe amb un altre empleat.

[Exercicis Entitat Relacio](./Exercicis%20Entitat%20Relacio.md)