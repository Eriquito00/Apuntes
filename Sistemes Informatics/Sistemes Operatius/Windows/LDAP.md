# LDAP
Lightweight Directory Access Protocol, protocol lleguger d'access a directoris. S'utilitza per ubicar objectes d'active directory.

Cada objecte de AD poseeix un nom de distincio (Distinguished Name, DN) que es unic i que el diferencia de la resta dels objectes, una cadena de text. Per exemple:

**DN="CN=maria,OU=Clients,DC=ASIX1,DC=com"**

Fa referencia a un objecte que es diu "maria" que esta a una unitat organitzativa que es diu "Clients" que esta al domain controller "ASIX1"."com". Amb aquest exemple treiem aquestes conclusions:

- CN: Common Name, per referirse al nom del objecte o a les carpetes.
- OU: Organizational Unit, per referirse a unitats organitzatives.
- DC: Domain Component, que fa referencia a les subcadenes que formen el nom del domini. Cada component esta separat per un punt, com anteriorment "ASIX1.com".
## Nom complet i relatiu
Nom complet:
- Es el DN en el nom de l'objecte i el lloc on esta ubicat, tota la cadena LDAp.

Nom relatiu:
- Identifica unicament l'objecte, sense expresar el contenidor.
- Es unicament el primer component del la cadena LDAP.