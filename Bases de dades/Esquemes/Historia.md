# Dades i bases de dades
Les **dades** són fets enregistrables amb significat implícit, com noms o telèfons, que s'han convertit en un actiu valuós per a les empreses, ja que permeten millorar el rendiment i establir estratègies de mercat. Per aprofitar-les adequadament, cal organitzar-les de manera coherent, sovint mitjançant bases de dades.

Una **base de dades (BD)** és un conjunt estructurat d'informació relacionada, dissenyada amb un propòsit específic per a un grup concret d'usuaris. Per considerar-se una BD, ha de complir tres criteris principals:
1. **Representar un aspecte del món real** (univers de discurs).
2. **Tenir un significat coherent** (no ser un conjunt aleatori de dades).
3. **Estar creada amb un propòsit específic**.

Les BD són essencials per a la presa de decisions estratègiques i han de complir les següents característiques:
- **Persistència**: les dades han de ser rellevants i perdurar en el temps.
- **Relacions**: inclouen entitats (com clients o productes) i les connexions entre elles (per exemple, un client compra un producte).
- **Compartició**: permeten múltiples usos i accés simultani per diferents usuaris.

Les BD poden ser manuals o informatitzades. Un exemple manual seria el catàleg de targetes d’una biblioteca, mentre que les BD informatitzades s’administren amb programes especialitzats o Sistemes Gestors de Bases de Dades (SGBD).
***
# SGBD
Un **Sistema de Gestió de Bases de Dades (SGBD)** és un programari que permet gestionar bases de dades de manera eficient, garantint la seguretat, integritat i independència de les dades respecte a les aplicacions. Es pot implementar com una aplicació amb sistemes de comunicació (client-servidor, xarxa, etc.) o com llibreries enllaçades al programa.
### Funcions principals d’un SGBD:
1. **Gestió de dades**: Les aplicacions interactuen amb el SGBD per fer operacions, com consultes o modificacions.
2. **Independència de dades**: Les dades poden ser accessibles i modificables sense necessitat d’altres aplicacions.
3. **Seguretat i integritat**: Controla l'accés a les dades i assegura que siguin consistents.
### Elecció d’un SGBD:
L'elecció depèn de les necessitats i recursos de l'organització. Per analitzar el mercat, es pot consultar el **Quadrant Màgic de Gartner**, que classifica els SGBD segons:
- **Líders**: Excel·lents en execució i visió de mercat.
- **Aspirants**: Funcionals, però amb menys visió estratègica.
- **Visionaris**: Innovadors, però amb menys solidesa en la seva plataforma.
- **Jugadors de nínxol**: Especialitzats en àrees concretes.

Exemples com AWS i MongoDB han evolucionat en aquest quadrant, adaptant-se i millorant les seves capacitats.
![[Pasted image 20241127164756.png]]
### Sistema d’Informació:
És la infraestructura necessària per gestionar informació dins d’una organització. Inclou no només el programari, sinó també persones, procediments i altres recursos que treballen conjuntament per assolir els objectius de l’organització. La informació és essencial per a la presa de decisions i requereix eines eficients per a la seva manipulació.
***
# Universitat
Per gestionar la informació dins d’una **Universitat**, és necessari definir una **base de dades** que emmagatzemi i organitzi dades sobre processos com matrícula, qualificacions, horaris, i assignació de professors i alumnes a cursos.
### Entitats i Relacions:
- **Entitats**: Estudiants, facultats, cursos, professors, semestres.
- **Relacions**:
    - Els estudiants estan matriculats en assignatures.
    - Els estudiants estudien en facultats.
    - Cada facultat ofereix assignatures.
    - La universitat conté diverses facultats.

Cada element ha de tenir una estructura específica amb les dades que es volen emmagatzemar. Per exemple, per un **estudiant** es guardarien: nom, DNI, número d’estudiant, carreres i assignatures matriculades.
### Manipulació de dades:
1. **Consultes**:
    
    - Llistar els alumnes matriculats en una assignatura.
    - Obtenir els alumnes amb més d’un 7 en una assignatura concreta (com Base de Dades) l'any passat.
    - Comptar els professors que han impartit una assignatura al llarg dels anys.
