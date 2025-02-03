Amb la llibreria File podem interactuar amb els fitxers, de forma que podem tant consultar dades dels fitxers y d'altres dades rellevants sobre el dispositiu on s'executa.
![[Pasted image 20250201203345.png]]
## Funcions per obtenir informació sobre arxius i carpetes
Aqui podem veure que per crear un fitxer seria recomanable posar la extensio ja directe y la carpeta nomes seria necesari el nom. La ruta fins al fitxer o la carpeta pot ser absoluta o relativa. Aqui tenim algunes funcions amb les que podem sapiguer la informacio del fitxer o carpeta.
- exists(): per saber si la ruta existeix.
- isHidden(): per saber si l'arxiu o carpeta està amagat.
- canRead(): per saber si l'arxiu o carpeta es pot llegir.
- canWrite(): per saber si l'arxiu o carpeta es pot modificar.
- canExecute(): per saber si l'arxiu es pot executar.
- isFile(): per saber si és un arxiu.
- isDirectory(): per saber si és una carpeta.
- length(): per saber la mida.
- lastModified(): per saber la data de l'última modificació. Retorna els mil·lisegons des de les **0:00** hores del **1/1/1970**.

Aqui tindriem la sortida per consola d'aquests parametres:
![[Pasted image 20250201203814.png]]
![[Pasted image 20250201203824.png]]
## Funcions per obtenir informació sobre la ruta
Amb aquests parametres podem obtenir mes informacio especificament de les rutes del que volem veure.
- getName(): retorna el nom de l'arxiu o la carpeta.
- getParent() o getParentFile(): retorna la carpeta pare on es troba l'arxiu o carpeta.  
    Si la ruta amb la que s'ha creat el _File_ és relativa, pot retornar _null_.
- getAbsolutePath() o getAbsoluteFile(): retorna la ruta absoluta.
- getCanonicalPath() o getCanonicalFile(): retorna la ruta absoluta eliminant símbols redundants com . o ...

Aqui tindriem la sortida per consola d'aquests parametres:
![[Pasted image 20250201204003.png]]
![[Pasted image 20250201204014.png]]
## Funcions per crear, esborrar, renombrar i moure
Amb les seguents funcions podem crear, esborrar, renombrer i moure els fitxers i carpetes.
- mkdir(): crea un directori (cal que la ruta fins al pare existeixi).
- mkdirs(): crea un directori i, si cal, els pares.
- createNewFile(): crea un arxiu buit excepte si ja existeix.
- renameTo(): canvia el nom d'un arxiu o el mou a una altra ruta.
- delete(): esborra un arxiu o directori. Si es tracta d'un directori, cal que estigui buit.

Aqui tindriem la sortida per consola d'aquests parametres:
![[Pasted image 20250201204208.png]]
## Altres funcions interessants
Amb aquestes altres funcions podem fer llistes i obtenir informacio sobre els discos del dispositiu.
- list() o listFiles(): si l'objecte _File_ és una carpeta, obté un _array_ de _Strings_ o de _File_ amb els arxius i carpetes que conté.
- listRoots(): retorna un _array_ de _File_ amb els sistemes d'arxius de la màquina.  
    En Windows podria ser C:\, E:\... En Linux podria ser / (el directori arrel).
- getTotalSpace(): obté la mida en _bytes_ de la partició on es troba el _File_.
- getFreeSpace(): obté l'espai lliure en _bytes_ de la partició on es troba el _File_.
- getUsableSpace(): obté l'espai que pot utilitzar la màquina virtual de la partició on es troba el _File_.

Amb listFiles() podem crear una array amb els fitxers i carpetes de dins d'una carpeta.
![[Pasted image 20250201204421.png]]

Amb listRoots() podem obtenir una llista amb totes les particions del dispositiu.
![[Pasted image 20250201204429.png]]

Aqui podem veure la informacio del espai total del disc, l'espai lliure i l'espai que podem utilitzar (no particionat) del disc.
![[Pasted image 20250201204657.png]]
![[Pasted image 20250201204747.png]]