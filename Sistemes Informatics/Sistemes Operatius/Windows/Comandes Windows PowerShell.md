# Comandas Windows PowerShell

**ELS \[\] SIGNIFIQUEN QUE SON ATRIBUTS OPCIONALS**
## Habilitar escriptori remot (no es ps)
cscript C:\Windows\System32\Scregedit.wsf /ar 0
## Activar / Desactivar firewall
Set-NetFirewallProfile domain,public,private 
- Enabled False (apagar) True (encendre)
## Xarxa
### Obtenir la IP i info de xarxa
Get-NetIPAddress
### Posar de nou 
New-NetIPAddress
- IPAddress
- AddressFamily
- PrefixLength
- InterfaceAlias
### Elimina la configuracio de xarxa del adaptador
Remove-NetIPAddress
- InterfaceAddress (interficie de xarxa)
### Obtenir el DNS
Get-DnsClientServerAddress
### Introduir el DNS
Set-DnsClientServerAddress
- InterfaceAlias
- ServerAddresses
## Cambiar nom del equip
Rename-Computer 
- NewName
## Rebre comandes remotes
Enable-PSRemoting -Force
## Cambiar firewall
Set-NetFirewallProfile (domain,public,private)
- Enabled (True o False)
## Instalacio del servei AD
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
## Copiar arxius d'una carpeta a altre
Copy-Item -Path "(origen)" -Destination "(desti)" -Force
## Posar clau de windows
slmgr /ipk (clau producte)
## Instalar servei de domini (o altres)
Install-WindowsFeature (nom de la caracteristica) -IncludeManagementTools (per instalar dependencies)
## Executar amb altres credencials

- Executa un executable amb l'usuari que diem. Com aquesta comanda es una mica complexa aqui tenim un exemple, que basicament inicia un Process powershell per parar un altre process  powershell amb credencials administrador.

Start-Process "executable" -Credential "usuari (si no posem res amb l'usuari que executa, ha de ser nom de Net-Bios)"
	\[-ArgumentList "arguments"\]

![](../../../Imatges/Pasted%20image%2020250225095947.png)

- Executa un executable amb un usuari administrador

Start-Process "executable" \[-ArgumentList "usuari (si no posem res amb l'usuari que executa, ha de ser nom de Net-Bios)"\]
	\[-Verb runas\] (SEMPRE DEMANARA EL PERFIL D'ADMINISTRADOR)

- Ens mostra els processos actius.

Get-Process

- Ens mostra els processos que estan actius amb el nom establert

Get-Process -Name ""nom process""

- Ens mostra els processos que estan actius amb el nom establert i quin usuari l'executa, nomes ho pot executar un administrador.

Get-Process -Name ""nom process"" -IncludeUserName

- Para un proces que esta en curs en base a la ID del process, podem altres parametres com -Force  per forçar a que es tanqui el process 

Stop-Process -Id (id del process) \[-Force\]

## Viatjar entre entorns
- Si estem a PowerShell i volem anar a cmd podem executar la seguent comanda a cmd. Aixi tindrem les comandes de cmd dins de la nostre terminal de powershell.

cmd

- Si volem executar comandes de PowerShell a cmd podem fer el seguent. Aixi podem executar comandes de powershell desde cmd pero el que fara en veritat sera executar la comanda en powershell y donarnos el resultat per cmd no l'executa directe al cmd

powershell /c (comanda) (EL "/c" ES PER A QUE EXECUTI AMB L'ENTORN QUE DEMANEM I DESPRES ES TANQUI)

## Control de dispositius
- Apagar un dispositiu mitjançant el seu hostname. I tambe podem utilitzar el parametre -Force per forçar que s'apagui el dispositiu, la estructura hauria de ser amb un " \`" si volem fer un canvi de linea per posar mes parametres

Stop-Computer -ComputerName (hostname)

- Reiniciar un dispositiu i utilitza tambe -ComputerName i el hostname

Restart-Computer -ComputerName (hostname)

- AQUESTA COMANDA NOMES ES POT UTILITZAR SI PERTANY A UN DOMINI. Serveix per enviar un missatge a un dispositiu. Tenint el hostname i posant titol i missatge, el titol i el missatge entre "".

Send-RDUserMessage -HostServer (hostname) \`
	-UnifieldSessionID 1 \`
	-MessageTitle "(titol del missatge)" \`
	-MessageBody "(missatge que volem enviar)"
## Temps d'espera
- Fa que el script esperi cert temps per seguir executant la resta de comandes.

Start-Sleep -Seconds (-Miliseconds) (temps de espera)
## Historial de comandes
- Ens dona l'historial de les ultimes comandes que hem introduit i podem crear un fitxer amb l'historial.

Get-History

- Tambe podem guardar l'historial a un fitxer aixi:

Get-History > (nom fitxer i extensio)
## Crear usuaris
- Crea un usuari de domini amb el nom que posem

New-ADUser (-Name) (nom usuari)

- A aquest usuari li falten les coses me importants, la forma d'iniciar sesio tant local com per domini amb el @ del domini.

New-ADUser -Name (nom usuari) \`
    -SamAccountName (nom usuari) \`
    -UserPrincipalName (nom usuari)@(extensio domini) \`
	-Enabled $true o $false (usuari habilitat) \`

- Tambe podem fer que al crear l'usuari ens demani la contraseña utilitzant la comanda Read-Host:

Read-Host -AsSecureString "(missatge)"

- O podem fer que ho faci creant-lo amb la contraseña que volem:

ConvertTo-SecureString "(contraseña)" -AsPlainText -Force

- Y podem aplicar-ho a la anterior de la seguent manera, entre parentesis per executar abans aquesta comanda.

New-ADUser -Name (nom usuari) \`
    -SamAccountName (nom usuari) \`
    -UserPrincipalName (nom usuari)@(extensio domini) \`
	-Enabled $true o $false (usuari habilitat) \`
	-AccountPassword (Read-Host -AsSecureString "(missatge)")

New-ADUser -Name (nom usuari) \`
    -SamAccountName (nom usuari) \`
    -UserPrincipalName (nom usuari)@(extensio domini) \`
	-Enabled $true o $false (usuari habilitat) \`
	-AccountPassword (ConvertTo-SecureString "(contraseña)" -AsPlainText -Force)

- Altres parametres de New-ADUser:

-DisplayName "(nom)" //Nom per mostrar
-GivenName "(nom)" //Nom de pila
-Surname "(nom)" //Cognoms
-EmailAddress (email) //assignar un correu electronic
-ChangePasswordLogon (true o false) //Que pugui cambiar la contraseña l'usuari
-PasswordNeverExpires (true o false) //Que la contraseña expiri
-CannotChangePassword (true o false) //Que l'usuari no pugui cambiar la contraseña
-LogonWorkstations (hostname) //nomes podra iniciar sessio a aquests dispositius, si volem que sigui mes de una posarem "(hostname),(hostname)" sense espais.
## Crear Grups
- Crear un grup amb el minim indispensable per poder crearlo.
New-ADgroup -Name (nom grup) \`
	-