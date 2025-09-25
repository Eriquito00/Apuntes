# Model Relacional
## Taules
Les taules aniran en plural i minúscules.

![](/Imatges/Pasted%20image%2020241106105927.png)


### Superclau
Son atributs que NO es poden repetir, poden ser 1 o més atributs que formen una superclau. Una superclau pot ser per exemple:

DNI - nom - cognoms
### Clau candidata
Una clau candidata és una superclau que quan s'elimina un atribut deixa de ser superclau. Per exemple tenim la superclau:

DNI - nom - cognoms 

Aquesta superclau si és clau candidata perquè si trèiem el DNI ja no seria una superclau, però en el següent exemple:

DNI - IDALU

Si trèiem DNI tenim el IDALU que també és únic i si trèiem IDALU tenim DNI, per tant, NO seria clau candidata.
### Clau primària
També coneguda per PK, una clau primària, és a dir, que només pot haver-hi UNA a cada taula, i NO pot ser NUL·LA. En el següent exemple:

DNI - nom - cognoms

La clau primària en aquest exemple no serien els tres, seria només DNI perquè és el que identifica i NO es repeteix. Si una clau primària es forma per dos atributs com per exemple una taula que s'identifica per lletres i un número es veuria així:

codi - lletra

En aquest cas els dos JUNTS són la clau primària.
### Clau alternativa
Les claus candidates NO escollides com a claus primàries (PK) són claus alternatives.
### Integritat referencial
És la connexió que tenen entre dues taules, per exemple:

alumnes

DNI (PK) - nom - cognoms


matrícules

(DNI (FK) - codi (FK) (PK)) - nota - any


crèdits

codi (PK) - nom - hores - curs


Aquí podem veure que la taula matrícula té com a atributs les dues PK de les altres dues taules. Però a les taules inicials han d'existir prèviament abans d'existir a la que es transmeten les dades, és a dir, que primer han d'existir les dades a alumnes i a crèdits abans que existeixin a la taula matrícules. A més a més, podem veure que la PK de la taula matrícules són les PK de les taules de les quals depèn.

A més a més, aquí podem veure que hi ha UN PK que és DNI i codi i de forma separada DNI i codi són claus foranes (FK). Una FK sempre ha de dependre de la PK d'una altra taula, però no té per què ser la FK una PK de la seva taula, per exemple:

DNI (PK) - nom - cognoms


matrícules

(DNI (FK) - codi (FK) (PK)) - nota - any (FK)


crèdits

codi (PK) - nom - hores - curs


any

año (PK)


Aquí podem veure que any es relaciona la PK amb la FK, però a la taula matricules la FK any no és una clau primària. A més a més, podem veure que la FK i la PK no tenen el mateix nom, però igualment es relacionen, no és necessari que tinguin el mateix nom. El valor d'una FK pot ser Nul sempre que aquesta FK no parteixi a una PK.
## Entitat relació a model relacional
### Pas 1
Agafem les entitats fortes i creem taules amb els seus atributs.
Si tenim atributs compostos es perdran.
La PK serà l'identificador de la taula.

![](/Imatges/Pasted%20image%2020241107105629.png)


### Pas 2
Agafem les entitats febles i creem taules amb els seus atributs.
Afegirem també la PK de l'entitat forta de la qual depèn, si depèn de dues o més doncs posem dues o més.

![](/Imatges/Pasted%20image%2020241107105719.png)


### Pas 3
Agafarem la generalització i especialitzacions i crearem taules amb els seus atributs.
Afegirem els atributs específics de cada especialització.
Afegirem la PK de l'entitat de la qual tenien totes en comú i aquesta FK i la PK.

![](/Imatges/Pasted%20image%2020241107105815.png)


### Pas 4
Busquem les relacions 1 a 1 com a màxims.
Agafarem la PK de qualsevol entitat que tenia el màxim 1 i els atributs que estaven a la relació i els afegim a l'altra taula de l'altra entitat posant com FK a la PK de l'altra entitat.

![](/Imatges/Pasted%20image%2020241107105906.png)


Si la relació és amb mínims 1,1 i 0,1 es tractarà de forma que sortirà millor si portem les dades cap a l'entitat que en té 0,1.

![](/Imatges/Pasted%20image%2020241107110052.png)


Si la relació és amb mínims 0,1 i 0,1 es tractarà de forma que es crearà una nova taula amb el nom que veiem convenient i es posaran els atributs de la relació, si no hi ha doncs res. Les PK poden ser o un o l'altre o els dos a la vegada.

![](/Imatges/Pasted%20image%2020241107110629.png)


### Pas 5
Busquem les relacions 1 a N com a màxims.
Agafarem la PK de l'entitat que tenia el màxim 1 i els atributs que estaven a la relació i els afegim a la taula de l'entitat que té el màxim de N posant com FK a la PK de l'altra entitat.

![](/Imatges/Pasted%20image%2020241107105919.png)


