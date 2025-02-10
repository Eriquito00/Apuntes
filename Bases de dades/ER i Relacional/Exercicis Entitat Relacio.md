# Exercicis Pizzeria Andiamo
## Exercici 1.1
Dissenyeu un petit diagrama ER pel següent fragment del sistema: La cadena de pizzeries té una carta de pizzes a on cadascuna d'elles té un nom i poden ser de diferents mides (individual, mitjana o familiar). Hem de poder guardar un preu diferent depenent de la mida i el nom de la pizza.
![[Pasted image 20240918112531.png]]
Cada Pizza es relaciona amb la mida depenent del preu que te, si la pizza es individual tindra un preu, si es mitjana un altre preu i una familiar un altre, per tant tenim una pizza que pot tenir 3 mides i tenim una mida que pot tenir una pizza.
## Exercici 1.2
Dissenyeu un petit diagrama ER pel següent fragment del sistema: Cada ingredient d'una pizza pot ser substituït per altres ingredients, en cas d'inexistència. Per exemple quan no hi ha mozzarella aquesta es substitueix per formatge emmental o parmesà. O per exemple quan no hi hagi pomodoro podrem utilitzar marinara o tomàquet triturat.
![[Pasted image 20240918112555.png]]
Es pot sustituir un ingredient per exemple pernil per un altre ingredient de la mateixa entitat com per exemple tonyina.
## Exercici 2
Dissenyeu un petit diagrama ER pel següent fragment del sistema: La cadena de pizzeries té diferents locals repartits per tot Catalunya. Els locals que poden ser de tipus restaurant, on els clients poden degustar-hi les pizzes in situ, o de tipus “per emportar”. Un mateix local pot ser, a la vegada, restaurant i admetre comandes per emportar. Cada local l'identifiquem mitjançant un número correlatiu i ens n'hem de guardar la seva adreça completa (carrer, número, codi postal i població), la data de la seva inauguració i els metres quadrats.
![[Pasted image 20240918112616.png]]
Aqui podem veure que un local te el seus respectius atributs i tambe por estar relacionat segons si es delivery, restaurant o delivery i restaurant per tant pot tenir un o mes serveis i un tipus de servei pot tenir un o mes restaurants.
## Exercici 3
Dissenyeu un petit diagrama ER pel següent fragment del sistema: Per cada comanda, en una pizzeria, cal enregistrar les línies que la componen, Les comandes han de guardar la següent informació d'exemple.
Exemple de comanda:
```
    COMANDA 278 – 25/05/2021
        2 Pizza margarita individual 10 €/unitat
        1 Pizza americana individual 12 €/unitat
        4 Aigues 1,5 €/unitat
    TOTAL: 38 €
```
![[Pasted image 20240918121425.png]]
Aqui podem veure que depenent de la mida de la pizza tindra un preu o altre segons la relacion entre pizza y la mida y tambe depenent del preu de la pizza o de la beguda es posa a la comanda, pero podem agafar per exemple nomes begudes o nomes pizza per tant la relacio entre beguda i comanda es que podem no demanar beguda i nomes demanar pizza i pizza i comanda que podem no demanar pizza i demanar nomes begudes.
## Exercici 4
Dissenyeu un petit diagrama ER pel següent fragment del sistema: Cal enregistrar a la nostra base de dades, quin empleat serveix cada comanda, en una pizzeria, per tal de poder obtenir a posteriori l’empleat del mes (aquell que ha facturat més). Els empleats els identificarem per el seu DNI, però en voldre guardar també el seu nom i cognoms.
![[Pasted image 20240919105613.png]]
Aqui podem veure que un empleat pot fer varies comandes pero una comanda nomes pot ser feta per un empleat.
## Exercici 5
Dissenyeu un petit diagrama ER pel següent fragment del sistema: A la cadena de pizzeries, cada empleat té associada una moto per si algun dia ha de fer la feina de motorista, però una moto és compartida per diversos empleats de diversos torns.
![[Pasted image 20240919112600.png]]
Aqui es pot veure que la relacio entre empleat i moto es si surt a repartir i que un empleat te asignada una moto i una moto pot estar asignada a varios empleats.
## Exercici 6.0
Dissenyeu un petit diagrama ER pel següent fragment del sistema: La cadena de pizzeries té diferents empleats i aquests estan assignats en els diferents locals que la cadena de pizzes té arreu de tot Catalunya. Quan la cadena contracta a un empleat li assigna un perfil (cuiner, cambrer, telefonista o motorista) i un local.

