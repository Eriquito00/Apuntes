# Usuaris
Per defecte els usuaris de Ubuntu tenen un grup inicial o principal que sera el mateix nom que l'usuari.
**adduser (nom)**
- crea un usuari amb aquest nom SI AQUEST USUARI NO EXISTIA PRÈVIAMENT. Aquesta comanda també configura el directori personal, shell i altres paràmetres de l'usuari.

**adduser --ingroup (grup) (nom)**
- crea un usuari amb aquest nom, assignant-li com a grup principal el grup que hem posat. EL GRUP HA D'EXISTIR ABANS.

**rm -R /home/(nomuser)**
- elimina el directori personal de l'usuari que li diem i tot el seu contingut. No elimina l'usuari ni el seu grup principal.

**deluser --remove-home (nomuser)**
- elimina l'usuari especificat i, a més, esborra el seu directori personal i altres fitxers associats. No elimina automàticament el grup principal de l'usuari, encara que quedi buit.

**usermod -L (nomuser)** i també **passwd -l (nomuser)**
- bloquegen l'usuari, desactivant la seva contrasenya. L'usuari no pot iniciar sessió, però el compte, el directori personal i el grup principal queden intactes.

**usermod -U (nomuser)** i també **passwd -u (nomuser)**
- desbloquegen l'usuari prèviament bloquejat amb usermod -L o passwd -l, permetent-li tornar a iniciar sessió.

**usermod -e (any)-(mes)-(dia) (nomuser)** i també **chage (nomuser) -E (any)-(mes)-(dia)**
- configuren una data de caducitat pel compte d'usuari. Després d'aquesta data, l'usuari no podrà iniciar sessió.

**passwd (nomuser)**
- permet canviar la contrasenya de l'usuari. Si no en té, en crea una. També activa opcions com la caducitat de la contrasenya segons el sistema.

**passwd -d (nomuser)** i també **passwd -e (nomuser)**
- passwd -d: elimina la contrasenya de l'usuari, permetent que accedeixi sense contrasenya (si el sistema ho permet).
- passwd -e: força la caducitat immediata de la contrasenya i obliga l'usuari a canviar-la en la pròxima sessió.

**visudo**
- permet editar de manera segura el fitxer sudoers. Per exemple, per fer que un usuari pugui executar ordres amb privilegis d'administrador o forçar un canvi de contrasenya en la primera sessió, afegim:
- - `(nomuser) ALL=(ALL:ALL) ALL`

ADDUSER:
- Script en perl.
- Potser que no funcioni en alguna distribucio.
- Crea automaticament la carpeta a /home.
- Demana parametres de text per configuracio.
USERADD:
- Es una compilacio navita de linux.
- Funcionara a totes les distribucions linux.
- No crea la carpeta /home. Si volem fer hem de posar la comanda "-m". El mateix amb userdel i deluser.
# Grups
**addgroup (nom)**
- crea un grup amb aquest nom SI AQUEST GRUP NO EXISTIA PREVIAMENT.

**id (nomuser)**
- fa un petit llistat de tots els grups als quals pertany l'usuari, **inclosos els noms dels grups i les seves GID** (identificadors de grup).

**groups (nomuser)**
- ens fa el llistat **només dels noms dels grups** als quals pertany l'usuari.

**usermod -g (nomgrup) (nomuser)**
- canvia el grup principal de l'usuari al grup indicat.

**deluser (nomuser) (nomgrup)**
- elimina l'usuari **com a membre** del grup especificat. Tant l'usuari com el grup seguiran existint, però l'usuari ja no pertany al grup.

**delgrup (nomgrup)**
- elimina el grup que li diem. **El grup ha d'estar buit**, és a dir, no pot tenir membres assignats.
# Altres
cat /etc/passwd | cut  -d":" -f1
- mostra tots els usuaris del dispositiu.
cat /etc/group | cut -d":" -f1
- mostra tots els grups del dispositiu.