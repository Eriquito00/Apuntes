a# DDL
Data Definition Language.
Si una instruccio es pot executar i no causara cap error s'executaran, INCLUS SI LA INSTRUCCIO ES ESBORRAR LA BASE DE DADES.
# DML
Data Manipulation Language.
# Parametres MySQL
CREATE:
- S'utilitza per la creacio de una base de dades, una taula o altres.

![[Pasted image 20250109083848.png]]
![[Pasted image 20250109083912.png]]

USE:
- Sutilitza per seleccionar la base de dades on executarem les sentencies.

![[Pasted image 20250109083927.png]]

DROP:
- Esborrar una taula o la base de dades tant la estructura com el contingut.

![[Pasted image 20250109083958.png]]
![[Pasted image 20250109084018.png]]

TRUNCATE:
- Esborra el contingut de la taula pero la estructura la segueix mantenint.

![[Pasted image 20250109084054.png]]

DELETE:
- Esborrar una columna de una taula.



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

	

	DROP:
	- Esborra la columna totalment, no es pot revertir.

	- Les claus primaries quan fem un drop s'esborra la clau primaria y el seu index a la vegada.

	![[Pasted image 20250109090242.png]]

	- Si fem DROP a una FOREIGN KEY, l'index de la clau forana no s'esborrara, per tant haurem de fer un DROP al INDEX de la clau forana (l'index te el mateix nom que la clau forana).

	![[Pasted image 20250109090911.png]]

# Dades MySQL
Les dades a MySQL es poden declarar y crear les columnes d'una taula, tambe crear les Primary Key, Foreign Key, Constraint, Referencies...
# Contrasenya😳
root:
p@st@n@g@
pere pi:
pastanaga