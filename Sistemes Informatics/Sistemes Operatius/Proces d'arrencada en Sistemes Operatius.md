# Windows
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
- "bootmgr" carrega en RAM i executa el fitxer winload.exer del SO escollit. Cada SO te un fitxer winload.exe associat.

6. winload.exe acaba de carregar els moduls que falten del SO, fins arribar a la pantalla de benvinguda o de logon.
- Benvinguda es quan surt el fons amb l'hora i logon es quan ens demana la contraseña.

# Ubuntu
Com arranca Ubuntu 22.04 LTS BIOS MBR GRUB 2:
1. Engeguem el PC amb el boto Power. BIOS dona el control al HDD, concretament al MBR.
2. MBR ha estat modificat per Linux quan l'hem instalat. Dins seu esta el contingut "boot.img". Aquest codi de programa es coneix com a "Fase 1".
3. "boot.img" carrega el codi "core.img" conegut com a "Fase 1.5" que esta guardat en una particio propia. "boot.img" no comprova quina es la particio activa. "core.img" carrega el "/boot/grub" conegut com a "Fase 2" ubicat en la particio de Ubuntu.
4. Aquesta Fase 2 s'encarrega de:
	- mostrar el menu de GRUB
	- carrega el kernel del SO
	- li cedeix el control al SO
	En  sda2 trobem una particio del sistema EFI de 512MiB pero no fa res si arranquem BIOS/MBR.