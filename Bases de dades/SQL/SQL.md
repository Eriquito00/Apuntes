# DDL
Data Definition Language.
Si una instruccio es pot executar i no causara cap error s'executaran, INCLUS SI LA INSTRUCCIO ES ESBORRAR LA BASE DE DADES.
# DML
Data Manipulation Language.
# Parametres MySQL
DROP:
- Esborrar una taula o la base de dades tant la estructura com el contingut.

TRUNCATE:
- Esborra el contingut de la taula pero la estructura la segueix mantenint.

DELETE:
- Esborrar una columna de una taula.

DESCRIBE:
	- Ens mostra la taula i tota la informacio de cada columna.

ALTER:
- Editar una columna de una taula, afegir, esborrar o editar.

	ADD:
	- Afegeix noves coses a una taula com un constraint, una columna...

	MODIFY:
	 - Permet canviar el tipus de dades, la mida i el valor per defecte d'una columna.

	CHANGE:
	- Podem tambe canviar el nom d'una columna mitjançant la clausula pero hem de tornar a definir la columna.

	DROP:
	- Esborra la columna totalment, no es pot revertir.
	- Si fem DROP a una FOREIGN KEY, l'index de la clau forana no s'esborrara, per tant haurem de fer un DROP al INDEX de la clau forana (l'index te el mateix nom que la clau forana).
	- Les claus primaries quan fem un drop s'esborra la clau primaria y el seu index a la vegada.
# Contrasenya😳
root:
p@st@n@g@
pere pi:
pastanaga