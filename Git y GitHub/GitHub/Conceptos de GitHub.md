# Conceptos de GitHub
GitHub es un servicio de hosting que nos permite almacenar proyectos de desarrollo de software y control de versiones usando Git.

Con Git los repositorios eran en local, pero en un proyecto de varios desarrolladores nos interesaría poder trabajar con una herramienta en la que todos puedan hacer los cambios en el mismo repositorio.
## Clonar un repositorio
Crear una copia local de un repositorio remoto en nuestro dispositivo, incluyendo las versiones y commits. Esto se usa en caso de tener un repositorio en GitHub y querer editar los archivos en nuestro dispositivo local.
## Origin
Nombre que usamos para referirnos al repositorio remoto que clonamos a nuestro dispositivo local.
## Fetch
Usado para verificar los cambios del repositorio remoto sin combinar esos cambios al repositorio local, de forma que obtiene los cambios que se han hecho en el repositorio remoto y, pero no, los trae al repositorio local. Por lo tanto, permite ver si se han hecho o no cambios en el repositorio remoto desde la última vez que actualizamos el repositorio local.
## Pull
Usado para descargar el contenido de un repositorio remoto e inmediatamente actualizar un repositorio local para que tanto el local como el remoto tengan la misma información.
## Push
Enviar los cambios que hemos hecho en nuestra máquina local a nuestro repositorio remoto. Para que los dos repositorios estén sincronizados y que tanto el local como el remoto tengan los mismos cambios.
## Fork
Crear una copia en nuestra cuenta de GitHub de un repositorio de GitHub que no es nuestro. I luego podemos hacer una copia de ese repositorio de forma local en nuestro dispositivo con Git.

Cuando hacemos un fork de un repositorio, si este inicial se le hacen más commits al nuestro, obviamente no se le harán esos cambios, pero sí que se podrían llegar a sincronizar.

Para poder llevar este repositorio que hemos hecho fork a nuestro dispositivo local será tan fácil como hacer un clon del repositorio que tenemos nosotros como copia.
## Pull requests
Solicitud de combinar tus cambios con el repositorio original del proyecto.

Si nosotros hacemos cambios en nuestro repositorio copiado, podríamos llegar a hacer un pull request al repositorio inicial del que hicimos el fork para aplicar los cambios al repositorio original, pero esto tiene que ser aceptado por un contribuidor del repositorio original.

También podemos hacer pull request internos en nuestros propios repositorios, por ejemplo, si tenemos varias ramas y queremos fusionar una rama a otra tendremos que hacer los pasos de un pull request para unir los cambios a esta rama a la que nos adherimos.
## Issues
Usado para proponer cambios a un repositorio que no es nuestro y crear un pequeño debate por un cambio que quieras implementar.

También se puede usar en propios repositorios para poner notas, reportar un bug, poner funciones que queremos implementar en un futuro o tareas pendientes.

Podemos poner etiquetas según la conveniencia que muestre. Asignarlo a algún colaborador en específico, cuando hacemos un pull request podemos automáticamente solucionar un issue y cerrarlo, para cerrarlo podemos cerrarlo como hecho o como que no se implementara.

También se pueden crear plantillas o estándares de issues en nuestro repositorio, de forma que será más fácil filtrar la información que queremos en según que issue se abra.
## Conflictos entre Git y GitHub
Pongámonos en el caso que hemos creado una rama en nuestro repositorio de GitHub y ahora queremos hacer cambios en ella de forma local, pero en nuestro repositorio local de Git no tenemos esa rama.

En este caso para poder usar esa rama tendremos que hacer 'git pull origin' o 'git fetch origin' i así podremos obtener los cambios del repositorio, pero podremos ver que si hacemos 'git branch' para ver las ramas no estará la nueva, por lo tanto, ahora solo tendremos que hacer un 'git checkout (nombre de la rama)' ahora sí, podremos usar esta rama con el contenido que tenía en GitHub.