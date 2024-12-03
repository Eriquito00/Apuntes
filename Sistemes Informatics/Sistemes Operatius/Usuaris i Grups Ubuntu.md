Els grups de linux NO son de tipus contenidor ja que aquests usuaris poden estar a varis grups.
# Usuaris
Per defecte els usuaris de Ubuntu tenen un grup inicial o principal que sera el mateix nom que l'usuari.
adduser (nom)
- crea un usuari amb aquest nom SI AQUEST USUARI NO EXISTIA PREVIAMENT.
adduser --ingroup (grup) (nom)
- crea un usuari amb aquest nom com a grup principal el grup que hem posat EL GRUP HA D'EXISTIR ABANS.
deluser (nomuser)
- elimina l'usuari que li diem i el seu grup principal queda buit tambe esborrara el seu grup principal.
rm -R /home/(nomuser)
- per borrar el directory principal de l'usuari.
deluser --remove-home (nomuser)
- esborra l'usuari i el seu directory principal y si el seu grup queda buit tambe l'esborra.
usermod -L (nomuser) i tambe passwd -l (nomuser)
- dehabilita l'usuari
usermod -U (nomuser) i tambe passwd -u (nomuser)
- habilita l'usuari
usermod -e (any)-(mes)-(dia) (nomuser) i tambe chage (nomuser) -E (any)-(mes)-(dia)
- activa la caducitat de un usuari.
passwd (nomuser)
- canvia la contrasenya de l'usuari
passwd -d (nomuser) i tambe passwd -e (nomuser)
- fer que demani en la primera sessio una nova contrasenya
visudo
- editar a la linea y posar el seguent sota root:
- (nomuser) ALL=(ALL:ALL) ALL

ADDUSER:
- Script en perl.
- Potser que no funcioni en alguna distribucio.
- Crea automaticament la carpeta a /home.
- Demana parametres de text per configuracio.
USERADD:
- Es una compilacio navita de linux.
- Funcionara a totes les distribucions linux.
- No crea la carpeta /home. Si volem fer hem de posar la comanda "-m".
El mateix amb userdel i deluser.
# Grups
addgroup (nom)
- crea un grup amb aquest nom SI AQUEST GRUP NO EXISTIA PREVIAMENT.
id (nomuser)
- fa un petit llistat de tots els grups al que pertany l'usuari AMB LES GID.
(nomgrup) (nomuser)
- ens fa el llistat nomes dels noms del grup al que pertany l'usuari.
usermod -g (nomgrup) (nomuser)
- canvia el grup principal de l'usuari.
deluser (nomuser) (nomgrup)
- elimina l'usuari COM A MEMBRE del grup, els dos seguiran existint pero l'usuari ja no perteneix al grup.
delgrup (nomgrup)
- elimina el grup que li diem.