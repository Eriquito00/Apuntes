# Lista de comandos Git i Bash

## Bash
#### cd (nombre carpeta)
Entrar a un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
#### cd ..
Salir de un directorio:
- ".." por cada directorio que queramos volver atras
- si ponemos solo cd nos volvera a la raiz
#### mkdir (nombre carpeta)
Crear un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
#### rmdir (nombre carpeta)
Borra un directorio (si el nombre de la carpeta contiene espacios entre el nombre entre "")
#### ls
Mirar los directorios o archivos que estan en la ruta donde estamos
#### clear
Limpia la linea de comandos
## Git
#### git config (flag) (apartado) (informacion)
Configura algunas cosas de git segun que flag i que apartado queramos configurar.

El apartado de informacion es basicamente lo que queramos establecer al apartado que estamos configurando.

Flags:
- \-\-global: aplica la configuracion a nivel de dispositivo.
- si no ponemos nada configura a nivel del repositorio en el que trabajamos.

Apartado:
- user.name: configura el nombre de usuario. (si no ponemos informacion nos muestra el que tenemos)
- user.email: configura el correu electronic del usuari. (si no ponemos informacion nos muestra el que tenemos)
- init.defaultBranch: configura el nombre por defecto de la primera rama de un repositorio.
#### git init
Inicializa (crea) un repositorio en la carpeta en la qual nos encontramos. (para borrar un repositorio tenemos que ir a la rama del repositorio y eliminar la carpera oculta ".git")









git add "Ruta al fichero"

git status

git commit -m "Descripcion"

git log

git diff

git diff --staged

git add

git restore "Nombre del archivo"

git commit --amend