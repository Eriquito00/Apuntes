# Proces d'arrencada
## Windows
Com arranca Windows Vista MBR BIOS endavant:
1. Donem al boto per encendre.

2. BIOS estava esperant a que presionem el boto.
- Comença a engegar components i fer les comprovacions. 
- BIOS dona el control al dispositiu que esta preparat per arrencar segons l'ordre. (Normalment el primer es el HDD).

3. BIOS dona el control al HDD seleccionat
- Carrega en la RAM el contingut en el 1r sector i executa el programa que conte.
- Aquest programa te acces a la taula de particions.
- La llegeix per sapiguer quina es la particio activa i en quina posicio comença.
- Com sap on comença, sap on esta el seu boot-sector, que el carrega a la RAM i l'executa.

4. El boot-sector busca el fitxer "bootmgr" EN CAS DE WINDOWS en l'arrel de la particio activa, el carrega en RAM i l'executa.

5. "bootmgr" llegeix el fitxer BCD que esta a la carpeta BOOT en la mateixa particio. BCD es un fitxer de configuracio, no es executable.
- BCD li diu a "bootmgr" quants sistemes operatius Windows hi ha i les preferencies d'arrencada.
- Amb la informacio del BCD, "bootmgr" mostra la llista dels SO instalats i demana escollirne un durant uns segons. Si nomes tenim 1 SO Windows no cal mostrar la llista.
- "bootmgr" carrega en RAM i executa el fitxer winload.exe del SO escollit. Cada SO te un fitxer winload.exe associat.

6. winload.exe acaba de carregar els moduls que falten del SO, fins arribar a la pantalla de benvinguda o de logon.
- Benvinguda es quan surt el fons amb l'hora i logon es quan ens demana la contraseña.

## Ubuntu
Com arranca Ubuntu 22.04 LTS BIOS MBR GRUB 2:
1. Engeguem el PC amb el boto Power. BIOS dona el control al HDD, concretament al MBR.

2. MBR ha estat modificat per Linux quan l'hem instalat. Dins seu esta el contingut "boot.img". Aquest codi de programa es coneix com a "Fase 1".

3. "boot.img" carrega el codi "core.img" conegut com a "Fase 1.5" que esta guardat en una particio propia. "boot.img" NO comprova quina es la particio activa. "core.img" carrega el "/boot/grub" conegut com a "Fase 2" ubicat en la particio de Ubuntu.

4. Aquesta Fase 2 s'encarrega de:
- mostrar el menu de GRUB
- carrega el kernel del SO
- li cedeix el control al SO

En  sda2 trobem una particio del sistema EFI de 512MiB pero no fa res si arranquem BIOS/MBR.
***
- LBA 0: Ubuntu amb EFI GPT te un legacy MBR que es conserva per tenir compatibilitat amb programes antics.

- LBA 1: Capçalera del GPT que defineix els blocs de disc que pot usar l'usuari. Defineix la quantitat de particions que s'han creat i la capacitat de cadascuna.

- LBA 2: Taula de particions que diu que cada particio ocupa 128 bytes per tant maxim podra tenir 128 particions. Aquesta limitacio en teoria nomes es per Windows pero per Linux en teoria son infinites.

- Ultims 33 LBA: Copia de seguretat GPT.

El codi per carregar el SO no esta al GPT, com UEFI pot accedir a tot el disc el codi esta ubicat a la particio ESP (Efi System Partition).

Com arranca Ubuntu 22.04 LTS EFI GPT GRUB 2:
1. Engeguem el PC amb el boto i UEFI dona el control directament al HDD concretament al fitxer "grubx64.efi" de la particio ESP.

2. "grubx64.efi" es el bootloader del grub, el grub esta a la propia particio de Ubuntu (/boot/grub). En aquesta part es fa la Fase 1 i la Fase 1.5.

3. Aquest grub es l'encarregat de:
- mostra el menu de grub.
- carrega el kernel del SO.
- finalment pasa el control al kernel carregar.

lsblk: llista els dispositius muntats
- lsblk -f /dev/sda: per saber quines particions tenim i com estan muntades.

df: informe del sistema de fitxers
- df /carpeta: per saber en quina particio esta muntada la carpeta.

Tots els dispositius de Ubuntu estan situats a /dev.
### Unitats en Linux
fd0 o fd1: disquetera floppy.
hda0, hda1...: particions dels discs durs HDD.
hdb0, hdb1...: discs durs HDD.
sda0, sda1...: discs durs sata o scsi.
scd0, scd1...: CD scsi o sata.