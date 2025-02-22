# Llibreria apache commons Java
La principal caracteristica rellevant d'aquesta llibreria es que es RECURSIVA per tant si creem algun directori o fitxer si les anteriors carpetes no existeixen les creara tambe.
## Crear Directoris
Per crear un directory podem utilitzar "FileUtils.forceMkdir(carpeta)" per crear la carpeta y en cas de que les predecesores no existeixin les crea tambe.

![](../../../../Imatges/Pasted%20image%2020250210163438.png)
## Esborrar un directory
Esborra un directory o un fitxer utilitzant "FileUtils.deleteDirectory(fitxer)" o "FileUtils.deleteFile(fitxer)". Aqui tenim un exemple del directory:

![](../../../../Imatges/Pasted%20image%2020250210163057.png)
## Copia de contingut
Amb aquesta llibreria podem fixar un origen i un desti per copiar y pegar una serie de carpetes a un altre.

![Llibreria Apache Commons Java](/Imatges/Pasted%20image%2020250201205333.png)

D'aquesta forma podem copiar el contingut d'una carpeta a un altre. Donant la carpeta d'origen i la de desti.
## Crea Fitxers
Per crear fitxers podem utilitzar la seguent funcio, que ens crea el fitxer que necesitem i a mes a mes gracies a la recursivitat d'aquesta llibreria en cas de que algunes de les carpetes fins la ruta del fitxer no existeixin les crea tambe.

![](../../../../Imatges/Pasted%20image%2020250220221318.png)
## Esborra Fitxers
Per esborrar fitxers amb aquesta llibreria es molt senzill, simplement necesitarem utilitzar la seguent funcio per forzar que s'esborri el fitxer que necesitem.

![](../../../../Imatges/Pasted%20image%2020250220221616.png)