2. **Actualitzacions**:
    
    - Modificar l’adreça d’un alumne.
    - Canviar el professor d’una assignatura.
    - Eliminar assignatures sense alumnes matriculats.
    - Assignar un alumne a una nova assignatura.

Aquest enfocament estructurat garanteix un sistema eficaç per gestionar i mantenir dades acadèmiques, facilitant tant l’actualització com les consultes.
***
# Decada dels 50
Durant la dècada dels 50, es van desenvolupar les **cintes magnètiques** que emmagatzemaven fitxers llegibles només de manera seqüencial. Això va donar lloc a les primeres **aplicacions basades en sistemes de fitxers**, considerades la **generació zero** dels sistemes de bases de dades, ja que el concepte de base de dades encara no existia.
![[Pasted image 20241127165109.png]]
### Funcionament:
1. **Fitxers mestre i de moviments**:
    - Es mantenia un fitxer mestre (ex. comptes bancàries).
    - Durant el dia s'acumulaven els moviments diaris en un fitxer fill.
    - A la nit, es processaven junts per crear un nou fitxer mestre actualitzat.
### Inconvenients:
1. **Lectura seqüencial**: Processament lent i inflexible.
2. **Dificultat per afegir atributs**: Modificar o ampliar dades era complicat.
3. **Duplicitat d’informació**: Cada programa tenia el seu conjunt de dades, cosa que generava redundància i malbaratament d'espai.
4. **Dependència de les dades**: Les dades estaven lligades a l'estructura interna del programa.
5. **Formats incompatibles**: Programes en diferents llenguatges no podien compartir fitxers fàcilment.
6. **Consultes predefinides**: Només es podien fer consultes preprogramades; noves necessitats requerien desenvolupar programes addicionals.

Aquest sistema, tot i ser pioner, tenia grans limitacions que van motivar l’evolució cap als sistemes moderns de bases de dades.
***
# Decada dels 60
Amb la introducció dels **discs magnètics**, es va revolucionar l'emmagatzematge de dades gràcies a la possibilitat d'accedir-hi de manera **directa**, sense necessitat de llegir registres seqüencialment. Això va permetre que els programes guardessin les adreces físiques de les dades (ex. número de compte) per accedir-hi de manera eficient.
### Desenvolupament de sistemes:
- **Sistemes centralitzats**: Consistien en un gran ordinador amb terminals "tontos" per interactuar-hi.
- **Models de dades jeràrquics**: Ex. IMS (Information Management System).
### Primer SGBD generalitzat:
- **Charles Bachman (1961)** va dissenyar el primer Sistema de Gestió de Base de Dades (SGBD) generalitzat: **Integrated Data Store (IDS)** de General Electric.
- Objectiu principal: Resoldre els problemes de gestió aïllada dels fitxers i assegurar la **coherència** de les dades.
### Característiques dels SGBD:
1. **Recuperació de dades** en cas de fallada.
2. **Gestió de concurrència**: Control automàtic de bloquejos per evitar conflictes en modificacions simultànies.
3. **Abstracció del model físic**: Els models lògics es creen independentment del format físic d'emmagatzematge.
### Model de dades en xarxa:
- **1969, CODASYL**: Primer model de dades en xarxa dissenyat gràcies a Bachman, posteriorment refinat per IBM amb l'IMS, desenvolupat per al programa Apollo de la NASA.
### Tipus de bases de dades desenvolupades:
1. **Jeràrquiques**: Organitzades en arbres.
2. **En xarxa**: Basades en llistes enllaçades.
Aquestes bases de dades aprofitaven l'accés directe dels discs magnètics, marcant un avenç significatiu en l'estructuració i la gestió de la informació.
![[Pasted image 20241127165354.png]]
***
# Decada dels 70
