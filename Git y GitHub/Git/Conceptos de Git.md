# Conceptos de Git
***GIT SE USA DE FORMA LOCAL Y GITHUB SE USA DE FORMA REMOTA***
## Controladores de versiones
Un controlador de versiones es un sistema encargado de almacenar y guardar los cambios realizados en un proyecto de desarrollo de software.
## Repositorios
Un repositorio es una colección de archivos de distintas versiones de un proyecto.

Tipos de repositorio:
- Repositorio local: Un repositorio local es un repositorio único y que solo puede estar en un mismo dispositivo. (Git)

- Repositorio remoto: Es un repositorio que se puede acceder desde varios dispositivos y poder almacenar cambios y actualizaciones de varios desarrolladores. (GitHub)

Un repositorio es un "proyecto" en el que se almacena toda la información, normalmente este término se usa en GitHub, ya que ***GitHub se usa en la nube***, básicamente está pensado para colaborar con otros desarrolladores y poder subir y descargar los cambios que hayamos hecho u otros desarrolladores del repositorio hayan hecho.

Si tenemos un proyecto con varios desarrolladores en vez de tener cada uno su repositorio local de Git se usa GitHub para poder tener un repositorio y que cada uno haga una copia de dicho repositorio y poder subir u obtener los cambios que hayamos hecho u otros hayan hecho.
## Ramas
Una rama es una copia exacta y paralela de un proyecto, se recomienda crear como mínimo una rama aparte de la principal que contiene el proyecto en su "fase final" para guardar en esta rama paralela NO DEFINITIVA los nuevos cambios y si todo funciona correctamente esta vez si enviarlo a la rama principal.

Para combinar las ramas se usa un término llamado ***MERGE*** que es básicamente juntar una rama con contenido ya comprobado y correcto a otra rama.

Una rama en Git es básicamente una línea independiente de desarrollo del repositorio, es decir, si queremos probar alguna cosa un tanto arriesgada en nuestro repositorio, podemos crear una rama del proyecto basado en el último commit y probar en esta nueva rama sin miedo a que no funcione el código después de probarlo.

A la vez también podemos seguir haciendo cambios en la rama principal y después combinar la rama que habíamos creado con la rama inicial del proyecto.
## Commit
Componente básico de la línea de tiempo de un proyecto de Git, un commit sería básicamente una "instantánea" o una "imagen" del proyecto en el momento de hacer el commit. De esta forma cuando un commit hay algún archivo mal hecho o que da un error y queremos volver a antes de hacerlo podemos volver al anterior commit que hemos hecho.

ESCRIBIR MENSAJES DESCRIPTIVOS EN LOS COMMIT ES MUY ÚTIL PARA DESCRIBIR LOS CAMBIOS QUE SE HAN EJECUTADO EN DICHO COMMIT.

Registran los cambios que se han hecho entre archivos respecto al anterior commit. Guardan tanto cuando sé:

- Eliminan
- Crear
- Mueven
- Cambian de nombre
- Quien ha hecho el commit
- Fecha y hora
- **Comentario que ponemos al hacerlo**

Cada commit tiene su Hash que es un algoritmo que crea un código único en este caso para cada commit.
## Merge
Nos permite combinar ramas. Se usa sobre todo cuando queremos aplicar alguna función un tanto arriesgada y para ello creamos una rama, una vez la funcionalidad está aplicada y probada y todo funciona correctamente podemos hacer el merge para volver a fusionar la rama en la que hemos hecho esta funcionalidad con el proyecto principal.

Es un proceso que permite combinar varias líneas independientes de desarrollo en una sola rama una vez ya no necesitamos esas ramas sobre las que hemos hecho esos cambios experimentales. **Para fusionar ramas tienes que estar en la rama que RECIBIRÁ el merge**.
## GitBash
Es una herramienta que permite ejecutar comandos de Git, es una línea de comandos que se instala automáticamente al instalar Git, este será el acceso que tenemos entre nosotros (desarrollador) y el proyecto (repositorio).