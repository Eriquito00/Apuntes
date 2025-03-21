# JDBC
Amb JDBC podem connectarnos mitjançant JAVA amb una BBDD per fer consultes, obtenir informacio, fer cambis o el que volguem amb la nostre BBDD, en el meu cas utilitzare JAVA amb JDBC i una BBDD SQLite.
## Metodes importants
- Connection: s'utitza per connectarnos amb la base de dades per poder fer les consultes.
- ResultSet: s'utilitza per obtenir els registres de la base de dades per poder pasarlos a la nostre aplicacio.
- ResultSetMetaData: s'utilitza per obtenir les metadades de les dades, si es int, string, float...
- Statement: s'utilitza per fer consultes planes, es a dir obtenir dades amb una consulta construida i estatica que no te id.
- PreparedStatement: s'utilitza per poder posar identificadors i poder fer consultes mes personalitzades, es a dir, que la funcio de consultes ens serveixi per consultar taules diferents.
## CRUD i DAO
CRUD son les sigles mes importants sobre les accions que s'utilitzen quan treballem amb bases de dades:
- Create: creacio de les dades.
- Read: llegir les dades.
- Update: actualitzar les dades.
- Delete: eliminar les dades.

DAO esta entre la nostre base de dades i el que seria el nostre controlador, es a dir seria el nostre Model que ens ajuda a connectar les consultes que es fan al nostre controlador i ferles a la nostre base de dades.

Basicament tindre una Classe DAO on farem un implements CRUD, les funcions que ens permetran tractar les dades, i despres segons el programa farem una modificacio, per exemple si estem tractant productes farem un ProducteDAO per acabar de fer aquestes modificacions i tractar les dades a la taula corresponent.