Cal tenir en compte que un empleat pot canviar de rol en un dia determinat o de local. Ens interessa saber el dia que aquest empleat a començat a treballar d'aquest rol. En definitiva ens interessa guardar quins diferents rols han anat tenint els empleats i en quins locals han estat assignats.

Per simplificar el disseny un empleat no pot assignar-se dues vegades al mateix rol i local.

Per exemple:

- El dia **21/05/2000** l'empleat amb DNI **111** va entrar a treballar de **cambrer** al **local 1**
- El **dia 22/10/2001** el mateix empleat va canviar a **telefonista**, però sense canviar de local.
- El dia **21/05/2000** l'empleat amb DNI **222** va entrar a treballar de **cuiner** al **local 2**
- El dia **01/12/2002** l'empleat **222** el van canviar de local.
![[Pasted image 20240919121835.png]]
Aqui podem veure que un empleat pot estar a varios locals i pot tenir varios rols i que un rol  pot tenir varios empleats i un local pot tenir varios empleats.
## Exercici 6.1
Modifica el diagrama anterior de tal manera que podem guardar l'historial que ha tingut un empleat i amb quins rols dins de la nostra cadena de pizzeries.
![[Pasted image 20240919121954.png]]
Aqui es pot veure que un empleat pot fer varios canvis pero un canvi nomes es d'un empleat.
## Exercici 7
Dissenyeu un petit diagrama ER pel següent fragment del sistema: En cada local de la cadena de pizzeries cal controlar l'estoc de cada ingredient que hi ha en un moment determinat, així com l'estoc mínim admissible. Aquest serveix perquè el sistema doni un avís de compra si l'estoc d'aquest ingredient està per sota d'aquest mínim.
![[Pasted image 20240920082404.png]]
Aqui podem veure que cada local dirigeix els seus ingredients i que un local te un o mes ingredients i un ingredient te un unic local.
## Exercici 8.0
Dissenyeu un petit diagrama ER pel següent fragment del sistema: Un empleat en un cert moment pot substituir a un altre empleat si aquest està malalt. Ens interessa saber quan el va substituir.

Per simplificar el disseny un empleat només pot substituir el mateix empleat una sola vegada.
![[Pasted image 20240925105204.png]]
Aqui es pot veure que un empleat pot substituir a un altre empleat i la data de substitucio es guarda a un atribut de la relacio.
## Exercici 8.1
Intenta de modificar el diagrama anterior per no tenir la restricció de que un empleat només pot substituri el mateix empleat una sola vegada.
![[Pasted image 20240925110700.png]]
Aqui es pot veure que un empleat pot substituir un altre empleat i la data inici i la data final es guarden a la entitat data.
## Exercici 9
Dissenyeu un petit diagrama ER pel següent fragment del sistema: Dissenyeu un petit diagrama ER pel següent fragment del sistema: En els locals que són de tipus restaurant, hi ha diverses taules. De cada taula ens cal saber el nombre de seients que té. Sabem que les taules s'enumeren amb un número seqüencial dins d'un local.
![[Pasted image 20240925112235.png]]
Aqui podem veure que un local pot tenir 0 o N taules i una taula nomes pot tenir un local.
## Exercici 10
Dissenyeu un petit diagrama ER pel següent fragment del sistema: En els locals de tipus restaurant s’admeten reserves. Llavors caldrà enregistrar el nom, el telèfon, el nombre de persones i la data i hora de la reserva, a més de la taula que se’ls assignarà, en el moment de fer la reserva.

