# ConsultesAD PowerShell
## Basic
- Podem obtenir dades de un objecte com per exemple un usuari utilitzan en aquest cas el Get.

```PowerShell
Get-ADUser -Identity (nom user o cadena LDAP) `
	-Properties (propietat, propietat, propietat)...

EXEMPLE:

Get-ADUser -Identity user `
	-Properties initials, displayname
```
## Filter
- Amb filter podem fer consultes per obtenir altres dades com per exemple tots els usuaris, grups o altres dades que podem consultar a la base de dades del domini.

```PowerShell
Get-ADUser -Filter {(propietat) (comparador) (valor)}

EXEMPLES

# Aqui podem veure que ens mostra els usuaris que com a propietat de cognom sigui exactament "Pi"

Get-ADUser -Filter {Surname -eq "Pi"}

# Aqui podem veure que obtenim els usuaris que no estiguin habilitats

Get-ADUser -Filter {Enabled -eq $false}
```

- Tambe podem fer una cerca directament a un unitat organitzativa.

```PowerShell
Get-ADUser -Filter * -SearchBase (cadena LDAP de la OU)

EXEMPLE

Get-ADUser -Filter * -SearchBase "OU=unitat,DC=domini,DC=ldap"
```

- Podem obtenir tambe segons el nivell de profunditat dins d'una OU

```POWERSHELL
Get-ADUser -Filter * -SearchBase (cadena LDAP de la OU) -SearchScope (base,onelevel,subtree)

# base
Amb base ens donara tots els usuaris que es diguin igual que la OU

# onelevel
Amb onelevel ens donara els usuaris que estiguin directament dins de la OU

# subtree
Amb subtree ens donara els usuaris de la OU i si hi ha alguna OU dins amb usuaris ens els donara tambe
```
### Comparadors
- -eq: Compara que la propietat que li diem sigui exactament la mateixa que la que li pasem com a valor.
- -like: Compara que la propietat que li diem tingui un regex, pero es una mica diferent, si volem que acabi o comenci per a podem posar que volem que acabi "\*a" i per que comenci per "a\*".
- -notlike: Funciona exactament igual que -like pero al contrari, es a dir que no compleixi el que li posem.
- \*: Amb aquest comparador podem utilitzarlo a propietats o sense, si fem un Get-ADUser -Filter \* obtindrem tots els usuaris.
- -or: S'utilitza per comparar que un valor sigui un O altre, per exemple si volem comparar que la seva ciutat sigui
- ```-city -eq "A" -or -city -eq "B"```
- -and: S'utilitza per asegurar que els dos valors dels costats es compleixin, per exemple si volem que la seva poblacio sigui "A" I que tingui codi postal 17000.
- ```-city -eq "A" -and PostalCode -eq 17000```
- it: Que un valor sigui menor a un altre, per exemple un codi postal mes petit que 17000 NO INCLOS
- ```PostalCode -it 17000```
- gt: Que un valor sigui major a un altre, per exemple un codi postal mes gran que 17000 NO INCLOS
- ```PostalCode -gt 17000```
- le: Que un valor sigui menor O IGUAL a un altre, per exemple un codi postal mes petit que 17000 INCLOS 
- ```PostalCode -le 17000```
- ge: Que un valor sigui major O IGUAL a un altre, per exemple un codi postal mes petit que 17000 INCLOS 
- ```PostalCode -ge 17000```