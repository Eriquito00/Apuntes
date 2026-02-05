# Configuracio de Apache amb Python + Flask

## Instalar i configurar Python con Flask

Primero instalaremos python para poder empezar. Y comprovaremos que tenemos instalado python.

```BASH
python3 --version
```

Ahora instalaremos la libreria de dotenv de python.

```BASH
sudo apt install python3-dotenv
```

Ahora instalaremos otra version de python, no se porque pero bueno ahi esta no

```BASH
sudo apt install python3.10-venv
```

Creamos una carpeta para el proyecto y poder guardar ahi todo lo que necesitemos.

```BASH
sudo mkdir mi_proyecto
```

Entramos a la carpeta del proyecto y creamos el "entorno virtual" de python.

```BASH
python3 -m venv .venv
```

Ejecutamos el entorno virtual que acabamos de crear

```BASH
. .venv/bin/activate
```

Una vez hecho podemos crear el primer fichero python para empezar a darle cañita.

```python
# importar flask
from flask import Flask render_template

# definir app como render
app = flask(__name__)

@app.route("/")
# funcion para renderizar el fichero de entrada
def hello_world():
	return render_template("fichero.html")
	
# ejecutar esto al inicio
if __name__ == "__main__":
	app.run(debug=True)
```

Instalamos la dependencia de flask para poder usarlo en el brutal increible script de python que nos acabamos de copiar

```BASH
pip install flask
```

Comprovamos que el flask esta bien instalado

```BASH
flask --version
```

Le damos cañita con el flask al script de python que hemos hecho

```BASH
flask --app fichero(python) run
```

Creamos una variable de entorno para poder cambiar el puerto por el que escucha flask, por la puta cara eh pero hace falta

```BASH
# cambiar el puerto por donde escucha flask
export FLASK_RUN_PORT=5500

# cambiar la red por donde escucha flask
export FLASK_RUN_HOST=172.18.1.1
```

Para poder mostrar los ficheros dentro del proyecto creamos una carpeta que se llama obligatoriamente "templates" y ahi dentre ponemos los ficheros html para poder llamar a los ficheros html desde los scripts de python.

Crearemos un fichero .env ahora por la cara porque hacerlo desde el principio no cundia asi que tenemos que cargarnos las variables de entorno por terminal.

```BASH
unset FLASK_RUN_PORT
unset FLASK_RUN_HOST
```

Ahora si que si hacemos las cosas bien y creamos un fichero .env en la raiz del proyecto y ponemos exactamente lo mismo en el fichero.

```.env
FLASK_RUN_PORT=5500
FLASK_RUN_HOST=172.18.1.1
```

## Instalar y configurar Gunicorn

Instalaremos Gunicorn en nuestra maravillosa maquina

```BASH
pip install gunicorn
```

Y ahora le damos caña cañisima encendiendo la encendida. Basicamente pillaremos la instancia en le fichero de python que tiene del flask y lo encenderemos con gunicorn

```BASH
gunicorn fichero(python):app
```

Ahora el maldigos gunicorn no aplica lo que le hemos dicho en el .env asi que tenemos encenderlo diciendole la ip y el puerto porque es minguito el malditos.

```BASH
gunicorn -b 172.18.1.1:3000 fichero(python):app 
```

## Aplicando apache

Con esto y un bizcocho el malvados vuelve, le vamos a meter un apache por delante para mostrar la web.

Nos iremos a un fichero de configuracion dentro de apache, es decir a los virtualhost que estan en la ruta `/etc/apache2/sites-available` y le añadiremos lo siguiente para que nos muestre lo que queremos.

```conf
ProxyPreserveHost On
ProxyPass / http://127.0.0.1:3000 (o cambiamos la ip y el puerto al que queramos)
ProxyPassReverse / http://127.0.0.1:3000 (o cambiamos la ip y el puerto al que queramos)
```

Ahora cuando entremos a ese virtual host nos hara un redirect a la web que tenemos en el gunicorn.

## Gestionando acceso publico o privado segun el host

Creamos un nuevo archivo de python para la nueva web

```python
# importar flask
from flask import Flask render_template

# definir app como render
app = flask(__name__)

@app.route("/")
# funcion para renderizar el fichero de entrada
def hello_world():
	return "<p>Hola classe de DAW2, esta es la zona publica chat</p>"

@app.route("/admin")
def hello_private():
	if request.remote_addr != "127.0.0.1":
	abort(403)
	return "<p>Hola classe de DAW2, esta es la zona privada chat</p>"

# ejecutar esto al inicio
if __name__ == "__main__":
	app.run(debug=True)
```

Ahora arrancaremos lo que seria esta nueva obra de ingenieria moderna.

```bash
gunicorn fichero(python):app
```