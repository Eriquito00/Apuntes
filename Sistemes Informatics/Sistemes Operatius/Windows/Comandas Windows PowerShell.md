# Comandas Windows PowerShell
### Habilitar escriptori remot (no es ps)
cscript C:\Windows\System32\Scregedit.wsf /ar 0
### Activar / Desactivar firewall
Set-NetFirewallProfile domain,public,private -Enabled False (apagar) True (encendre)
### Xarxa
#### Obtenir la IP i info de xarxa
Get-NetIPAddress
#### Posar de nou 
New-NetIPAddress
- IPAddress
- AddressFamily
- PrefixLength
- InterfaceAlias
#### Elimina la configuracio de xarxa del adaptador
Remove-NetIPAddress
- InterfaceAddress
#### Obtenir el DNS
Get-DnsClientServerAddress
#### Introduir el DNS
Set-DnsClientServerAddress
- InterfaceAlias
- ServerAddresses
### Cambiar nom del equip
Rename-Computer -NewName
### Cambiar firewall
Set-NetFirewallProfile (domain,public,private)
- Enabled (True o False)
### Instalacio del servei AD
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
### Copiar arxius d'una carpeta a altre
Copy-Item -Path "(origen)" -Destination "(desti)" -Force
