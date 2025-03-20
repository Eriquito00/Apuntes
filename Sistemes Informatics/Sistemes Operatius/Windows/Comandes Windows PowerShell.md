# Comandas Windows PowerShell
## Xarxa
- Obtenir la IP i info de xarxa
```Powershell
Get-NetIPAddress
```
- Establir una ip i una configuracio de xarxa
```PowerShell
New-NetIPAddress `
- IPAddress (ip) `
- AddressFamily (IPv4 o IPv6) `
- PrefixLength (numero de mascara) `
- InterfaceAlias (interface de xarxa)
```
- Elimina la configuracio de xarxa del adaptador
```PowerShell
Remove-NetIPAddress `
- InterfaceAddress (interficie de xarxa)
```
- Obtenir el DNS
```PowerShell
Get-DnsClientServerAddress
```
- Introduir el DNS
```PowerShell
Set-DnsClientServerAddress `
- InterfaceAlias `
- ServerAddresses
```
- Activar / Desactivar firewall
```PowerShell
Set-NetFirewallProfile domain,public,private 
- Enabled False (apagar) True (encendre)
```
- Cambiar firewall
```PowerShell
Set-NetFirewallProfile (domain,public,private)
- Enabled (True o False)
```
Habilitar escriptori remot (no es powershell)
```CMD
cscript C:\Windows\System32\Scregedit.wsf /ar 0
```
## Equips
- Cambiar nom del equip
```PowerShell
Rename-Computer `
- NewName
```
- Rebre comandes remotes
```PowerShell
Enable-PSRemoting -Force
```
- Apagar un dispositiu mitjançant el seu hostname. I tambe podem utilitzar el parametre -Force per forçar que s'apagui el dispositiu, la estructura hauria de ser amb un " \`" si volem fer un canvi de linea per posar mes parametres
```PowerShell
Stop-Computer -ComputerName (hostname)
```
- Reiniciar un dispositiu i utilitza tambe -ComputerName i el hostname
```PowerShell
Restart-Computer -ComputerName (hostname)
```
- AQUESTA COMANDA NOMES ES POT UTILITZAR SI PERTANY A UN DOMINI. Serveix per enviar un missatge a un dispositiu. Tenint el hostname i posant titol i missatge, el titol i el missatge entre "".
```PowerShell
Send-RDUserMessage -HostServer (hostname) `
	-UnifieldSessionID 1 `
	-MessageTitle "(titol del missatge)" `
	-MessageBody "(missatge que volem enviar)"
```
### Temps d'espera
- Fa que el script esperi cert temps per seguir executant la resta de comandes.
```PowerShell
Start-Sleep -Seconds (-Miliseconds) (temps de espera)
```
## Gestio
- Instalacio del serveis
```PowerShell
Install-WindowsFeature (nom de la caracteristica) -IncludeManagementTools (per instalar dependencies)
```
- Copiar arxius d'una carpeta a altre
```PowerShell
Copy-Item -Path "(origen)" `
-Destination "(desti)" `
-Force
```
- Posar clau de windows
```PowerShell
slmgr /ipk (clau producte)
```
### Historial de comandes
- Ens dona l'historial de les ultimes comandes que hem introduit i podem crear un fitxer amb l'historial.
```PowerShell
Get-History
```
- Tambe podem guardar l'historial a un fitxer aixi:
```PowerShell
Get-History > (nom fitxer i extensio)
```
## Executar amb altres credencials

- Executa un executable amb l'usuari que diem. Com aquesta comanda es una mica complexa aqui tenim un exemple, que basicament inicia un Process powershell per parar un altre process  powershell amb credencials administrador.
```PowerShell
Start-Process "executable" -Credential "usuari (si no posem res amb l'usuari que executa, ha de ser nom de Net-Bios)"
	[-ArgumentList "arguments"]