Cada reserva està identificada per un codi que vindrà generat per el nostre aplicatiu.
![[Pasted image 20240925113935.png]]
Aqui podem veure que un local te 0 o N taules i una taula te un local i una taula pot tenir una reserva i una taula pot tenir 0 o N reserves durant el dia.
# Exercicis La Volta
## Exercici 1
Les etapes de La Volta s’identifiquen per un número correlatiu, a comptar a partir de l’1, que com és lògic s’associa a la primera etapa, a continuació el 2 s’associa a la segona, i així successivament fins a l’última. Cada etapa comença en una localitat i acaba en una altra. La localitat d'arribada pot ser la mateixa que la de sortida si l'etapa és circular.

Ens cal saber la data en la qual es desenvolupen les etapes. No hi pot haver cap etapa que duri més d'un dia. També ens diuen que cal guardar el total de Kms de cada etapa.
![[Pasted image 20240926111249.png]]
Aqui podem veure que una etapa comença a una localitat i que una localitat pot estar a 0 o M etapes i igual amb la localitat que acaba.
## Exercici 2
Cada etapa de La Volta pot incloure un o més ports de muntanya (o cap), però cada port només pot estar inclòs dins d’una etapa. Dels ports de muntanya ens interessa saber el seu topònim i la seva alçada en metres.
![[Pasted image 20240926105210.png]]
Aqui podem veure que una etapa pot tenir zero o M i un port pot estar nomes a una etapa.
## Exercici 3
Cada etapa de La Volta passa pel territori d’una o més províncies, però per una mateixa província pot passar més d’una etapa (o cap). Cal registrar el total de km de cada etapa que travessen per cada província. Per exemple, a l'etapa 2 es travessa 35 km per la província de Barcelona i 47 km per la província de Tarragona.
![[Pasted image 20240926112117.png]]
Aqui podem veure que una etapa pasa per 0 o N provincies i que una provincia pot estar a mes d'una etapa.
## Exercici 4
La nostra base de dades ha de poder registrar quin ciclista porta cada mallot (general, punts, muntanya, etc.) a cada etapa de La Volta. Cada mallot s’identifica gràcies a un codi (3 lletres) i un color determinat. Els ciclistes s’identifiquen per un dorsal, i a la BD ha de constar també el seu nom i cognoms i la seva data de naixement.
![[Pasted image 20240926123453.png]]
Aqui podem veure que un ciclista pot portar 0 o 4 mallots i que un mallot el port portar 0 o 1 ciclista.
## Exercici 5
Els ports de muntanya s’identifiquen pel seu topònim, i tenen una una alçada determinada per sobre del nivell del mar.

Depenent de la dificultat els ports es classifiquen en quatre categories (especial, 1a, 2a i 3a).

Cal dissenyar un sistema per tal d’emmagatzemar els punts que poden assolir els ciclistes segons la posició en què arribin a cada port segons es detalla a continuació.
![[Pasted image 20241002110636.png]]
Aqui podem veure que una categoria pot tenir 0 o N ports i que un port nomes pot tenir una categoria i que una categoria te una o M posicions i que una posicio te 1 o N ports en funcio dels punts.
## Exercici 6
Seguint el mateix funcionament que el Tour de França es determinarà el sistema de puntuació per aconseguir el mallot verd.

Cada etapa es categoritzarà en: etapa plana, etapa mitja muntanya, etapa de muntanya, contrarellotge individual.

Els punts s'obtindran per el primers llocs de cada etapa i en funció de la seva categoria. La distribució de punts es realitzarà mitjançant la següent taula:

