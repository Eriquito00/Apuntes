# Permisos NTFS
NTFS es el sistema de fitxers de windows, esta basicament a un dispositiu de dades com un HDD i gestiona directoris i fitxers, els permisos d'aquest sistema de fitxers gestiona qui pot crear, modificar, esborrar... cada element.

Exemples de SO i sistemes de fitxers:
- MSDOS -> reconeix FAT12 i FAT16
- Windows 95 -> reconeix FAT12, FAT16 i FAT32
- Windows NT -> reconeix NTFS i FAT

MSDOS i Windows95 estan pensats per treballar com a dispositiu personal per cada persona. Per altre banda Windows NT esta pensat per treballar en xarxa i en entorns multius i necesita un control d'access als elements del sistema.
## Seguretat de FAT
Esta basat en atributs no en permisos.
Cada fitxer o carpeta pot tenir activats els seguents atributs:
- (R)ead Only: indica que l'element nomes pot ser llegit.
- (H)idden: indica que l'element esta ocult a la vista.
- (S)ystem: indica que el fitxer del sistema operatiu.
- (A)rchive: indica que l'element ha estat modificat.
Com no estaba basat en permisos els podia modificar qualsevol usuari per tant no donava seguretat.
## Comanda per gestionar atributs (CMD)
Attrib \[+R | -R], \[+A | -A,] \[+S | -S], \[+H | -H\] "(nom fitxer)"
\[\s\] subdirectoris
\d\] tambe carpetes
Sense posar cap ens mostra els permisos del fitxer.
Sense nom del fitxer actua sobre tots els fitxers.
Tambe funciona a PowerShell.
# Comandes de carpetes i fitxers
## Crear carpetes o fitxers
Per crear fitxers o directoris a powershell podem executar la comanda de new item.

```PowerShell
New-Item -Name "(nom carpeta o fitxer)" `
	-Path "(ruta)" `
	-Value "(contingut del fitxer)" `
	-ItemType file o directory `
	-Force (sobre escriu si ja existia)
```

## Renombrar carpetes o fitxers
Tambe poden renombrar un arxiu amb la seguent comanda introduint el nou nom i la ruta.

```PowerShell
Rename-Item -Path "(ruta al fitxer)" `
	-NewName "(nou nom)"
```
## Esborrar un fitxer o carpeta
Per esborrar un fitxer o carpeta tambe podem eliminar amb segons les conveniencies.

```PowerShell
Remove-Item -Path "(ruta)"
	-Filter //podem aplicar un filtre per eliminar tots els que coincideixin
	-Recursive //si introduim una ruta llarga eliminara totes les carpetes
	-Force //per forzar la eliminacio sense que salti error o haber de confirmar
	-Include 
	-Exclude
```
## Moure un fitxer o carpeta
Serveix per moure un fitxer o carpeta a un altre directory.

```PowerShell
Move-Item -Path "(fitxer)" `
	-Destination "(ruta desti)"
```
## Canviar de directori
Cambia un fitxer o carpeta a un altre directori que introduim a la ruta

```PowerShell
Set-Location -Path "(ruta)"
```

## Mostrar carpetes i fitxers
Podem mostrar tots els fitxers i/o carpetes amb les seguents comandes segons les nostres necesitats.

```PowerShell
//Arbre de totes les carpetes 
tree
```

```PowerShell
//Arbre de totes les carpetes i fitxers
tree /f
```
## Permisos NTFS basics
- Lectura: ens permet en cas de fitxer llegirlo y en cas de carpeta els seus elements.
- Lectura i execucio: ens permet tots els permisos de lectura y poder executar el fitxer si es executable.
- Escriptura: ens permet escriure dins del fitxer.
- Modificar: Lectura i execucio, escriptura y a mes poder eliminar el fitxer.
- Control total: Totes les de modificar i poder gestionar els permisos.
## Creator Owner
Es un permis especial que nomes el te l'usuari que ha creat l'arxiu o carpeta, es mes conegut com una variable que ofereix al creador certes avantatges.
## Permisos NTFS avançats
Son els permisos reals NTFS. Els altres eren agrupacions de permisos NTFS sota un unic nom. Els permisos son els seguents:
- Control Total: Da qualquier permiso a carpetas o archivos.
- Atravesar carpeta / ejecutar archivo: Permet accedir a carpetes dins de la carpeta i executar arxius executable.
- Mostrar carpeta / leer datos: Mostra el contingut de la carpeta i llegir les dades dels fitxers.
- Leer atributos: Llegir els atributs.
- Leer atributos extendidos: Llegir els atributs estesos
- Crear archivos / escribir datos: Permet crear archius i escribir als fitxers.
- Crear carpetas / anexar datos: Permet crear carpetes i afegir linies als fitxers.
- Escribir atributos: Permite editar atributos.
- Escribir atributos extendidos: Permite editar atributos extendidos.
- Eliminar subcarpetas y archivos: Permite eliminar subcarpetas y archivos de la carpeta i subcarpetas.
- Eliminar: Permite eliminar archivos y carpetas.
- Permisos de lectura: Ofrece permisos de lectura.
- Cambiar permisos: Permite cambiar los permisos.
- Tomar posesion: Agafar la propietat d'un arxiu o carpeta.
## Permisos ICACLS
Amb aquesta comanda CMD podem consultar certa informacio, ens serveixen per sapiguer tambe si les carpetes, fitxers o ella mateixa heretara certs permisos.

```CMD
//Donar permisos
icacls (nom ficher) /grant (nom usuari): "((permisos))"
```

Aqui podem veure els permisos que podem oferir amb icacls
- N - sin acceso
- F - acceso total
- M - acceso de modificacion
- RX - acceso de lectura y ejecuci¢n
- R - acceso de solo lectura
- W - acceso de solo escritura
- D - acceso de eliminacion
- I - heredados

Aqui podem veure els permisos AVANÇATS que podem oferir amb icacls
X - ejecutar/atravesar
RD - leer datos/lista de directorio
RA - leer atributos
REA - leer atributos extendidos
WD - escribir datos/agregar archivo
AD - anexar datos/agregar subdirectorio
WA - escribir atributos
WEA - escribir atributos extendidos
DC - eliminar secundario
DE - eliminar
RC - control de lectura
WDAC - escribir DAC
WO - tomar posesion

I tambe a on poden accedir depenent dels permisos que donem i a qui els hi donem:
- OI: significa que la carpeta que el tingui ho tindran les carpetes dins d'aquesta carpeta.
- CO: significa que la carpeta que el tingui ho tindran els fitxers de dins d'aquesta carpeta.
- IO: significa que la carpeta te el permis aquesta mateixa carpeta NO tindra els permisos.
### Qui pot cambiar els permisos?
- Propietari
- Administradors del grup administradors
- Usuaris i grups amb permisos control total
- Usuaris i grups amb el PE cambiar permisos
- Usuaris i grups amb el PE tomar posesion
### Qui pot obtenir la possesio?
- Qualsevol membre del grup administradors
- Usuaris i grups amb permis control total
- Usuaris i grups amb el PE cambiar permisos i posarse com control total
- Usuaris amb algun permisos anteriors executant la seguent comanda cmd "TAKEOWN /f (fitxer)".
### Qui pot donar la possesio?
- Qualsevol membre del grup administradors
- Usuaris amb el permis anterior executant amb icacls /setowner