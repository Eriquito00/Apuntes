# Eines administratives WS 2022

Son eines, programes o comandes que ens ajuden a administrar el nostre equip.

Amb RSAT podem utilitzar les eines administratives desde altre dispositiu i aqui veurem algunes personalitzacions que podem fer a la maquina remota per fer una administracio mes senzilla.

Podem fer un "windows + r" i buscar 'MMC' amb aquesta eina podem afegir les opcions d'administracio que volguem.

![](../../../Imatges/Pasted%20image%2020250217093842.png)

Aqui podem afefir o treure complements i podem afegir els complements que volguem.

![](../../../Imatges/Pasted%20image%2020250217093907.png)

Aqui podem veure totes les eines que podem afegir pero s'ha d'anar en compte perque hi han eines que estan disponibles a nivell local i de domini, si volem administrar el domini ens hem d'asegurar que escollim la de domini.

## Objectes ActiveDirectory
De objectes al nostre domini tenim de dos tipus:
- Contenidors que poden tenir altres objectes dins seu, a AD tenim el propi domini i les Unitats Organitzatives (UO). Els contenidors nomes poden penjar de altres contenidors.
- No  contenidors que son simplement objectes d'un tipus especific, com per exemple els Usuaris, Grups, Equips, entre altres.