- Etapes planes: 50, 30, 20, 18, 16, 14, 12, 10, 8, 7, 6, 5, 4, 3 y 2 punts respectivament des del primer fins el quinzè ciclista en arribar a la meta.
- Etapes de mitja muntanya: 30, 25, 22, 19, 17, 15, 13, 11, 9, 7, 6, 5, 4, 3 y 2 punts respectivament des del primer fins el quinzè ciclista en arribar a la meta.
- Etapes de muntanya i contrarellotges individuals: 20, 17, 15, 13, 12, 10, 9, 8, 7, 6, 5, 4, 3, 2 y 1 punts respectivament des del primer fins el quinzè ciclista en arribar a la meta.
![[Pasted image 20241002113313.png]]
Aqui podem veure que una posicio te 1 o N tipus y un tipus 1 o M posicions  segons els punts i que 1 tipus te 1 o N etapes i que una etapa pot tenir 1 tipus.
# Eleccions generals
Davant les properes eleccions al Congrés dels Diputats, se'ns demana que prepareu el disseny d'una base de dades utilitzant el model E/R vist a classe que permeti:

- A les eleccions s'hi presenten una sèrie de partits PP(Partit Pessimista), PSOE (Partit Salat i Organitzat d'Espanya), IU (Independents Units), PODEMOS (Parit Oficial Demòcrata Espanyol Municipalista Obrer Social) entre altres. A on ens interessa saber el nom llarg i les sigles del partit (aquestes seran úniques per cada partit).
- Els escons del Congrés venen determinats per les circumscripcions. Cada circumscripció té assignat un nombre determinat d'escons en el Congrés.
- Cada circumscripció s'identifica de manera única amb un nom i aquesta correspon només amb una província de l'estat que s'identifica amb un codi i a més a més ens interessa guardar el seu nom, el nom de la capital, a quina comunitat autònoma pertany i la superfície de m2.
- Per cada circumscripció es poden presentar un número determinat de llistes de partits polítics (poden haver-hi partits que no es presentin en una determinada circumscripció) i aquestes només es poden presentar en una sola circumscripció.
- Aquestes llistes de partits polítics estan formades per candidats dels quals ens interessa saber el seu dni, nom, nº de vegades que s'ha presentat, quin nº ocupa a la llista.
- Evidentment un candidat només serà d'un partit i ens interessa saber quin és el candidat de cada partit que es presenta per President del Govern.
- Cada província té un conjunt de ciutadans que voten en els municipis on estan empadronats, els quals es té la informació de el seu dni, nom, cognoms, telèfon, adreça.
- Cada municipi s'identifica amb un codi únic i a més amés ens interessa saber el seu nom, el nom complet (nom i cognoms de l'actual alcalde).
- A cada municipi es disposen les meses electorals corresponents per què els ciutadans votin. Normalment es situen en col·legis electorals. A cada ciutadà li correspondrà anar a votar a una determinada mesa electoral i vota a una sola llista (no vota a un candidat, sinó a una llista de la seva circumscripció).
- Les meses electorals s'identifiquen pel municipi a on són i dins el municipi per districte (valor numèric de dos dígits), secció (valor numèric 3 dígits) i mesa(caràcter representat per una lletra). La conjunció dels valors de districte, secció i mesa poden ser iguals en diferents municipis, però no dins el mateix municipi.
- El nostre sistema ha de permetre que el dia de les eleccions i després del recompte de vots, cada mesa pugui entrar el número de vots que han obtingut de les llistes dels partits que s'hi presentaven.

**El nostre sistema cal que permeti. Entre altres coses, fer consultes del tipus:**

