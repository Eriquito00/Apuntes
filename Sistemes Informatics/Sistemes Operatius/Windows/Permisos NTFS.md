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
Attrib \[(+R, -R, +A, -A, +S, -S, +H, -H)\] "(nom fitxer)"
\[\s\] subdirectoris
\d\] tambe carpetes
Sense posar cap ens mostra els permisos del fitxer.
Sense nom del fitxer actua sobre tots els fitxers.
Tambe funciona a PowerShell.