# Grups Windows
## Objectes del domini
Builtin: Son grups que el sistema concedeix certs privilegis per poder controlar la maquina localment perque un DC no pot tenir ni grups ni usuaris locals.

Computer: dispositius del domini.

ForeignSecurityPrincipals: son els controladors que tenen relacions de confiança amb el DC.

Managed Service Accounts: son comptes que estan associats a serveis d'un equip.
### Grups de Builtin
- Administradores: acces complet al domini i a administrar equips.
- Dumplicadores: poden duplicar el domini.
- Opers de impresion: administren les impresores del domini.
- Opers de servidores: administren els servidors del domini.
- Operadores de copia de seguridad: administren les copies de seguretat pero no poden canviar la configuracio de seguretat.
## Grups de seguretat especials
Dins de Users tenim els seguents grups:
- Administradores de empresas o organizacion que son administradors del bosc
- Administradores de esquema: podem modificar l'esquema del AD
- Admins. del dominio: administren el domini
### Usuarios Avanzados
Dins de W8.1 tenim usuarios avanzados que poden:
- Administran usuaris i grups locals
- Administrar recursos compartits
- Canviar la hora del programa
- Instalar i desinstalar programes

I no poden:
- Administrar la propietat dels arxius
- Fer copies de seguretat
- Administrar drivers
- Administrar registres d'auditoria
## Ambits i tipus dels grups
Quan creem un grup:
- Domini local: els seus emembres poden ser de qualsevol domini, pero unicament tenen drets sobre aquell domini.
ALERTA Grup local <> Grup del domini local
- Global: els membres son del domini on es troba el grup i tenen permisos a nivell de tot el bosc.
- Universal: els membres poden ser de qualsevol domini i tenen permisos a nivell de tot el bosc.
- Grup de seguretat: per assignar permisos d'access als recursos en Active Directory.
- Grups de distribucio: poden enviar correus electronics als usuaris.