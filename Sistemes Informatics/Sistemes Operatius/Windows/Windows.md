# Windows Server
# Xarxes
MAC: Medium Access Control
- Identificador de tota la targeta o dispositiu de xarxa
- Es unic a nivell mundial, no poden haver 2 dispositius amb la mateixa mac
- Es coneix tambe com adreça fisica
- Format de 48 bits expressat en 12 digits hexadecimals
	- 24 bits que identifiquen el fabricant
	- 24 bits que identifiquen unic assignat pel fabricant

Els numeros en Octal son agrupacions de 3 bits:

BINARI                  001|010|100|111
OCTAL                    3  |   2  |  4 |  7

Els numeros en Hexadecimal son agrupacions de 4 bits:

BINARI                  0010|1010|0111
HEXADECIMAL        6   |   A   |   7

IPv4: Internet Protocol versio 4
- Identifiquen un punt de connexio de la xarxa
- Es coneix tambe com a adreça logica
- Es assignat a cada interface de xarxa per un administrador de xarxa
- Format de 32 bits expresats en 4 bytes separats per punts:
	192.168.1.1
- Cada adreça IP te dos camps:
	- Identificador de xarxa
	- Identifica del host dins la xarxa
- La quantitat de bits de cada part es variable, pero la suma ha de ser sempre 32 bits.
- L'adreça de Host no poden ser tots 0 ni 1

Principals tipus de IPv4:
- Classe A: 0.0.0.0 -> 127.255.255.255
10.0.0.0 - 10.255.255.255
- Classe B: 128.0.0.0 -> 191.255.255.255
172.16.0.0 - 172.31.255.255
- Classe C: 192.0.0.0 -> 223.255.255.255
192.168.0.0 - 192.168.255.255

Broadcast:
Adreça que permet arribar de manera automatica a tots els host d'una xarxa, sense necessitat de saber les respectives adreces IP de cada host.

APIPA:
Automatic Private Intenet Protocol Addressing, adreça IP que resulta de fallar la comunicacio amb un servidor DHCP.

Loopback:
Direccio especial que s'utilitza per comunicar-se amb el mateix host, sense necesitat d'arribar a la xarxa fisica.

IP Estatica:
- La IP es fixa, configurada manualment al dispositiu per un administrador de xarxa
- Sempre tindra la mateixa, a no ser que l'administrador la torni a canviar.

IP Dinamica:
- La IP s'assigna automaticament a traves d'un servidor DHCP.
- Cada cop que el dispositiu es connexta a Internet, el servidorDHCP pot assignar una diferent.

IP Publiques:
- Son visibles en tot internet
- Si un PC vol connectar-se a internet cal tenir acces a un IP publica
- Un ordinador amb una IP publica es accesible (visible) des de qualsevol altre ordinador connectat a internet.

IP Privades (reservades):
- Son visibles unicament per altres hosts de la seva propia xarxa.
- Es fan servir a les empreses per connectar les terminals de treball
- Els PC amb IP privades poden sortir a internet per mitja d'un router o proxy que tingui una IP publica, pero des d'intenet no es pot accedir als PC de dins de la xarxa.
