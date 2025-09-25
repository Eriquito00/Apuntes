# Lista de comandos Git y Bash

## Bash
### cd (nombre carpeta)
Entrar a un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre"")
### cd ..
Salir de un directorio:
- ".." Por cada directorio que queramos volver atrás
- si ponemos solo cd nos volverá a la raíz
### mkdir (nombre carpeta)
Crear un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre"")
### rmdir (nombre carpeta)
Borra un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre"")
### ls
Mirar los directorios o archivos que están en la ruta donde estamos
### clear
Limpia la línea de comandos
## Git
### git config (flag) (apartado) (información)
Configura algunas cosas de git según qué flag y que apartado queramos configurar.

El apartado de información es básicamente lo que queramos establecer al apartado que estamos configurando.

Flags:
- \-\-global: aplica la configuración a nivel de dispositivo.
- si no ponemos nada, configura a nivel del repositorio en el que trabajamos.

Apartado:
- user.name: configura el nombre de usuario. (si no ponemos información nos muestra el que tenemos)
- user.email: configura el correo electrónico del usuario. (si no ponemos información nos muestra el que tenemos)
- init.defaultBranch: configura el nombre por defecto de la primera rama de un repositorio.
- core.editor: configura el editor de código por defecto donde nos llevara a describir los commits. (en la parte de información se tendrá que poner entre"")
	- El editor cambia según el que queramos, por ejemplo; VSC es "code --wait", atom es "atom --wait"... eso se puede encontrar por internet, si queremos volver a que nos lo pida en terminal de GitBash podemos poner "nano".
### git init
Inicializa (crea) un repositorio en la carpeta en la cual nos encontramos. (para borrar un repositorio tenemos que ir a la rama del repositorio y eliminar la carpeta oculta ".git")
### git status
Nos muestra el estado del repositorio, entre la información el último commit, que hay preparado para hacer commit y la rama que estamos.
### git add (nombre archivo)
Añade un archivo del área de directorio de trabajo al área de preparación para poder añadirlo en el próximo commit.

EN VEZ DE PONER NOMBRE DE ARCHIVO PODEMOS PONER UN "." PARA AÑADIR TODOS LOS ARCHIVOS QUE ESTÉN PENDIENTES AL ÁREA DE PREPARACIÓN.
### git diff
Nos muestra los cambios de cada fichero que se han hecho antes de hacer un git add, así podremos ver lo que tenía el archivo antes del último commit y el estado actual del archivo.
### git restore (Nombre del archivo)
Nos restaura el estado del archivo al estado como estaba en el último commit. Así, en caso de no haber hecho un commit aún y querer restaurar el archivo al estado del último commit porque no queremos los cambios que hemos hecho.
### git rm (flag) (nombre del archivo)
Elimina un archivo de un directorio o área del repositorio.

Flags:
- --cached: Quita un archivo del área de preparación y lo devuelve al área del directorio de trabajo para que NO sea incluido en el próximo commit.
- sin flag: borrará el archivo con ese nombre CUIDADO.
### git commit (atributo | flag) (mensaje del commit)
Básicamente hace un commit con los cambios en el área de preparación.

Atributos:
- -m: Pone un pequeño título al commit. Permite mensaje de commit entre"".
- sin atributo: Nos llevará a nuestro editor de código que hayamos puesto o nos abrirá un archivo con la información de lo que se hará en el commit y tendremos que poner ahí nuestro mensaje del commit.

Flags:
- --amend: Permite modificar el último commit que hemos hecho, permitiendo cambiar el mensaje del commit. CUIDADO: solo usar cuando se usan repositorios locales, ya que si se ha hecho el commit y otro developer ya ha obtenido esos cambios habrá problemas en el proyecto. No permite mensaje de commit.
### git log (flag | atributo)
Muestra el historial de commits a nuestro repositorio. I junto a ello toda la información del commit y los archivos que se han añadido, etc.

Flags:
- --oneline: muestra los commits de forma más simplificada con la descripción.
- sin flag: muestra toda la información de todos los commits de forma más completa.

Atributos:
- -p: muestra los commits hechos con la información de qué archivos se han modificado en cada uno y el contenido que tenía anteriormente y el contenido que se ha cambiado en ese commit.
- sin atributo: muestra toda la información de todos los commits de forma más completa.
### git reset (flag) (referencia al commit)
Nos devuelve commits atrás según los commits que queramos volver atrás.

Flags:
- --soft: Nos retrocede x número de commits y los cambios que ha habido desde aquel commit hasta el actual nos los deja en los archivos que tenemos en el repositorio, pero no estarán guardados en el repositorio.
- --hard: Nos retrocede x número de commits y los cambios que ha habido desde aquel commit hasta el actual no nos los guarda y simplemente nos devuelve los archivos al estado en el que estaban en ese anterior commit.

