# Lista de comandos Git i Bash

## Bash
### cd (nombre carpeta)
Entrar a un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
### cd ..
Salir de un directorio:
- ".." por cada directorio que queramos volver atras
- si ponemos solo cd nos volvera a la raiz
### mkdir (nombre carpeta)
Crear un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
### rmdir (nombre carpeta)
Borra un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
### ls
Mirar los directorios o archivos que estan en la ruta donde estamos
### clear
Limpia la linea de comandos
## Git
### git config (flag) (apartado) (informacion)
Configura algunas cosas de git segun que flag i que apartado queramos configurar.

El apartado de informacion es basicamente lo que queramos establecer al apartado que estamos configurando.

Flags:
- \-\-global: aplica la configuracion a nivel de dispositivo.
- si no ponemos nada configura a nivel del repositorio en el que trabajamos.

Apartado:
- user.name: configura el nombre de usuario. (si no ponemos informacion nos muestra el que tenemos)
- user.email: configura el correu electronic del usuari. (si no ponemos informacion nos muestra el que tenemos)
- init.defaultBranch: configura el nombre por defecto de la primera rama de un repositorio.
- core.editor: configura el editor de codigo por defecto donde nos llevara a describir los commits. (en la parte de informacion se tendra que poner entre "")
	- El editor cambia segun el que queramos, por ejemplo; VSC es "code --wait", atom es "atom --wait"... eso se puede encontrar por internet, si queremos volver a que nos lo pida en terminal de GitBash podemos poner "nano".
### git init
Inicializa (crea) un repositorio en la carpeta en la qual nos encontramos. (para borrar un repositorio tenemos que ir a la rama del repositorio y eliminar la carpera oculta ".git")
### git status
Nos muestra el estado del repositorio, entre la informacion el ultimo commit, que hay preparado para hacer commit i la rama que estamos.
### git add (nombre archivo)
Añade un archivo del area de directorio de trabajo al area de preparacion para poder añadirlo en el proximo commit.

EN VEZ DE PONER NOMBRE DE ARCHIVO PODEMOS PONER UN "." PARA AÑADIR TODOS LOS ARCHIVOS QUE ESTEN PENDIENTES AL AREA DE PREPARACION.
### git diff
Nos muestra los cambios de cada fichero que se han hecho antes de hacer un git add, asi podremos ver lo que tenia el archivo antes del ultimo commit y el estado actual del archivo.
### git restore (Nombre del archivo)
Nos restaura el estado del archivo al estado como estaba en el ultimo commit. Asi en caso de no haber hecho un commit aun y querer restaurar el archivo al estado del ultimo commit porque no queremos los cambios que hemos hecho.
### git rm (flag) (nombre archivo)
Elimina un archivo de un directorio o area del repositorio.

Flags:
- --cached: Quita un archivo del area de preparacion i lo devuelve al area del directorio de trabajo para que NO sea incluido en el proximo commit.
- sin flag: borrara el archivo con ese nombre CUIDADO.
### git commit (atributo | flag) (mensaje del commit)
Basicamente hace un commit con los cambios en el area de preparacion.

Atributos:
- -m: Pone un pequeño titulo al commit. Permite mensaje de commit entre "".
- sin atributo: Nos llevara a nuestro editor de codigo que hayamos puesto o nos abrira un archivo con la informacion de lo que se hara en el commit i tendremos que poner ahi nuestro mensaje del commit.

Flags:
- --amend: Permite modificar el ultimo commit que hemos hecho, permitiendo cambiar el mensaje del commit. CUIDADO: solo usar cuando se usan repositorios locales ya que si se ha hecho el commit i otro developer ya ha obtenido esos cambios habra poblemas en el proyecto. No permite mensaje de commit.
### git log (flag | atributo)
Muestra el historial de commits a nuestro repositorio. I junto a ello toda la informacion del commit i los archivos que se han añadido etc...

Flags:
- --oneline: muestra los commits de forma mas simplificada con la descripcion.
- sin flag: muestra toda la informacion de todos los commits de forma mas completa.

Atributos:
- -p: muestra los commits hechos con la informacion de que archivos se han modificado en cada uno y el contenido que tenia anteriormente y el contenido que se ha cambiado en ese commit.
- sin atributo: muestra toda la informacion de todos los commits de forma mas completa.
### git reset (flag) (referencia al commit)
Nos devuelve commits atras segun los commits que queramos volver atras.

