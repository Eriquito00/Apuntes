# Particions

## MBR (Master Boot Record)

- Es una taula de particiones que guarda la configuracio de les particions del disc.  
- Fisicament es troba en el primer sector del HDD.  
- Normalment te una longitud de 512 bytes.  

![Pasted image 20241022092627](/Imatges/Pasted%20image%2020241022092627.png)

### Tipus de particions MBR

- Primaries: tenen un boot-sector per poder arrencar. MBR nomes te espai per guardar un maxim de 4 particions.  
- Estesa: es una particio primaria que al seu interior nomes conte particions logiques. Com molt hi ha 1 estesa per cada dispositiu fisic.  
- Logiques: particions dins d'una particio estesa. No hi ha limit, nomes la capacitat de la particio estesa.  
Sempre tindra maxim 4 particions, per exemple 3 primaries i 1 estesa i dins de la estesa les que volguem.

## GPT (GUID Partition Table)

- Es l'equivalent a MBR, pero en dispositius UEFI.  
- UEFI es el successor de BIOS.

### Tipus de particions GPT

- Nomes poden ser primaries.  
- En GPT no hi ha cap limit de primaries.

## Particio

- Una particio es una de les zones del disc dur contigues i no solapades.  
- Des d'un punt de vista logic son tractades com diferents unitats, tot i que internament formen part de la mateixa unitat fisica.  
- Les particions estan definides al MBR o GPT.

### Particio activa

- Es la particio escollida per arrencar.  
- Conte un programa en el primer sector de la particio (boot-sector).  
- Sols 1 particio per cada disc pot ser activa.  
- La informacio de quina es l'activa es guarda en la taula de particions.

### Sector

Es la minima unitat de lectura o d'escriptura fisica del HDD. Normalment te una capacitat de 512 bytes.

### Boot Sector (sector d'arrencada)

Es el primer sector de cada particio primaria tant si es activa com si no.

### Cluster

- Es una agrupacio de sectors consecutius.  
- Determinen la unitat minima de informacio de la particio que sera ocupada o alliberada.  
- La longitud del cluster es defineix quan es dona format a una particio.

## Taula de fitxers

- Es un espai a l'inici de cada particio (despres del boot-sector) on es guarda la informacio de cada fitxer que conte la particio.  
- Entre altres coses, de cada fitxer es guarda: nom complet, ruta on es trobada, clusters on esta ubicat, atributs i altres detalls de seguretat.  
- En un sistema de fitxers FAT32, la taula s'anomena FAT (File Allocation Table).  
- En un sistema NTFS, la taula es MFT (Master File Table).

INICIALITZAR EL DISC es basicament crear la taula de particion MBR o GPT. Sobre un espai lliure del disc es marca quins sectors ocupara (d'inicia a final).  
- Si la particio es primaria reserva el 1r sector pel boot-sector.  
- Si la particio es logica no reserva boot-sector perque les logiques han d'estar a dins d'una estesa.

Formatar la particio

- Defineix quin sistema de fitxers fara servir.  
- Reserva un espai gran al principi de la particio per guardar la taula de fitxers.  
- Estableix quina es la longitud dels clusters.  
- Marca l'etiqueta de la particio.  
NTFS utilitza la taula MFT que ocupa un 12,5% de tota la particio.  
Quan es crea una particio activa (a) quan es fa a gpt es selecciona automaticament "ESP" que es "Efi System Partition".