### Pas 6
Busquem les relacions de N a M.
Crearem una nova taula amb el nom que creiem convenient i els identificadors de les taules que contenien N a M seran PK de la nova taula, les dues juntes. Els atributs d'aquesta taula seran els atributs que estiguin a la relació, si no hi ha doncs res.

![](/Imatges/Pasted%20image%2020241107110340.png)


### Pas 7
Busquem les relacions ternàries, quaternàries...
Es crearà una nova taula amb el nom que veiem convenient i es posaran els atributs que hi ha a la relació i la PK seran el de totes les relacions que les formen, tots junts.

![](/Imatges/Pasted%20image%2020241107111003.png)


### Pas 8
Busquem les entitats associatives.
Crearem una nova taula amb el nom que creem convenient que la PK seran els identificadors de les dues taules de dins de l'entitat associativa i les relacions que hi hagi amb aquesta taula depenent si són 1,1 i 1,1 o 1,N i 1,1 o 1,N i 1M doncs s'aplicaran els passos 4, 5 o 6 depenent de la relació amb l'associativa.

![](/Imatges/Pasted%20image%2020241107111307.png)


### Pas 9
Incloure tota la informació necessària i útil per limitar l'entrada de dades o dades obligatòries, per exemple:
DNI: 8 dígits i 1 lletra.
Nom: obligatori.
Telèfon: numèric.
## MYSQL Workbench

### Tipus de Storage
- Primary Key: Clau primària.
- Foreign Key: Un atribut que prové d'un altra taula.
- Not Null: Aquest valor no pot ser null.
- Unique: Aquest valor no es pot repetir.
- Unsigned: Només pot ser un valor positiu i fa que siguin més útils els valors positius, si un tipus de dada arriba entre -100 i 100 aquest unsignet fa que pugui arribar entre 0 i 200.
- Auto Increment: Valor automàtic incremental, es crea un ID incremental que comença per 1.
- Generated: Un atribut calculat d'acord amb altres atributs.

### Característiques de les dades
- char: s'utilitza per dades amb longitud fixa i s'accedeix de forma més ràpida que varchar.
- varchar: s'utilitza per dades amb longitud dinàmica i s'accedeix de forma més lenta que char.
- int: s'utilitza per nombres enters positius i negatius.

Diferències entre char i varchar, principalment l'espai, ja que depenent la dada char ocuparà sempre el màxim que es pugui introduir i varchar s'adapta i ocupa només el que ocupen les dades. Però també char, per dades amb longitud definida i que sabem que no serà més gran, aquesta dada serà més ràpida accedir a ella si és char i si posem varchar serà més lent l'accés a aquesta dada.
## Normalització
La normalització costa de fer aquestes dades que es repeteixen per fer el model més senzill.
Tenim una taula amb l'estructura següent:

| matricula | marca | model | color |

En aquest cas si la matrícula és 1111 AAA, la marca el model i el color ja es poden saber perquè aquell cotxe només té aquesta matrícula que és única per ell.
### Forma normal 1
Un atribut no pot tenir 2 valors:

| codi | pel·lícula | dates emissió |

| 1 | Star Trek | 1/12/24 - 2/12/24 - 3/12/24 |

Aquesta taula NO compleix.
Bàsicament que un atribut només pot tenir 1 valor.

| codi | pel·lícula | dates emissió |

| 1 | Star Trek | 1/12/24 |

| 1 | Star Trek | 2/12/24 |

| 1 | Star Trek | 3/12/24 |

Aquesta taula SI compleix.
### Forma normal 2
Una taula té un atribut que depèn d'un atribut de la PK però no d'altres:

| client | exercici | preu |

| 1 | ciclisme | 25 |

| 1 | aeròbic | 30 |

Aquesta taula NO compleix.
Bàsicament que preu depèn d'exercici, però no depèn de client.

Taula 1

| client | exercici |

| 1 | ciclisme |


Taula 2

| exercici | preu |

| ciclisme | 25 |

Aquesta taula SI compleix.
### Forma normal 3
Trencar les taules per separar les dades iguals:

| client | edifici | preu |

| 1 | e1 | 25 |

| 2 | e1 | 25 |

| 3 | e2 | 30 |

| 4 | e1 | 25 |

| 5 | e2 | 30 |


Aquesta taula NO compleix:
Bàsicament, el que passa és que preu depèn d'edifici i edifici de client, per tant, s'han de separar.

Taula 1

| client | edifici |

| 1 | e1 |

| 2 | e1 |

| 3 | e2 |

| 4 | e1 |

| 5 | e2 |


Taula 2

| edifici | preu |

| e1 | 25 |

| e2 | 30 |


Aquesta taula SI compleix.

1. **Primera Forma Normal (1NF):**
- Assegura que cada columna té un sol valor (dates atòmics).
1. **Segona Forma Normal (2NF):**
- Compleix amb la 1NF.
- Elimina dates que depenen d'una part de la clau primària (clau composta).
1. **Tercera Forma Normal (3NF):**
- Compleix amb la 2NF.
- Elimina dependències indirectes entre columnes que no són claus primàries.