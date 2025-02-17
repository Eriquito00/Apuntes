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

- Executa un executable amb l'usuari que diem.

Start-Process "executable" -Credential "usuari (si no posem res amb l'usuari que executa)"
	\[-ArgumentList "arguments"\]

- Executa un executable amb un usuari administrador

Start-Process "executable" \[-ArgumentList "usuari (si no posem res amb l'usuari que executa)"\]
	\[-Verb runas\]

- Ens mostra els processos actius.

Get-Process

- Ens mostra els processos que estan actius amb el nom establert

Get-Process -Name ""nom process""

- Ens mostra els processos que estan actius amb el nom establert i quin usuari l'executa, nomes ho pot executar un administrador.

Get-Process -Name ""nom process"" -IncludeUserName