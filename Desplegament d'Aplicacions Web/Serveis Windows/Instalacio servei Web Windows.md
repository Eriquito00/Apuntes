# Instalacio servei Web Windows
Entrem a administrador de servidors de Windows i instalarem el servei Web de Windows, una vegada instalat segurament necesitarem fer un reinici del servidor per aplicar la nova caracteristica/rol.

Una vegada reiniciat podem anar al Administrador de serveis de windows i buscar Intenet Information Service (IIS).

Una vegada obert podem anar a l'apartat de Sitios i alla tindrem totes les pagines, podem obrir la primera i una vegada desplegada podem veure que funciona correctament.
## Creacio de una web a IIS
Les nostres webs hi seran a la seguent direccio seguent `C:\inetpub\wwwroot`. Aqui podem crear les carpetes que volguem, una per cada web que volguem.

Per tant una vegada tinguem la nostre web alla podem afegir un site a IIS, alla haurem de omplenar la seguent informacio:
- Nom del lloc
- Domini
## Modificacio de DNS
Per a que el nostre dispositiu ens mostri la web local i no vagi a buscarla al DNS anirem a la seguent ruta perque no vagi a buscarla i la mostri directament. La ruta es `C:\Windows\system32\drivers\etc` entrarem el fitxer hosts i afegirem la IP 127.0.0.1 i el domini de la pagina que volguem.
## Afegir alies
Si volem trobar la web per un alies podem anar a la web que volguem, anar a enlaces i afegir un enllaç, per exemple si tenim la web `www.web.com` i volem fer que la poguem trobar posant `web.com`.
## Document d'apertura
Si volem escollir altre arxiu com a apertura de la nostre web que no sigui el tipic `index.php` o `index.html` podem anar a la web que volem cambiar, anar a `Documento predeterminado` i alla afegir el nom del fitxer que volem que sigui la nostre entrada.
## VirtualHost
Si volem que ens funcioni en local haurem de fer la modificacio al fitxer hosts tambe.
### Host
Anirem a cadascuna de les webs que tinguem i els hi posarem host diferents, podem posar a cadascuna un d'aquests hosts:
- www.host1.com
- www.host2.com
- www.host3.com
Aixi podem tenir 3 web al mateix servidor i segons quina web es demana mostrarem una o altre depenent del HOST que ens demanin.
### Port
Anirem a cadascuna de les webs que tinguem i els hi posarem ports diferents, podem posar a cadascuna un d'aquests ports:
- 80
- 8080
- 8088
Aixi podem tenir 3 web al mateix servidor i AL MATEIX HOST segons quina web es demana mostrarem una o altre depenent del PORT que ens demanin.

Fent aixo cambia una mica la cerca al navegador per tant si totes tenen el mateix HOST pero diferent PORT la cerca es veuria de la seguent manera:
- www.host1.com:80
- www.host1.com:8080
- www.host1.com:8088
### IP
Principalment necesitem que el servidor estigui a dues xarxes a l'hora, una vegada fet podem configurar que si ens entra per una xarxa o altres d'aquestes dues:
- 172.16.0.1
- 172.16.0.2

Una vegada fet podem accedir al servidor web per la IP del servidor que tingui a cada xarxa i segons la configuracio ens enviara a una web o altre.