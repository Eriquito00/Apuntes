# Usuaris i Grups Ubuntu
# Usuaris
Per defecte els usuaris de Ubuntu tenen un grup inicial o principal que sera el mateix nom que l'usuari.

**adduser (nom)**
- crea un usuari amb aquest nom SI AQUEST USUARI NO EXISTIA PRÈVIAMENT. Aquesta comanda també configura el directori personal, shell i altres paràmetres de l'usuari.
![](/Imatges/Pasted_image_20250202164651.png)

**adduser --ingroup (grup) (nom)**
- crea un usuari amb aquest nom, assignant-li com a grup principal el grup que hem posat. EL GRUP HA D'EXISTIR ABANS.
![](/Imatges/Pasted_image_20250202164920.png)

**rm -R /home/(nomuser)**
- elimina el directori personal de l'usuari que li diem i tot el seu contingut. No elimina l'usuari ni el seu grup principal.
![](/Imatges/Pasted_image_20250202164947.png)

**deluser --remove-home (nomuser)**
- elimina l'usuari especificat i, a més, esborra el seu directori personal i altres fitxers associats. No elimina automàticament el grup principal de l'usuari, encara que quedi buit.
![](/Imatges/Pasted_image_20250202165052.png)

**usermod -L (nomuser)** i també **passwd -l (nomuser)**
- bloquegen l'usuari, desactivant la seva contrasenya. L'usuari no pot iniciar sessió, però el compte, el directori personal i el grup principal queden intactes.
![](/Imatges/Pasted_image_20250202165148.png)

**usermod -U (nomuser)** i també **passwd -u (nomuser)**
- desbloquegen l'usuari prèviament bloquejat amb usermod -L o passwd -l, permetent-li tornar a iniciar sessió.
![](/Imatges/Pasted_image_20250202165212.png)

**usermod -e (any)-(mes)-(dia) (nomuser)** i també **chage (nomuser) -E (any)-(mes)-(dia)**
- configuren una data de caducitat pel compte d'usuari. Després d'aquesta data, l'usuari no podrà iniciar sessió.
![](/Imatges/Pasted_image_20250202165313.png)

**passwd (nomuser)**
- permet canviar la contrasenya de l'usuari. Si no en té, en crea una. També activa opcions com la caducitat de la contrasenya segons el sistema.
![](/Imatges/Pasted_image_20250202165349.png)

**passwd -d (nomuser)** i també **passwd -e (nomuser)**
- `passwd -d`: elimina la contrasenya de l'usuari, permetent que accedeixi sense contrasenya (si el sistema ho permet).
![](/Imatges/Pasted_image_20250202165446.png)

- `passwd -e`: força la caducitat immediata de la contrasenya i obliga l'usuari a canviar-la en la pròxima sessió.
![](/Imatges/Pasted_image_20250202165507.png)

**visudo**
- permet editar de manera segura el fitxer sudoers. Per exemple, per fer que un usuari pugui executar ordres amb privilegis d'administrador o forçar un canvi de contrasenya en la primera sessió, afegim:
![](/Imatges/Pasted_image_20250202165634.png)

- `(nomuser) ALL=(ALL:ALL) ALL`
![](/Imatges/Pasted_image_20250202165600.png)

### ADDUSER:
- Script en Perl.
- Potser que no funcioni en alguna distribució.
- Crea automàticament la carpeta a `/home`.
- Demana paràmetres de text per configuració.
![](/Imatges/Pasted_image_20250202170123.png)

### USERADD:
- És una compilació nativa de Linux.
- Funcionará a totes les distribucions Linux.
- No crea la carpeta `/home`. Si volem fer-ho, hem de posar la comanda `-m`. El mateix amb `userdel` i `deluser`.
![](/Imatges/Pasted_image_20250202170135.png)

# Grups

**addgroup (nom)**
- crea un grup amb aquest nom SI AQUEST GRUP NO EXISTIA PRÈVIAMENT.
![](/Imatges/Pasted_image_20250202170234.png)

**addgroup (usuari) (grup)**
- afegeix l'usuari indicat al grup que hem dit.
![](/Imatges/Pasted_image_20250202170552.png)

**id (nomuser)**
- fa un petit llistat de tots els grups als quals pertany l'usuari, **inclosos els noms dels grups i les seves GID** (identificadors de grup).
![](/Imatges/Pasted_image_20250202170349.png)

**groups (nomuser)**
- ens fa el llistat **només dels noms dels grups** als quals pertany l'usuari.
![](/Imatges/Pasted_image_20250202170725.png)

**usermod -g (nomgrup) (nomuser)**
- canvia el grup principal de l'usuari al grup indicat.
![](/Imatges/Pasted_image_20250202170805.png)

**deluser (nomuser) (nomgrup)**
- elimina l'usuari **com a membre** del grup especificat. Tant l'usuari com el grup seguiran existint, però l'usuari ja no pertany al grup.
![](/Imatges/Pasted_image_20250202171312.png)

- En cas que sigui el grup principal, no ho farà. Haurem de donar-li un altre grup com a principal i després eliminar-lo.
![](/Imatges/Pasted_image_20250202170854.png)

**delgrup (nomgrup)**
- elimina el grup que li diem. **El grup ha d'estar buit**, és a dir, no pot tenir membres assignats.
![](/Imatges/Pasted_image_20250202171349.png)

# Altres

`cat /etc/passwd | cut  -d":" -f1` o `getent passwd | cut -d":" -f1`
- mostra tots els usuaris del dispositiu.
![](/Imatges/Pasted_image_20250202171559.png)

`cat /etc/group | cut -d":" -f1` o `getent group | cut -d":" -f1`
- mostra tots els grups del dispositiu.
![](/Imatges/Pasted_image_20250202171735.png)
