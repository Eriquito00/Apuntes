# Windows
## Windows Server
## Xarxes
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

Mascara de subxarxa
- Es una combinacio de bits
- Serveix per segmentar l'adreça IP i saber quins bits son adreça de xarxa i quins de host.
	- Exemple:
		192.168.28.5 IP
		255.255.255.0 Mascara

IPv6 (Internet Protocol versio 6):
- Pensades per substituir a l'anterior IPv4
- Format: 128 bits expressats en 8 blocs de 4 digits hexadecimals separat per dos punts (:).
	1467 : 2001 : 12C5 : 23B0 : 0000 : 0000 : 0000 : AF13
- Si hi han blocs de 0000 es poden substituir per "::".
	1467 : 2001 : 12C5 : 23B0 :: AF13
- Adreça de loopback es :: 1

Altres definicions:
- Porta d'enllaç (Gateway) dispositiu per interconectar mes d'una xarxa.
A la practica, serveix per connectar un PC amb IP privada amb un PC que te IP publica, i aixi tenir acces a internet.

- Adreça DNS: Adreça del dispositiu que fa la funcio de servidor DNS.
A la practica es fa servir per demanar una traduccio entre nom de maquina i IP.

- Firewall: sistema de seguretat de la xarxa que fitra el transit de la xarxa entrant i sortint.
Funciona bloquejant o permetent el pas per la xarxa dels paquets de dades.

- Escritori remot: tecnologia que permet a un usuari treballar en un PC des d'un ordinador remot.
	- El PC local envia per xarxa les comandes que cal fer al PC remot.
	- Es del PC remot qui executa les comandes (amb els recursos de CPU i RAM de la maquina a la que s'acceix).
	- El PC remot envia per xarxa la informacio per pantalla.

- Administracio remota: tecnologia que permet fer canvis a la configuracio d'un equip de manera remota.

La configuracio de xarxa recomanada es que el server tingui com a DNS la seva IP i com a alternativa localhost (127.0.0.1) i el client nomes tingui la IP DNS del servidor.

[Comandas Windows PowerShell](Comandas%20Windows%20PowerShell.md)