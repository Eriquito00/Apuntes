# Història
## Dades i bases de dades
### Què és una dada? 
Fets coneguts que poden enregistrar-se i que tenen un significat. 
### Què és una base de dades? 
Un conjunt endreçat d'informació que s'emmagatzema mitjançant algun tipus de suport i que es pot consultar i mantenir. 
### Característiques de les BBDD:

#### Persistència:
- Les dades que han de durar en el temps.
- Només s'emmagatzemen dades rellevants.    
#### Relacions:
- Entitats, conjunt de dades respecte a un tema
- Relacions, connexions entre entitats    
#### Compartir:
- Diferents maneres d'entrar, mantenir i visualitzar les dades
- Interessa que moltes persones puguin utilitzar al mateix temps la base de dades. Tant per mantenir com per visualitzar
***
## SGBD
### Que és un SGBD?
Un sistema de gestor de base de dades, programari que permet gestionar un conjunt de dades.
Les aplicacions no accedeixen directament a les dades, li demanen al SGBD.
Per tal que un programari pugui considerar-se SGBD ha de ser capaç de facilitar una sèrie d'operacions. Una de les capacitats més importants que ha de tenir és la independència de les dades respecte a les aplicacions.
#### Tipus de SGBD
Líders: Obtenen les millors puntuacions
Aspirants: Bones funcionalitats, però no arriben a líders.
Visionaris: Tenen habilitat per anticipar-se, però no tenen plataforma sòlida.
Nínxols específics: Enfocats en determinades àrees de les tecnologies.
Exemples com AWS i MongoDB han evolucionat en aquest quadrant, adaptant-se i millorant les seves capacitats.

![Pasted image 20241127164756.png](/Imatges/Pasted%20image%2020241127164756.png)

#### Sistema d’Informació:
Conjunt d'elements relacionats entre si d'acord amb certes regles que aporten a l'organització la informació necessària per a l’acompliment dels seus propòsits.
#### Distribució de BBDD
La tecnologia utilitzada habitualment en la distribució de BD és l'arquitectura client/servidor.
***
## Dècada dels 50
NO existien les BBDD. Fer una cerca de dades a la unitat de cinta era molt lent, ja que havia de fer tota la volta a tota la cinta per poder trobar la dada necessària.

S’inventen les cintes magnètiques, aquestes només es poden llegir de forma seqüencial i ordenadament.

Les cintes emmagatzemaven fitxers amb registres que es processaven seqüencialment juntament amb fitxers de moviments per generar nous fitxers actualitzats.

Això era conegut com la generació zero dels sistemes de base de dades, ja que llavors no existia ni el concepte de base de dades.

![Pasted image 20241127165109.png](/Imatges/Pasted%20image%2020241127165109.png)

***
## Dècada dels 60
El 1961 Charles Bachman va dissenyar el primer SGBD generalitzat.

Un SGBD hi havia de, en primer lloc, assegurar la coherència de les dades en tot moment. (Bàsicament, complir les tres normes a la vegada de CAP).
CAP:
C: Consistència.
A: Disponibilitat.
P: Tolerància a Particions.

![Pasted image 20241209172322.png](/Imatges/Pasted%20image%2020241209172322.png)

Gràcies a això en 1969 es concep el primer model de BBDD conegut com a CODASYL i posteriorment el va desenvolupar IBM.

Van aparèixer les bases de dades jeràrquiques i en xarxa:

![Pasted image 20241127165354.png](/Imatges/Pasted%20image%2020241127165354.png)

***
## Dècada dels 70
Edgar Frank Codd en la dècada dels 70 s creo el modelo relacional.

Avui en dia, el model relacional de Codd, tot i les existents variants i alternatives, segueix essent el més utilitzat a tots els nivells i la seva potent base matemàtica del model va ser la clau del seu èxit.

Al voltant del 1976 el doctor Peter. Chen va proposar un model conceptual anomenat Entitat-Relació (Entity-Relationship / ER) per tal de dissenyar Base de Dades.

Durant la dècada dels 70 s es va crear el llenguatge SEQUEL (SQL antic).
***
## Anys 80:
Durant la dècada dels 80 IBM llança el seu motor de base de dades DB2 basant-se en el seu sistema System R.

En la dècada dels 80 és on el sistema relacional agafa més volada i es proposa com a principal model de dades per a moltes empreses utilitzant els SGBD relacionals.

IBM crea el llenguatge SQL durant la dècada dels 80 s, concretament l'any 1986, on l’Institut Nacional Nord-americà de Normalització (ANSI) va publicar les primeres normes que enunciaven la sintaxi i la semàntica de l’SQL i aquest passa a convertir-se en llenguatge estàndard de les BD relacionals.
***
## Anys 90:
Al final de la dècada dels 90 s IBM i ORACLE creen les bases de dates orientades a objectes (ODBMS).

![Pasted image 20241209171518.png](/Imatges/Pasted%20image%2020241209171518.png)

***
## Personatges importants
Charles Bachman: dissenyador del primer SGBD generalitzat.

![Pasted image 20241209173016.png](/Imatges/Pasted%20image%2020241209173016.png)

Edgar Frank "Ted" Codd: creador del model relacional.

![Pasted image 20241209173036.png](/Imatges/Pasted%20image%2020241209173036.png)

Peter Chen: creador del model Entitat-Relació.

![Pasted image 20241209173052.png](/Imatges/Pasted%20image%2020241209173052.png)
