# Slots d'expansio
## Tipus de slots d'expansio
### El bus PCI
- El bus PCI vol dir Peripheral Component Interconnect, interconnexio de components periferics.
- Desenvolupat per Intel als anys 90.
- Adoptat per molts fabricants fins i tot pels MAC.
Esta en desus pero encara es troba.
- 2 versions amb diferent voltatge i velocitat pero el mateix connector
- Per distingir estan muntades al reves

#### Versio 1

![](/Imatges/Pasted%20image%2020240930093850.png)

#### Versio 2

![](/Imatges/Pasted%20image%2020240930094943.png)

A nivell de targetes podem trobar 3 tipus:

#### Versio 1

![](/Imatges/Pasted%20image%2020240930094454.png)

#### Versio 2

![](/Imatges/Pasted%20image%2020240930094541.png)

#### Versio universal

![](/Imatges/Pasted%20image%2020240930094503.png)

### El Bus PCI-Express
- Desenvolupat per Intel a 2004 i basat en PCI
- Intel vol unificar tots els slots de dispositius i fer desapareixer el pont del nord i el pont del sud.
- Es fa servir per tot tipus de targetes, especialment grafiques perque el bus es el mes rapid fins el moment.

#### Caracteristiques
- El un bus local
Es un bus connectat directament a la señal de rellotge de la CPU i a les seves connexions de dades i adreçes. Per aixo disposa dels mateixos valors de velocitat i ample de bits pel processador.
- Transferencia hibrida
Pot treballar en serie o paralel, el slot PCIe x1 treballa amb un ample de 1 bit (es serie). Els altres slots PCIe treballen a diferent amplada: 4, 8, 16 bits (son paralels).
- Punt a punt
Que cada dispositius que connectem al bus te linea directa i exclusiva amb el controlador. El PCI no era punt a punt perque el bus i el rellotge eren compartits entre tots els dispositius connectats.
- Full duplex
Cada una d'aquestes linies exclusives amb el controlador es el connector i es denomina link. Cada link esta format per un o mes lanes (carrils d'un bit). El numero del link (x1, x4,...) indica els lanes.
- PCIe x1 = 1 lanes
- PCIe x4 = 4 lanes
- PCIe x8 = 8 lanes
- PCIe x16 = 16 lanes
Per tant full duplex significa que cada lane pot enviar i rebre dades al mateix temps.
Podem trobar 4 tipus diferents links PCI-Express que te 4 slots diferents. tambe podem trobar 6 revisions diferents del protocol:

![](/Imatges/Pasted%20image%2020240930100516.png)

### Diferencia entre PCI i PCIe
- El color no forma part de l'estandar.
- Tenen dos grups de contactes separats.
- Estan mirant sempre a la part de sortida del back panel de la placa base.
- El PCIe sempre esta una mica mes endins de la placa que el PCI.
- El PCIe x1 te la part de transferencia mes petita que la part de alimentacio.
- El PCIe x4 te el doble de transferencia que d'alimentacio, no es frequent trobar-ho.
- El PCIe x8 la part de dades es entre 3 y 4 vegades mes llarga que la de alimentacio, no es frequent trobar-ho.
- El PCIe x16 es tan llarg com un PCI.

![](/Imatges/Pasted%20image%2020240930100841.png)

### Altres consideracions
Podem utilitzar altres tarjetes PCIe a altres slots de PCIe, per exemple una targeta de PCIe x8 pot estar a un slot PCIe x16.
Si connectem un PCIe v1.0 que va a 250MB/s per lane si el conectem a un slot PCIe v3.0 la controladora adaptara la velocidad a la versio mes baixa per tant anira a la velocitat del PCIe v1.0.
Podem trobar un slot PCIe x4 que tingui la llargada d'un PCIe x16 pero els pins nomes arriben fins al PCIe x4.

![](/Imatges/Pasted%20image%2020241001105630.png)

Tambe podem trobar tarjetes PCIe que tinguin la llargada per entrar a un PCIe x16 pero els pins nomes arriben a ser PCIe x4.

![](/Imatges/Pasted%20image%2020241001105221.png)

Podem trobar PCIe "oberts" que son PCIe que permeten tarjetes mes llargues, per exemple un PCIe x8 que al arribar als 8 no te un limitador que no ens permeti una tarjeta mes gran.

![](/Imatges/Pasted%20image%2020241001104740.png)

Sigui el cas que sigui sempre que el slot PCIe sigui mes gran que el PCIe de la tarjeta es podra connectar.

# Normes dels USB
Els USB (Universal Serial Bus) no son ports de connexio, son busos de connexio exterior de qualsevol tipus de periferic. Podem trobar 3 tipus de connectors diferents:
(foto de los 3 tipos de usb A, B i C)
USB 1.0 = 1.5Mb/s = 0.188MB/s
USB 1.1 = 12Mb/s = 1.5MB/s
USB 2.0 = 480Mb/s = 60MB/s, tenen el plastic de color blanc o negre.
USB 3.0 = 4.8Gb/s = 600MB/s, tambe es diu SuperSpeed USB i te el plastic de color blau.
Amb ajuda de concentradors de USB es poden connectar fins 127 dispositius i poden ser interns o externs.
Es posible que els USB tenen el logo de USB normal aixo es que son USB 2.0.

![](/Imatges/Pasted%20image%2020241001095705.png)

Tambe pot ser que porti SS que significa que es un USB 3.0.

![](/Imatges/Pasted%20image%2020241001095729.png)

Hi han USB que tenen un logo de carrega i un petit raig que aixo significa que en cas de que s'apaga l'equip aquest USB segueix subministrant.

![](/Imatges/Pasted%20image%2020241001095833.png)

Si el USB te SS10 significa que es un USB 3.1 pero no es cap estandar.

![](/Imatges/Pasted%20image%2020241001095811.png)

Del USB 3.1 tambe incorpora el USB tipus C, es reversible i pot alimentar fins a 100W pensat per substituir els cables d'alimentacio.

# SATA
SATA fa referencia a Serial ATA, es una evolucio de ATA i ATA tenia transmisio paralela la qual cada cicle enviava 16 bits.
Un tipus de cable i te el mateix connector per un costat tant per l'altre, te 7 pins i els cables son mes fins i normalment vermell, no te cap connector enmig ni te el conecpte de Master i Slave, un cable es per un dispositiu.
SATA 1 = 1.5Gb/s = 150MB/s
SATA 2 = 3Gb/s = 300MB/s
SATA 3 = 6Gb/s = 600MB/s
Els calcus esstan de forma que per cada 8 bits de dades necesitava enviar 10 per aixo la conversio entre Gb a MB es com si fos de GB a MB.
Seria idoni que un Disc Dur SATA 1 la controladora tambe sigui SATA 1, un disc SATA 2 amb un controlador SATA 2 i un disc SATA 3 amb una controladora SATA 3.
De totes formes l'estandar esta proveit de Backward compativility, es a dir compatibilitat amb dispositius antics i Forward compatibility que es compatibilitat amb productes futurs.
Aixo es pot fer amb un jumper per limitar la velocitat del disc i adaptarse a controladors inferiors, pero nomes es pot rebaixar una versio, es a dir de SATA 3 a SATA 2 o de SATA 2 a SATA 1.

![](/Imatges/Pasted%20image%2020241001104327.png)

Si es el cas contrari, es a dir una controladora SATA 2 i tenim un disc SATA 1 hi han algunes controladores que poden negociar la velocitat i rebaixar la velocitat.
