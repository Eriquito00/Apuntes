# Conceptos de GitHub
GitHub es un servicio de hosting que nos permite almacenar proyectos de desarrollo de software y control de versiones usando Git.

Con Git los repositorios eran en local pero en un proyecto de varios desarrolladores nos interesaria poder trabajar con una herramienta en la que todos puedan hacer los cambios en el mismo repositorio.
## Clonar un repositorio
Crear un copia local de un repositorio remoto en nuestro dispositivo incluyendo las versiones y commits. Esto se usa en caso de tener un repositorio en GitHub i querer editar los archivos en nuestro dispositivo local.
## Origin
Nombre que le asignamos normalmente al repositorio remoto que clonamos a nuestro dispositivo local.
## Fetch
Usado para verificar los cambios del repositorio remoto sin combinar esos cambios al repositorio local, de forma que obtiene los cambios que se han hecho en el repositorio remoto y pero no los trae al repositorio local. Por lo tanto permite ver si se han hecho o no cambios en el repositorio remoto desde la ultima vez que actualizamos el repositorio local.
## Pull
Usado para descargar el contenido de un repositorio remoto e inmediatamente actualizar un repositorio local para que tanto el local como el remoto tengan la misma informacion.
## Push
Enviar los cambios que hemos hecho en nuestra maquina local a nuestro repositorio remoto. Para que los dos repositorios esten sincronizados y que tanto el local como el remoto tengan los mismos cambios.