- Nº d'habitants empadronats en un municipi.
- Votants d'un municipi i quina mesa tenen assignada.
- Municipis d'una província
- Partits que es presenten en una província.
- Quin són els candidats d'un partit en una determinada província.
- Per cada partit, quin és el candidat que es presenta com a President del Govern.
- Número de vots que ha obtingut un partit en una mesa, en un municipi i en una província.
![[image.png]]
# DGT (Direcció General de Trànsit)
La Direcció General de Trànsit (DGT) vol mantenir certa informació del parc de vehicles a nivell d'Estat Espanyol per tal de fer una gestió adequada de les infraccions de trànsit que es cometin. En una primera fase es vol recopilar informació sobre les marques i models que hi ha al mercat, per la qual cosa des de les diferents cases de cotxes se'ls remet la informació següent: nom de la marca i adreça social a Espanya. Així mateix, per a cada marca es recullen els noms de models del vehicles disponibles i la potència (CV) de cadascun. Cal assenyalar que cada marca es codifica amb un codi i que associat al nom del model podem distingir cadascun dels models que existeixen.

Quan un vehicle nou es matricula es registra la informació de la marca i el model del cotxe, el número de matrícula (7 caràcters alfanumèrics majúscules), el bastidor (17 caràcters alfanumèrics majúscules), la data de matriculació, així com les dades del propietari. D'aquest s'han de conèixer les següents dades: nif, cognoms, nom, data de naixement i domicili complet (carrer, núm., municipi, província i codi postal). Cal tenir en compte que a la DGT vol mantenir la informació actualitzada del propietari, per tant si en algun moment es produeix un canvi de propietari s'ha d'actualitzar a la base de dades, sense perdre informació de la història dels propietaris anteriors junt amb les dates que indiquen el període de propietat, per si de cas es necessiten per tramitar multes antigues. Per facilitar el disseny un mateix propietari no pot poseir el mateix vehicle durant dos períodes diferents. Per la població la manera d'identificar un vechicle és mitjançant la matrícula ja que aquest número ha de ser únic per tots els vechicles i no es pot reutilitzar, però la DGT utilitza el número de bastidor per poder identificar tots els vehicles.

Quan una persona comet una infracció i se li imposa una multa, l'agent pren nota d'una sèrie de dades. En primer lloc, les dades de la persona infractora: nif, nom, cognoms, data de naixement i domicili complet (carrer, núm., municipi, província i codi postal). Si a la infracció hi ha intervingut un vehicle, es necessiten a més, les dades de la seva matrícula, marca i model del vehicle. Cal assenyalar que les multes s'imposen a persones, no a vehicles, ja que, per exemple, es podria imposar una multa a un vianant o a un ocupant d'un vehicle. Tot i que també és cert que en la majoria de les infraccions intervé un vehicle. També han de constar a la multa la data, el número de registre personal de l'agent que ha posat la multa, l'article que ha infringit la persona infractora (4 dígits), el lloc exacte on ha passat la infracció (carretera + quilòmetre concret o adrecça si es tracta d'una infracció en una via urbana) i l'import de la multa. Encara que hi ha una guia dels articles amb les seves descripcions, en aquest moment no es vol encara emmagatzemar aquesta informació a la base de dades. Cada infracció comesa s'identifica amb un número d'expedient únic (9 dígits) i dóna lloc a una única multa.

Setmanalment a la Direcció Central de Trànsit se li envien informes on consta informació del nombre d'infraccions que s'han comès aquesta setmana, agrupades per carretera o per municipi i import i un rànquing dels articles que més s'han infringit.

A la unitat de trànsit a què pertany cada agent que ha imposat una multa se li envia mensualment un llistat de les multes imposades pels seus agents i l'estat en què es troben els expedients (multa pendent, pagada o recorreguda). Aquesta informació és important perquè de tant en tant els agents han de declarar en relació en alguna de les infraccions en què han intervingut, per a això se'ls hi envia una citació via correu electrònic i una carta certificada al seu domicili. També cada cert temps s'obtenen estadístiques per als mitjans de comunicació sobre les característiques de les persones que cometen més infraccions (per trams d'edat, municipi i/o província de residència, etc.) i dels vehicles implicats (marques, models , etc.).

Entre altres coses la DGT vol:

- Crear un llistat de matrícula de vehicle + Nom i cognoms del propietari actual
- Crear un llistat de tots els vehicles d'una província concreta.
![[dgt.png]]
[[Entitat Relacio]]