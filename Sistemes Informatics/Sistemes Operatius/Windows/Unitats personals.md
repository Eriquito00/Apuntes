# Unitats personals
- Son unitats propies i personals per cada usuari.
- La configuracio es fara a l'administrador mai l'usuari a diferencia de les unitats de xarxa.
- La unitat sortira a cada dispositiu del domini on l'usuari inici sesio.
- Cada unitat personal es privada per cada usuari.

Hem d'anar amb cuidado perque no hi hagi cap permis NTFS per todos, usuarios... ja que no ens interesa que puguin tenir access algun altre usuari que no sigui el que te la unitat personal. Nomes hauriem de tenir els permisos:
- Control total a administradors
- Com a minim access a l'usuari destinat

Tenint en compte que la carpeta esta creada previament podem crear una unitat personal per comandes podem executar la seguent comanda.

En el meu cas creare directament al disc E: una unitat que es diu Personals i donant access total a tots.

```POWERSHELL
New-SmbShare -Name Personals -Path E:\personals\ -FullAccess todos
```

Despres podem crear dins d'aquesta carpeta compartida altres carpetes per cada usuari i donarli permisos manualment i eliminar els permisos que siguin heredats de la seguent forma.

```POWERSHELL
//crear carpeta amb nom del usuari
New-Item -Name (nom user) -ItemType directory -Path (ruta)

//donar permisos al usuari que volem
icacls .\(nom carpeta)\ (nom usuari) /grant (nom usuari):"((permisos))"

//treure permisos heretats
icacls (nom carpeta) /inheritance:r

//treure altre permis no heretat pero que no ens interesa
icacls (nom carpeta) /remove "(usuari o grup)"
```

Per fer-ho per entorn grafic podem anar a administracio de equips del servidor i anar a carpetes compartides y a recursos compartits.

![](../../../Imatges/Pasted%20image%2020250526114847.png)

Aqui podem tots els recursos que hi ha incloyent l'anterior creat per comandes.

![](../../../Imatges/Pasted%20image%2020250526115013.png)