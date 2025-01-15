# DDL
Data Definition Language.
Si una instruccio es pot executar i no causara cap error s'executaran, INCLUS SI LA INSTRUCCIO ES ESBORRAR LA BASE DE DADES.
# DML
Data Manipulation Language.
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

## Consultes a les taules
Per fer consultes SQL s'utilitza SELECT i 
## Parametres MySQL
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
		
		- HASH: S'utilitza per encriptar les dades en HASH, de forma que amb una petita variacio d'un caracter canvia tota la estructura del HASH, fent practicament imposible sapiguer aquesta dada.

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
	- Podem tambe canviar el nom d'una columna mitjançant la clausula pero hem de tornar a definir la columna.
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
# Contrasenya😳
root:
p@st@n@g@
pere pi:
pastanaga