```

![](../../../Imatges/Pasted%20image%2020250225095947.png)

- Executa un executable amb un usuari administrador
```PowerShell
Start-Process "executable" [-ArgumentList "usuari (si no posem res amb l'usuari que executa, ha de ser nom de Net-Bios)"]
	[-Verb runas] (SEMPRE DEMANARA EL PERFIL D'ADMINISTRADOR)
```
## Procesos
- Ens mostra els processos actius.
```PowerShell
Get-Process
```
- Ens mostra els processos que estan actius amb el nom establert
```PowerShell
Get-Process -Name ""nom process""
```
- Ens mostra els processos que estan actius amb el nom establert i quin usuari l'executa, nomes ho pot executar un administrador.
```PowerShell
Get-Process -Name ""nom process"" -IncludeUserName
```
- Para un proces que esta en curs en base a la ID del process, podem altres parametres com -Force  per forçar a que es tanqui el process 
```PowerShell
Stop-Process -Id (id del process) [-Force]
```
## Viatjar entre entorns
- Si estem a PowerShell i volem anar a cmd podem executar la seguent comanda a cmd. Aixi tindrem les comandes de cmd dins de la nostre terminal de powershell.
```PowerShell
cmd
```
- Si volem executar comandes de PowerShell a cmd podem fer el seguent. Aixi podem executar comandes de powershell desde cmd pero el que fara en veritat sera executar la comanda en powershell y donarnos el resultat per cmd no l'executa directe al cmd
```CMD
powershell /c (comanda) (EL "/c" ES PER A QUE EXECUTI AMB L'ENTORN QUE DEMANEM I DESPRES ES TANQUI)
```
## Activar execucio de scripts
- Ens diu si tenim o no dret d'executar scripts
```PowerShell
Get-ExecutionPolicy
```
- Ens permet o ens restringeix executar scripts
```PowerShell
Set-ExecutionPolicy (restricted / unrestricted)
```
## Usuaris
### Crear
- Crea un usuari de domini amb el nom que posem
```PowerShell
New-ADUser (-Name) (nom usuari)
```
- A aquest usuari li falten les coses me importants, la forma d'iniciar sesio tant local com per domini amb el @ del domini.
```PowerShell
New-ADUser -Name (nom usuari) `
    -SamAccountName (nom usuari) `
    -UserPrincipalName (nom usuari)@(extensio domini) `
	-Enabled $true o $false (usuari habilitat)
```
- Tambe podem fer que al crear l'usuari ens demani la contraseña utilitzant la comanda Read-Host:
```PowerShell
Read-Host -AsSecureString "(missatge)"
```

```PowerShell
New-ADUser -Name (nom usuari) `
    -SamAccountName (nom usuari) `
    -UserPrincipalName (nom usuari)@(extensio domini) `
	-Enabled $true o $false (usuari habilitat) `
	-AccountPassword (Read-Host -AsSecureString "(missatge)")
```
- O podem fer que ho faci creant-lo amb la contraseña que volem per guardar la contrasenya de forma segura:
```PowerShell
ConvertTo-SecureString "(contraseña)" -AsPlainText -Force
```

```PowerShell
New-ADUser -Name (nom usuari) `
    -SamAccountName (nom usuari) `
    -UserPrincipalName (nom usuari)@(extensio domini) `
	-Enabled $true o $false (usuari habilitat) `
	-AccountPassword (ConvertTo-SecureString "(contraseña)" -AsPlainText -Force)
```
- Altres parametres de New-ADUser:

-DisplayName "(nom)" //Nom per mostrar
-GivenName "(nom)" //Nom de pila
-Surname "(nom)" //Cognoms
-EmailAddress (email) //assignar un correu electronic
-ChangePasswordLogon (true o false) //Que pugui cambiar la contraseña l'usuari
-PasswordNeverExpires (true o false) //Que la contraseña expiri
-CannotChangePassword (true o false) //Que l'usuari no pugui cambiar la contraseña
-LogonWorkstations (hostname) //nomes podra iniciar sessio a aquests dispositius, si volem que sigui mes de una posarem "(hostname),(hostname)" sense espais.
## Grups
### Crear
- Crear un grup amb el minim indispensable per poder crearlo.
```PowerShell
New-ADgroup -Name (nom grup) `
	-GroupScope (DomainLocal, Global, Universal)
```
### Eliminar
- Elimina un grup pero NO elimina els usuaris que estaben afegits a ell.
```PowerShell
Remove-ADGroup -Identity (nom grup) `
    -Confirm: $false //per eliminar el missatge de confirmacio, true per demanarlo
```
### Renombrar
- Renombra el nom d'un grup per altre que posem. Nomes cambia el nom del objecte no el nom de la sam, es a dir, ens seguirem referint a aquest grup pel no antic que tenia si no fem un set amb SamAccountName
```PowerShell
Rename-ADObject -Identify (cadena LDAP) `
	-NewName (nou nom)
	-Confirm: $false //per eliminar el missatge de confirmacio, true per demanarlo
```
### Editar
- Podem editar propietats dels grups com per exemple la sam.
```PowerShell
Set-ADGroup -Identify (nom grup) `
	-SamAccountName (nou nom sam) //cambia el nom de la sam
```
## Afegir i treure usuaris a grups i grups a usuaris
### Afegir
#### Usuaris a grups
- Afegeix els usuaris que li diguem al grup que li posem, tambe podem utilitzar la sam: "CN=(nom usuari),OU=(nom OU), DC=(nom domini),DC=(extensio del domini)"
```PowerShell
Add-ADDGroupMember -Identify (nom grup) `
	-Members (nom usuari), (nom usuari)... //per eliminar el missatge de confirmacio, true per demanarlo
```
#### Grups a usuaris
- Afegeix els grups que li diem al usuari que posem, tambe podem utilitzar igual que amb l'anterior la seva sam: "CN=(nom grup),OU=(nom OU), DC=(nom domini),DC=(extensio del domini)"
```PowerShell
Add-ADPrincipalGroupMembership -Identity (nom usuari) `
	-MemberOf (nom grup), (nom grup)...
```
### Treure
#### Usuaris a grups
- Treu una serie d'usuaris d'un grup. Podem utilitzar la seva sam: "CN=(nom usuari),OU=(nom OU), DC=(nom domini),DC=(extensio del domini)"
```PowerShell
Remove-ADGroupMember -Identify (nom grup) `
	-Member (nom usuari), (nom usuari)... `
	-Confirm: $false //per eliminar el missatge de confirmacio, true per demanarlo
```
#### Grups a usuaris
- Treu grups d'un usuari en concret, tambe podem utilitzar igual que amb l'anterior la seva sam: "CN=(nom grup),OU=(nom OU), DC=(nom domini),DC=(extensio del domini)"
```PowerShell
Remove-ADPrincipalGroupMembership -Identity (nom usuari) `
	-MemberOf (nom grup), (nom grup)... `
	-Confirm: $false //per eliminar el missatge de confirmacio, true per demanarlo
```
## Mostra
### Usuaris a grups
- Ens mostra la informacio del grup entre ella els seus membres.
```PowerShell
Get-ADGroupMember -Identify (nom grup)
```
### Grups a usuaris
- Ens mostra la informacio del grup entre ella els seus membres.
```PowerShell
Get-ADPrincipalGroupMembership -Identity (nom usuari)
```