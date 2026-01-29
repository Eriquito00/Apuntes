# Configuracio de Apache amb Tomcat

El tomcat necesita un usuario y grupo que se llamen tomcat para poder usarse. Asi que crearemos el usuario y el grupo.

```bash
sudo useradd -s /bin/false -g tomcat -d /hopt/tomcat tomcat

sudo groupadd tomcat
```

Ahora añadiremos un repositorio necesario

```bash
sudo add-apt-repository ppa:linuxprising/java
```

Ahora instalaremos el jdk de java

```bash
sudo apt install openjdk-17-jdk
```

Ahora instalaremos tomcat i tomcat admin

```
sudo apt install tomcat9 tomcat9-admin
```

Ahora iniciamos el servicio de tomcat i miramos que el servicio este que flipas de bien

```bash
sudo systemctl start tomcat9

sudo systemctl status tomcat9
```

Ahora permitiremos el puerto 8080 por ambas direcciones pot tcp para el firewall

```bash
ufw allow from any to any port 8080
```

Ahora iremos a la configuracio de tomcat que esta en /etc/tomcat9/tomcat-users.xml

```xml
<role rolename="admin-gui" />
<role rolename="manager-gui" />
<user username="tomcat" password="pass" roles="admin-gui,manager-gui" />
```

Ahora haremos un restart del tomcat

```bash
sudo systemctl restart tomcat9
```

En tomcat los arxivos de nuestra web tendran que ir en una carpeta que nosotros decidamos pero obligatoriamente la estructura tendra que ser `/carpeta_proyecto/ROOT`.

Vale una vez tenemos esto ahora podemos crear los VirtualHost. Las webs estaran en la ruta `var/lib/tomcat9/proyecto/ROOT`.

Ahora daremos los permisos necesarios

```bash
sudo chown -R tomcat:tomcat directorio/

sudo chmod -R 755 directorio/
```

Para que tomcat se de cuenta que tenemos ahi nuestros archivos iremos a `etc/tomcat9/` i abriremos el archivo `server.xml`.

Iremos al apartado de Engine y añadiremos un bloque con los datos de nuestra web como este.

```xml
<Host name="web.com"
	appBase="ficheros_de_mi_web"
	unpackWARs="true"
	autoDeploy="true">
	<Alias>www.web.com</Alias>
</Host>
```

Una vez modificado el archivo le haremos un restart al servicio.

```bash
sudo systemctl restart tomcat9
```

Ahora volvemos al antiguo apache2 mitico de toda la vida, en el virtualhost del confiables le pondremos tres nuevas directivas para que nos redirija de este apache normal al tomcat.

```
ProxyPreserveHost On
ProxyPass / http://localhost:8080/ruta_directorio_tomcat
ProxyPassReverse / http://localhost:8080/ruta_directorio_tomcat
```

Y como no queremos que vengan los malos a rompernos la fiesta pondremos que el tomcat solo permita peticiones del localhost.

Volveremos a la ruta con el fichero del tomcat que es en `etc/tomcat9/server.xml` ahi buscaremos el apartado de Connector i descomentamos esta linea.

```xml
<Connector port="8080" protocol="HTTP/1.1"
	connectionTimeOu="20000"
	redirectPort="8443"
	address="127.0.0.1"/>
```