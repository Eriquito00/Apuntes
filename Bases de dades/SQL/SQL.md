# DDL
Data Definition Language.
## Parametres MySQL DDL
CREATE:
- S'utilitza per la creacio de una base de dades, una taula o altres.
	DATABASE:
	![[Pasted image 20250109083848.png]]

	TABLE:
	- Tambe podem afegir les columnes a la taula nomes crearla de forma que ja quedi una taula estructurada desde un inici.
	![[Pasted image 20250113182814.png]]

	VIEW:
	- Tambe podem crear una vista que es una consulta a una taula per obtenir la informacio d'unes columnes especifiques.
		![[Pasted image 20250115182850.png]]
		SELECT:
		- Normalment s'utilitzen junt amb VIEW per crean una vista amb certes dades d'una taula, en aquest cas es crea una vista amb les dades de les taules jugador_id, nom i punts:
		![[Pasted image 20250115182850.png]]
		- Tot i que si a la vista volem que les columnes tinguin un nom mes descriptiu:
		![[Pasted image 20250115191530.png]]

	INDEX:
	- Els index es poden crear als camps que mes es consulten a la nostre base de dades, de forma que quan es consultin es fara d'una forma mes rapida.
		![[Pasted image 20250115191758.png]]

	- Aqui podem veure dos index, la diferencia, a part de les dades sobre les que es creen els index, es que un utilitza el sistema BTREE y l'altre HASH.
		- BTREE: S'utilitza per crear un arbre sobre les dades de la columna per anar fent descartacions i poder les dades que es demanen d'una forma mes rapida.
		![[Pasted image 20250116153058.png]]

		- HASH: S'utilitza per encriptar les dades en HASH, de forma que amb una petita variacio d'un caracter canvia tota la estructura del HASH, fent practicament imposible sapiguer aquesta dada.
		![[Pasted image 20250116153108.png]]

	- \[WITH \[CASCADED | LOCAL] CHECK OPTION]
		- WITH CHECK OPTION o WITH  CHECK OPTION CASCADED: Asegura que qualsevol dada nova o actualitzada compleixi les condicions definides a la vista i les de alguna vista superior en cas d'haver fet una vista a una vista.
		
		- WITH LOCAL CHECK OPTION: Asegura que la vista compleixi les condicions de la vista actual pero no les condicions de una vista superior en cas d'haver fet alguna vista d'una vista.

USE:
- Sutilitza per seleccionar la base de dades on executarem les sentencies.
![[Pasted image 20250109083927.png]]

DROP:
- Esborrar una taula o la base de dades tant la estructura com el contingut.
![[Pasted image 20250109083958.png]]
![[Pasted image 20250109084018.png]]
![[Pasted image 20250115182953.png]]

TRUNCATE:
- Esborra el contingut de la taula pero la estructura la segueix mantenint.
![[Pasted image 20250109084054.png]]

DELETE:
- Esborrar una columna de una taula.
![[Pasted image 20250115184247.png]]

DESCRIBE:
- Ens mostra la taula i tota la informacio de cada columna.
![[Pasted image 20250109084222.png]]

