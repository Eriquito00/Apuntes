# Usuaris
Per defecte els usuaris de Ubuntu tenen un grup inicial o principal que sera el mateix nom que l'usuari.
adduser (nom)
- crea un usuari amb aquest nom SI AQUEST USUARI NO EXISTIA PREVIAMENT.
adduser --ingroup (grup) (nom)
- crea un usuari amb aquest nom com a grup principal el grup que hem posat EL GRUP HA D'EXISTIR ABANS.

ADDUSER:
- Script en perl.
- Potser que no funcioni en alguna distribucio.
- Crea automaticament la carpeta a /home.
- Demana parametres de text per configuracio.
USERADD:
- Es una compilacio navita de linux.
- Funcionara a totes les distribucions linux.
- No crea la carpeta /home. Si volem fer hem de posar la comanda "-m".
# Grups