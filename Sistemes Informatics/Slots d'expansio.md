## Tipus de slots d'expansio
### El bus PCI
- El bus PCI vol dir Peripheral Component Interconnect, interconnexio de components periferics.
- Desenvolupat per Intel als anys 90.
- Adoptat per molts fabricants fins i tot pels MAC.
Esta en desus pero encara es troba.
- 2 versions amb diferent voltatge i velocitat pero el mateix connector
- Per distingir estan muntades al reves
#### Versio 1
![[Pasted image 20240930093850.png]]
#### Versio 2
 ![[Pasted image 20240930094943.png]]
A nivell de targetes podem trobar 3 tipus:
#### Versio 1
![[Pasted image 20240930094454.png]]
#### Versio 2
![[Pasted image 20240930094541.png]]
#### Versio universal
![[Pasted image 20240930094503.png]]
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
![[Pasted image 20240930100516.png]]
### Diferencia entre PCI i PCIe
- El color no forma part de l'estandar.
- Tenen dos grups de contactes separats.
- Estan mirant sempre a la part de sortida del back panel de la placa base.
- El PCIe sempre esta una mica mes endins de la placa que el PCI.
- El PCIe x1 te la part de transferencia mes petita que la part de alimentacio.
- El PCIe x4 te el doble de transferencia que d'alimentacio.
![[Pasted image 20240930100841.png]]