ALTER:
- Editar una columna de una taula, afegir, esborrar o editar.

	ADD:
	- Afegeix noves coses a una taula com un constraint, una columna... Tambe podem utilitzar FIRST per afegir la columna al inici, AFTER despres de una que especifiquem i si no posem res per defecte ho afegira al final.
	![[Pasted image 20250109084521.png]]

	MODIFY:
	 - Permet canviar el tipus de dades, la mida i el valor per defecte d'una columna.
	![[Pasted image 20250109084949.png]]

	CHANGE:
	- Fa exactament el mateix que MODIFY pero tambe ens permet canviar el nom de la columna.
	![[Pasted image 20250115183740.png]]

	DROP:
	- Les claus primaries quan fem un drop s'esborra la clau primaria y el seu index a la vegada.
	![[Pasted image 20250109090242.png]]

	- Si fem DROP a una FOREIGN KEY, l'index de la clau forana no s'esborrara, per tant haurem de fer un DROP al INDEX de la clau forana (l'index te el mateix nom que la clau forana).
	![[Pasted image 20250109090911.png]]

	RENAME:
	- Directament podem posar RENAME i el nou nom de la taula que volem.
	![[Pasted image 20250113182341.png]]

	VIEW:
	- S'utilitza per editar la informacio que es mostra a una view.
	![[Pasted image 20250115184024.png]]
# DML
Data Manipulation Language.
## Parametres MySQL DML
INSERT:
- Insereix nova informacio a una taula sobre diferents columnes que podem seleccionar.
![[Pasted image 20250116164449.png]]

DELETE:
- Si fem un delete sol eliminarem totes les dades la taula. Pero tambe podem eliminar files si compleixen alguna condicio com la que estan a l'exemple.
![[Pasted image 20250116164516.png]]

UPDATE:
- El UPDATE serveix per editar les dades d'alguna columna de la taula, per exemple aqui podem veure que si el id de localitzacio es 1700 afegirem un "\_H", el CONCAT() es equiparable a un +=, i tambe podem veure si es NULL utilitzant IS o si no es null IS NOT.
![[Pasted image 20250116164657.png]]
![[Pasted image 20250116170207.png]]

SELECT:
- Un select es compon per els atributs de la taula que volem veure, en aquest exemple s'agafen dades de la taula empleats i s'agafaran les dades dels camps nom, cognoms i deparatment_id sempre i quan el departament_id de l'empleat sigui 60, tambe tenim el ORDER BY per dir per quin camp volem ordenar i podem utilitzar DESC per que sigui descendent i ASC perque sigui ascendent.
	![[Pasted image 20250116170308.png]]

	FROM: 
	- S'utilitza per indicar de quina taula provenen les dades de les columnes indicades.
	![[Pasted image 20250123112816.png]]
	- Si tenim algun valor repetit i no volem els repetits podem utilitzar DISTINCT.
	![[Pasted image 20250123113007.png]]
	- Tambe podem crear una columna que no es guardara amb alguna operacio aritmetica i tambe podem fer-li que mostri un nom personalitzar a la columna.
	![[Pasted image 20250123113135.png]]
	- Tant al inici del SELECT com al WHERE podem utilitzar operadors aritmetics com el '<', '>', '=', '!=', entre altres.
	![[Pasted image 20250123113423.png]]
	- SOBRETOT si volem comprovar NULL o NOT NULL utilitzarem IS no '='. 
	![[Pasted image 20250123113619.png]]
	- A mes a mes tambe podem utilitzar rangs amb BETWEEN, en els quals tant el inicial com el final estan inclosos, igual que NULL podem utilitzar NOT BETWEEN que no incluira ni el minim ni maxim.
	![[Pasted image 20250123113723.png]]
	- Tambe podem utilitzar IN per dir que ens retornin el que estan exactament en aquest valor.
	![[Pasted image 20250123113940.png]]
	- Si volem un missatge quan hi hagi un NULL a una columna podem utilitzar IFNULL().
	![[Pasted image 20250123114428.png]]
	- Si volem fer una cerca d'un patro, com un regex, podem utilitzar LIKE. Podria ser que depenent com tenim configurada la base de dades ens mostrara els valors que començen per la lletra o nomes els que comencin per la lletra MAJUSCULA o minuscula. Tambe tenim RLIKE per regular expresions.
	![[Pasted image 20250123114613.png]]
	![[Pasted image 20250123115116.png]]
	- A MySql no tenim una funcio per crear una columna amb la primera en majuscula y la resta en minuscula pero podem utilitzar aquesta funcio,  'CONCAT(UPPER(LEFT(nom,1)),LOWER(SUBSTRING(nom,1)))'.
	![[Pasted image 20250123122537.png]]
	- A MySql tampoc podem fer un random entre un numero i un altre, pero podem utilitzar la seguent funcio, RAND() \* (max - min + 1).
	![[Pasted image 20250123144034.png]]
	- Una altre funcio que podem utilitzar es una semblant a fer un if que es CASE. Amb els diferents WHEN que serien els respectius else if y el ultim que es ELSE, aquesta sentencia finalitza amb END AS (nom del camp).
	![[Pasted image 20250129205312.png]]
## Altres funcions per SELECT
- CONCAT(text,text,text...): Retorna un String amb tots els textos que he introduit.
- LENGTH(text): Retorna la longitud del String.
- LOWER(text) i LCASE(text): Retorna el String en minuscules.
- UPPER(text) i UCASE(text): Retorna el String en MAJUSCULES.
- LEFT(text,length): Retorna els (length) caracters començant per l'esquerra.
- RIGHT(text,length): Retorna els (length) caracters començant per la dreta.
- MID(text, pos, len), SUBSTRING(text, pos), SUBSTRING(text, pos, len): S'utilitza per obtenir porcions d'una cadena de text.
- INSTR(text, sub_text): Retorna la posició de la primera aparició de sub_text dins a text.
- LOCATE(sub_text, text), LOCATE(sub_text, text, pos): S'utilitza per obtenir porcions d'una cadena de text. A més podem indicar la posició a iniciar la cerca.
- LPAD(text, len, padtext): Retorna el string text omplint-lo amb el text padtext per l'esquerra fins obtenir la longitud len.
- RPAD(text,len,padtext): Retorna el string text omplint-lo amb el text padtext per la dreta fins obtenir la longitud len.
- TRIM(text), LTRIM(text), RTRIM(text): Retorna el text traient els possibles espais en blanc d'esquerra i dreta.
- REPEAT(text, count): Retorna un string de longitud count repetint el string text.
- SPACE(len): Retorna un string de longitud len només format per espais en blanc.
- REPLACE(text, from, to): Retorna el string text reemplaçant les ocurrències del string from per el string to.
- REVERSE(text): Retorna string text amb l'orde dels caràcters en format invers.
- IFNULL(camp, substitucio): Comprova si el valor es NULL i si es NULL posa el valor que substitueix.
### Funcions de dates
- YEAR(camp): Agafa l'any d'una data.
- MONTH(camp): Agafa el mes d'una data.
- DAY(camp): Agafa el dia d'una data.
- CURDATE(): Obte la data del dia actual.
# Dades MySQL
Les dades a MySQL es poden declarar y crear les columnes d'una taula, tambe crear les Primary Key, Foreign Key, Constraint, Referencies... Per explicar agafarem inicialment aquesta taula.
## Creacio i modificacio de taules
![[Pasted image 20250113182905.png]]
![[Pasted image 20250113195834.png]]

Entre altres coses d'aquesta taula podem veure algunes caracteristiques sobre algunes columnes de la taula. Com UNSIGNED, NOT NULL o AUTO_INCREMENT, aqui podem veure per a que serveix cadascun:

NUMEROS ENTERS:
- BIGINT: Entre -9.000.000.000.000.000.000 i 9.000.000.000.000.000.000.
- INT: Entre -2.000.000.000 i 2.000.000.000.
- SMALLINT: Entre -32.000 i 32.000.
- TINYINT: Entre -128 i 127.

NUMEROS DECIMALS:
- FLOAT: Te una precicio de 7 digits.
- DOUBLE: Te una precicio entre 15 i 16 digits.

STRINGS:
- CHAR(): S'utilitza per valors amb longitud fixe, com el DNI que sempre son 9 caracters.
- VARCHAR(): S'utilitza per valors amb longitud dinamica, com el nom d'una persona.

CONSTRAINTS:
- CONSTRAINT: S'utilitza per crear una "recla" sobre algun camp.
	- PRIMARY KEY: Selecciona quina es la columna o columnes que seran la PK de la taula.
	- FOREIGN KEY: Selecciona quina sera la columna que tindra la informacio de la FK.
	- CHECK: Verifica les dades que s'hagin introduit a aquesta columna, com un valor que hagi d'estar entre 0 i 100 (en SQL no funciona per ara).
	- UNIQUE: S'utilitza per fer que els valors d'aquesta columna no es pugui repetir amb un altre, com el DNI que es unic per cada persona.
- REFERENCES: S'utilitza per fer una referencia a la columna d'una altre taula.
	- ON UPDATE: Quan les dades s'acctualitzin.
	- ON DELETE: Quan les dades s'esborrin.
		- CASCADE: Basicament que quan esborrem o actualitzem les dades, si estan enllaçades a altres taules tambe s'esborrin.

ALTRES TIPUS DE DADES:
- YEAR: Guarda el valor d'un any.
- DATE: Guarda el valor d'una data.

CARACTERISTIQUES DE COLUMNES:
- UNSIGNED: Provoca que no hi puguin haver negatius i en cas dels valors de numero enters "dupliquen el seu limit", per exemple TINYINT es entre -128 i 127 i amb UNSIGNED es entre 0 i 255.
- NOT NULL: Fa que en aquesta columna no hi pugui haver un valor null.
- AUTO_INCREMENT: Fa que aquest valor sigui autoincremental.
- ENUM(): Ens fa un "llistat" del que podem seleccionar, per exemple "maduixa", "cirera", "poma".
- GENERATED ALWAYS AS(): Serveix per fer un atribut calculat entre altres atributs d'altres columnes.
- DEFAULT: Serveix per tenir un valor per defecte als atributs de la columna.
# Contrasenya😳
root:
p@st@n@g@
pere pi:
pastanaga