Referencias:
- HEAD~x: Aquí nos referimos a quantos commits queremos volver atrás, es decir si tenemos 4 commits atrás podemos sustituir la x por, por ejemplo 1 para volver al commit número 3, es decir retroceder 1 commit.
### git branch (atributo) (nombre de la rama) (nombre nuevo de la rama)
**Ves con cuidado al crear una rama, ya que si ejecutas este comando en la rama inicial se creará una sub rama basándose en esa, pero si lo ejecutas en una sub rama de la rama principal se creará una sub rama de la sub rama.**

Atributos:
- -m: Podemos usarlo directamente con un nombre, de forma que cambiaria el nombre de la rama ACTUAL, o podemos poner primero el nombre de una rama existente y después el nombre nuevo que queremos asignar.
- -d: Elimina de forma permanente la rama con el nombre que le hemos puesto. SOLO SE PUEDE HACER EN REPOSITORIOS LOCALES.
- -a: Nos muestra las ramas remotas que tenemos en GitHub (no poner el nombre de la rama)
- sin atributo: Creará una rama nueva con el nombre establecido en el repositorio. Si simplemente ponemos git branch nos mostrará todas las ramas del repositorio y nos señalará en que rama estamos ahora mismo.
### git checkout (atributos) (nombre de la rama)
Nos permite viajar entre las ramas de nuestro repositorio, simplemente ponemos el nombre de la rama que ya tiene que existir previamente y nos llevara a ella. Nos mostrará la rama a la que hemos ido.

**Ves con cuidado al crear una rama, ya que si ejecutas este comando en la rama inicial se creará una sub rama basándose en esa, pero si lo ejecutas en una sub rama de la rama principal se creará una sub rama de la sub rama.**

Atributos:
- -b: En este caso nos combina el uso de branch y checkout, básicamente nos creara una rama con el nombre que hemos puesto y nos llevara directamente a la rama que acabamos de crear.
- sin atributos: nos permite viajar entre ramas de nuestro repositorio TANTO LOCAL COMO REMOTO.
### git merge (nombre rama que quiero fusionar | flag)
**ANTES DE FUSIONAR TIENES QUE ESTAR EN LA RAMA QUE RECIBE LOS CAMBIOS.**
Fusiona la rama que especificamos con la rama en la que nos encontramos. También como las fusionamos podemos ver los commits que se han hecho en la rama que ha sido fusionada.

Flags:
- --continue: En caso de haber tenido conflictos, una vez se han arreglado en vez de hacer un commit podemos usar merge con continue para confirmar el merge y finalizar.
- sin flag: Si estamos en una rama y ponemos el nombre de otra, nos hará el merge.
### git clone (enlace al repositorio)
Clona un repositorio de GitHub a nuestro dispositivo local mediante el enlace que podemos conseguir en el repositorio que queramos clonar. También obtenemos todos los commits y la información de las versiones.
### git remote (atributo)
Vemos el nombre que se ha asignado o el nombre que tiene el repositorio en GitHub.

Atributos:
- -v: nos muestra las operaciones que podemos hacer en esa rama como "fetch" i "push" i las respectivas URL.
- sin atributo: nos muestra el nombre del repositorio remoto.
#### git remote add origin (link al repositorio)
Gracias a git remote en caso de tener nuestro repositorio local y después querer migrarlo a GitHub podemos ejecutar esta comanda y así enlazar nuestro repositorio local con el repositorio remoto, estos son los pasos: 
1. Crear el repositorio remoto en GitHub.
2. Enlazarlo con git remote add y el link del repositorio.
3. Hacer el push para subirlo todo al repositorio remoto.
### git push (nombre repositorio remoto) (atributo) (nombre rama)
Sube todos los cambios que hemos hecho en nuestros commits a nuestro repositorio remoto, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".

Atributos:
- -d: nos elimina una rama en el repositorio remoto de GitHub.
- sin atributo: Sube todos los cambios que hemos hecho en nuestros commits a nuestro repositorio remoto.
### git pull (nombre repositorio remoto) (nombre rama)
Usado para obtener el contenido de un repositorio remoto para que el repositorio local tenga los cambios que se han hecho y que ya tiene el repositorio remoto, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".
### git fetch (nombre repositorio remoto) (nombre rama)
Usado para saber si hay cambios en el repositorio remoto que podamos traer a nuestro repositorio local SIN TRAERLOS solo nos muestra si hay nuevos cambios o no, normalmente el nombre del repositorio es "origin" i el nombre de la rama principal "main".