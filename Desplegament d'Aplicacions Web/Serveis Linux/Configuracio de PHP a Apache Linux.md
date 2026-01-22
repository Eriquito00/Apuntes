# Configuracio de PHP a Apache Linux

Per configurar nomes per un website les directives podem anar als fitxer de configuracio de cada website que podem trobar a: `/etc/apache2/sites-available/`.

La configuracio de la directiva per poder modificar el temps maxim de proces i el maxim de memoria podem afegir el seguent:

```conf
php_value (nom de la variable) (valor)
php_value memory_limit 16M
```

La configuracio que podem fer com administradors als fitxers d'apache directament per segons el website es permeti poder consultar un fitxer .htaccess i fer les directives que indica o no, podem modificar el fitxer `/etc/apache/apache2.conf` i cambiar el seguent:

```.htaccess
<Directory />
	AllowOverride All (permes a tothom) - None (permes a ningu)
</Directory />
```

Si volem fer-ho per afectar nomes a un afegirem la direccio a la seva web.

```.htaccess
<Directory /var/www/brutaliticawebsite>
	AllowOverride All (permes) - None (no permes)
</Directory />
```

Si volem fer un redirect perque els usuaris no arribin a la nostre web que no esta activa ara mateix i volem reenviar a un altre podem fer el seguent als fitxer de configuracio de cada website:

```.htaccess
Redirect 301 / https://webalternativa.com
```

Para poder usar los modulos hace falta ejecutar el siguiente comando:

```bash
a2enmod alias
```

## Deshabilitar un modulo

Podemos deshabilitar la version de php que queramos con el comando de deshabilitar modulos

```BASH
sudo a2dismod php8.3
```

Ahora podemos habilitar el modulo para manejar varias versiones de php de la siguiente forma.

```BASH
sudo a2enmod mpm_event
```

Instalamos php-fpm para poder manejar varias versiones con:

```BASH
sudo apt install php-fpm
```

Ara instalarem el servei que gestionara les versions de php com un servei

```BASH
sudo apt install libapache2-mod-fcgid
```

Ahora habilitaremos la configuracion que acabamos de instalar que lo podemos hacer de la siguiente forma:

```BASH
sudo a2enconf php8.1-fpm
```

Ahora activamos el modulo de proxy de fcgi

```BASH
sudo a2enmod proxy_fcgi
```

Ahora necesitaremos arrancar / reiniciar / reparar / restaurar segun como se haya liado nuestro apache

```BASH
sudo systemctl start / reload apache2.service
```

## Varias versiones de php

Ahora instalaremos los siguientes paquetes:

```BASH
sudo apt install software-properties-common gnupg2 -y
```

Ahora añadiremos una fuentes para descargar php ya empaquetado

```BASH
sudo add-apt-repository ppa:ondrej/php
```

Ahora instalaremos las version / versiones que queramos

```BASH
sudo apt install php8.2 php8.2-fpm php8.2-cli
```

```BASH
sudo apt install php8.3 php8.3-fpm php8.3-cli
```

Ahora iniciamos el servicio de php en la version que queramos

```BASH
sudo systemctl start php8.2-fpm.service
```

```BASH
sudo systemctl start php8.3-fpm.service
```

Para cambiar la version de php que tiene apache cambiaremos la siguiente configuracion

```BASH
sudo a2disconf php8.1-fpm
```

Y podemos activar otra version activando la siguiente configuracion

```BASH
sudo a2enconf php8.2-fpm
```

Para modificar por cada site la version de php que quieres usar puedes poner en los ficheros de configuracion del site las siguientes lineas.

```BASH
<FilesMatch \.php$>
	SetHandler "proxy:unix:/run/php/php8.1-fpm.sock|fcgi://localhost"
</FilesMatch>
```
