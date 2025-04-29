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