Flags:
- --soft: Nos retrocede x numero de commits i los cambios que han habido desde aquel commit hasta el actual nos los deja en los archivos que tenemos en el repositorio pero no estaran guardados en el repositorio.
- --hard: Nos retrocede x numero de commits i los cambios que han habido desde aquel commit hasta el actual no nos los guarda y simplemente nos devuelve los archivos al estado en el que estaban en ese anterior commit.

Referencias:
- HEAD~x: Aqui nos referimos a quantos commits queremos volver atras, es decir si tenemos 4 commits atras podemos sustituir la x por, por ejemplo 1 para volver al commit numero 3, es decir retroceder 1 commit.
### git branch (atributo) (nombre de la rama) (nombre nuevo de la rama)
**Ves con cuidado al crear una rama ya que si ejecutas este comando en la rama inicial se creara una subrama en base a esa pero si lo ejecutas en una subrama de la rama principal se creara una subrama de la subrama.**

Atributos:
- -m: Podemos usarlo directamente con un nombre, de forma que cambiaria el nombre de la rama ACTUAL o podemos poner primero el nombre de una rama existente i despues el nombre nuevo que queremos assignar.
- -d: Elimina de forma permanente la rama con el nombre que le hemos puesto. SOLO SE PUEDE HACER EN REPOSITORIOS LOCALES.
- sin atributo: Creara una rama nueva con el nombre establecido en el repositorio. Si simplemente ponemos git branch nos mostrara todas las ramas del repositorio y nos señalara en que rama estamos ahora mismo.
### git checkout (atributos) (nombre de la rama)
Nos permite viajar entre las ramas de nuestro repositorio, simplemente ponemos el nombre de la rama que ya tiene que existir previamente y nos llevara a ella. Nos mostrara la rama a la que hemos ido.

**Ves con cuidado al crear una rama ya que si ejecutas este comando en la rama inicial se creara una subrama en base a esa pero si lo ejecutas en una subrama de la rama principal se creara una subrama de la subrama.**

Atributos:
- -b: En este caso nos combina el uso de branch i checkout, basicamente nos creara una rama con el nombre que hemos puesto i nos llevara directamente a la rama que acabamos de crear.
- sin atributos: nos permite viajar entre ramas de nuestro repositorio TANTO LOCAL COMO REMOTO.
### git merge (nombre rama que quiero fusionar | flag)
**ANTES DE FUSIONAR TIENES QUE ESTAR EN LA RAMA QUE RECIBE LOS CAMBIOS.**
Fusiona la rama que especificamos con la rama en la que nos encontramos. Tambien como las fusionamos podemos ver los commits que se han hecho en la rama que ha sido fusionada.

Flags:
- --continue: En caso de haber tenido conflictos, una vez se han arreglado en vez de hacer un commit podemos usar merge con continue para confirmar el merge y finalizar.
- sin flag: Si estamos en una rama i ponemos el nombre de otra nos hara el merge.
### git clone (enlace al repositorio)
Clona un repositorio de GitHub a nuestro dispositivo local mediante el enlace que podemos conseguir en el repositorio que queramos clonar. Tambien obtenemos todos los commits i la informacion de las versiones.
### git remote (atributo)
Vemos el nombre que se ha assignado o el nombre que tiene el repositorio en GitHub.

Atributos:
- -v: nos muestra las operaciones que podemos hacer en esa rama como "fetch" i "push" i las respectivas URL.
- sin atributo: nos muestra el nombre del repositorio remoto.
#### git remote add origin (link al repositorio)
Gracias a git remote en caso de tener nuestro repositorio local i despues querer migrarlo a GitHub podemos ejecutar esta comanda y asi enlazar nuestro repositorio local con el repositorio remoto, estos son los pasos: 
1. Crear el repositorio remoto en GitHub.
2. Enlazarlo con git remote add i el link del repositorio.
3. Hacer el push para subirlo todo al repositorio remoto.
### git push (nombre repositorio remoto) (nombre rama)
Sube todos los cambios que hemos hecho en nuestros commits a nuestro repositorio remoto, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".
### git pull (nombre repositorio remoto) (nombre rama)
Usado para obtener el contenido de un repositorio remoto para que el repositorio local tenga los cambios que se han hecho y que ya tiene el repositorio remoto, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".
### git fetch (nombre repositorio remoto) (nombre rama)
Usado para saber si hay cambios en el repositorio remoto que podamos traer a nuestro repositorio local SIN TRAERLOS solo nos muestra si hay nuevos cambios o no, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".