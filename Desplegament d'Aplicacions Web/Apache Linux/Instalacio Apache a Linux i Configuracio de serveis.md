# Instal·lació Apache a Linux i Configuració de serveis

Instalem apache2

```BASH
sudo apt install apache2
```

Comprovem el servei amb systemctl

```BASH
sudo systemctl status apache2.service
```

Rutes importants de apache2:
- /etc/apache2/apache2.conf -> fitxer de configuracio de apache2.
- /etc/apache2/sites-available -> fitxers de configuracio de les webs accesibles.
- /etc/apache2/sites-available/000-default.conf -> fitxer de configuracio per defecte (podem copiarla i aplicarla a altre web)
- /etc/apache2/ports.conf -> configuracion de puertos.

Dins del fitxer de copia de 000-default.conf podem cambiar els seguents parametres:
- ServerName (nom server) -> nom del "domini" que l'allotjara.
- ServerAlias (alias server) -> url de la web a la que accedim.
- DirectoryIndex (fitxer inicial normalment index.html) -> punto de entrada.
- DocumentRoot (carpeta de la web) -> ubicacio dels fitxers de la web.

Ara podem crear una web simple a la ruta `/var/www/html` podem crear aqui dins una carpeta i alla els nostres arxius de la nostre web.

Si volem accedir de forma local com si fos per internet haurem de "enganyar" el nostre DNS i dir que quan anem a buscar per exemple "www.daw.com" el busqui primer de forma local. Aixo es fa a `/etc/hosts`.

Una vegada tenim tant la web com el fitxer de hosts fet podem executar la seguent comanda per a que apache2 entengui que pot desplegar la web per poder veure-la amb virtualhost.

```BASH
sudo a2ensite (nom del nostre arxiu).conf
```

Una vegada fet ens demanara fer les seguents comandes per fer un reload i mirar que sigui ences el nostre apache.

```BASH
sudo systemctl reload apache2.service

sudo systemctl status apache2.service
```

Si segueix "enable" anirem a `/etc/apache2/sites-enable` i comprovarem que estigui el nostre arxiu `(nom del nostre arxiu).conf`.

Ahora intentarem anar una mica mes enllà. Instalarem PHP 8.1 i crearem la oportunitat de crear una web mes dinamica.

```BASH
sudo apt install php8.1
```

Ara executarem la seguent comanda per aplicar-ho a apache2.

```BASH
sudo a2enmod php8.1
```

I ara podem crear webs dinamiques amb PHP de la forma anterior. Ara instalarem un servei de BBDD com MySQL. Per tant executarem el seguent:

```BASH
sudo apt install mysql-server 
```

Mirem que el servei de MySQL estigui correctament.

```BASH
sudo systemctl status mysql-server
```

Ara farem una instalacio i configuracio del servei MySQL

```BASH
sudo mysql_secure_installation 
```

Ara ens fara unes preguntes de configuracio en el meu cas he posat tot que no. Les preguntes son:

- VALIDATE PASSWORD COMPONENTS
- Remove anonymous users
- Disallow root login remotely
- Remove test database
- Reload privilege tables now

Ara podem tita la comanda seguent per connectarnos al servei per terminal.

```BASH
sudo mysql -u root -p
```

Ara instalarem PHPMYADMIN per la nostre propia administracio de BBDD i totes les dependencies necesaries amb la seguent comanda.

```BASH
sudo apt install phpmyadmin php-mbstring php-gd php-zip php-json php-curl
```

Durant la instalacio ens demanara unes coses de configuracio haurem de posar "apache2" a totes les preguntes dir que "si" i quan ens demani la contrasenya posarem la que volguem.

OH NO!!! PRIMER ERROR DELS SISTEMES EL MEU PHPMYADMIN SURT EN BLANC. QUE FAIG QUE FAIG!!!

Tranquil, els sistemes fallen i s'arreclen, i aquest error en especific s'arrecla de la seguent manera.

En cas de que el error que surt esperque el modul mpm_event esta ences i s'ha de desabilitar el modul executarem les seguents comandes en ordre.

```BASH
sudo a2dismod mpm_event
sudo a2enmod mpm_prefork

sudo a2enmod php8.1

sudo systemctl restart apache2.service

apache2ctl -M | grep -E 'mpm|php'
```

Una vegada fet podem anar a `localhost/phpmyadmin` al nostre navegador de confiança (o no amb que sigui un navegador ens va be) i veurem que ja ens carrega. Una vegada fet aixo posarem la seguent comanda per temes de que MySQL autentifica usuaris amb un metode de autentificacio diferent al de PHPMYADMIN.

```BASH
ALTER user 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY '(contrasenya)';
```

Ara ja podrem iniciar sesio a PHPMYADMIN amb el nostre usuari "root" amb la contrasenya que hem introduit a la anterior comanda.

Si volem iniciar sesio per comanda a MySQL podem fer-ho amb la seguent comanda que despres ens demanara la contrasenya que hem introduit tambe a la anterior comanda.

```BASH
sudo mysql -u root -p
```