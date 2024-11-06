# Taules
Les taules aniran en plural i minuscules.
![[Pasted image 20241106105927.png]]
## Superclau
Son atributs que NO es poden repetir, poden ser 1 o mes atributs que formen una superclau. Una superclau pot ser per exemple:
DNI - nom - cognoms
## Clau candidata
Una clau candidata es una superclau que quan s'elimina un atribut deixa de ser superclau. Per exemple tenim la super clau:
DNI - nom - cognoms 
Aquesta superclau si es clau candidata perque si treiem el DNI ja no seria una superclau, pero en el seguent exemple:
DNI - IDALU
Si treiem DNI tenim el IDALU que tambe es unic i si treiem IDALU tenim DNI per tant NO seria clau candidata.
## Clau primaria
Tambe coneguda per PK, una clau primaria, es a dir, que nomes pot habe UNA a cada taula, i NO pot ser NULA.
En el seguent exemple:
DNI - nom - cognoms
La clau primaria en aquest exemple no serien els tres, seria nomes DNI perque es el que identifica i NO es repeteix. Si una clau primaria es forma per dos atributs com per exemple una taula que s'identifica per lletres i un numero es veuria aixi:
codi - lletra
En aquest cas els dos JUNTS son la clau primaria.
## Clau alternativa
Les claus candidates NO escollides com a claus primaries (PK) son claus alternatives.
## Integritat referencial
Es la conexio que tenen entre dos taules, per exemple:
alumnes
dni(PK) - nom - cognoms
matricules
(dni(FK) - codi(FK)(PK)) - nota - any
credits
codi(PK) - nom - hores - curs
Aqui podem veure que la taula matricula te com a atributs les dues PK de les altres dues taules. Pero a les taules inicials han de existir previament abans de existir a la que es transmeten les dades, es a dir, que primer han de existir les dades a alumnes y a credits abans de que existeixin a la taula matricules. A mes a mes podem veure que la PK de la taula matricules son les PK de les taules de les que depen.
A mes a mes aqui podem veure que hi ha UN PK que es dni i codi i de forma separada dni i codi son claus foranes (FK). Una FK sempre ha de dependre de la PK d'una altre taula pero no te perque ser la FK una PK de la seva taula, per exemple:
dni(PK) - nom - cognoms
matricules
(dni(FK) - codi(FK)(PK)) - nota - any(FK)
credits
codi(PK) - nom - hores - curs
any
año(PK)
Aqui podem veure que any es relaciona la PK amb la FK pero a la taula matricules la FK any no es una clau primaria. A mes a mes podem veure que la FK i la PK no tenen el mateix nom pero igualment es relacionen, no es necesari que tinguin el mateix nom. El valor de una FK pot ser Nul sempre i cuan aquesta FK no perteneixi a una PK.
# Entitat relacio a model relacional
## Pas1
Agafem les entitats fortes i creem taules amb els seus atributs.
Si tenim atributs compostos es perdran.
La PK sera l'identificador de la taula.
## Pas2
Agafem les entitats febles i creem taules amb els seus atributs.
Afegirem tambe la PK de la entitat forta de la que depen, si depen de dues o mes doncs posem dues o mes.
## Pas3
Agafarem les generalitzacion i especialitzacions i crearem taules amb els seus atributs.
Afegirem els atributs especifics de cada especialitzacio.
Afegirem la PK de la entitat de la que tenien totes en comu i aquesta FK i la PK.
## Pas4
Busquem les relacions 1 a 1 com a maxims.
Agafarem la PK de qualsevol entitat que tenia el maxim 1 i els atributs que estaben a la relacio i els afegim a la altre taula de la altre entitat posant com FK a la PK de la altre entitat.
## Pas5
Busquem les relacions 1 a N com a maxims.
Agafarem la PK de la entitat que tenia el maxim 1 i els atributs que estaben a la relacio i els afegim a la taula de la entitat que te el maxim de N posant com FK a la PK de la altre entitat.
## Pas6