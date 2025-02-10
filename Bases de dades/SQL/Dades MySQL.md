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