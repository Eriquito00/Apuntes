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
### git rm (flag) (nombre archivo)
Elimina un archivo de un directorio o area del repositorio.

Flags:
- --cached: Quita un archivo del area de preparacion i lo devuelve al area del directorio de trabajo para que NO sea incluido en el proximo commit.
- sin flag: borrara el archivo con ese nombre CUIDADO.
### git commit (atributo) (mensaje del commit)
Basicamente hace un commit con los cambios en el area de preparacion.

Atributos:
- -m: Pone un pequeño titulo al commit. Permite mensaje de commit entre "".
- sin atributo: Nos llevara a nuestro editor de codigo que hayamos puesto o nos abrira un archivo con la informacion de lo que se hara en el commit i tendremos que poner ahi nuestro mensaje del commit.
### git log
Muestra el historial de commits a nuestro repositorio. I junto a ello toda la informacion del commit i los archivos que se han añadido etc...






git diff

git diff --staged

git add

git restore "Nombre del archivo"

git commit --amend