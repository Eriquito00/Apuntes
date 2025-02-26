# Conceptos de Git
***GIT SE USA DE FORMA LOCAL Y GITHUB SE USA DE FORMA REMOTA***
## Controladores de versiones
Un controlador de versiones es un sistema encargado de almacenar i guardar los cambios realizados en un proyecto de desarrollo de software.
## Repositorios
Un repositorio es una coleccion de archivos de distintas versiones de un proyecto.

Tipos de repositorio:
- Repositorio local: Un repositorio local es un repositorio unico y que solo puede estar en un mismo dispositivo. (Git)

- Repositorio remoto: Es un repositorio que se puede acceder desde varios dispositivos y poder almacenar cambios y actualizaciones de varios desarrolladores. (GitHub)

Un repositorio es un "proyecto" en el que se almacena toda la informacion, normalmente este termino se usa en GitHub, ya que ***GitHub se usa en la nube***, basicamente esta pensado para colaborar con otros desarrolladores y poder subir i descargar los cambios que hayamos hecho o otros desarrolladores del respositorio hayan hecho.

Si tenemos un proyecto con varios desarrolladores en vez de tener cada uno su repositorio local de Git se usa GitHub para poder tener un repositorio y que cada uno haga una copia de dicho repositorio y poder subir o obtener los cambios que hayamos hecho o otros hayan hecho.
## Ramas
Una rama es una copia exacta i paralela de un proyecto, se recomienda crear como minimo una rama a parte de la principal que contiene el proyecto en su "fase final" para guardar en esta rama paralela NO DEFINITIVA los nuevos cambios y si todo funciona correctamente esta vez si enviarlo a la rama principal.

Para combinar las ramas se usa un termino llamado ***MERGE*** que es basicamente juntar una rama con contenido ya comprovado y correcto a otra rama.

Una rama en Git es basicamente una linea independiente de dessarrollo del repositorio, es decir, si queremos probar alguna cosa un tanto arriesgada en nuestro repositorio, podemos crear una rama del proyecto basado en el ultimo commit y probar en esta nueva rama sin miedo a que no funcione el codigo despues de probarlo.

Ala vez tambien podemos seguir haciendo cambios en la rama principal y despues combinar la rama que habiamos creado con la rama inicial del proyecto.
## Commit
Componente basico de la linea de tiempo de un proyecto de Git, un commit seria basicamente una "instantanea" o una "imagen" del proyecto en el momento de hacer el commit. De esta forma cuando un commit hay algun archivo mal hecho o que da un error y queremos volver a antes de hacerlo podemos volver al anterior commit que hemos hecho.

ESCRIBIR MENSAJES DESCRIPTIVOS EN LOS COMMIT ES MUY UTIL PARA DESCRIBIR LOS CAMBIOS QUE SE HAN EJECUTADO EN DICHO COMMIT.

Registran los cambios que se han hecho entre archivos respecto al anterior commit. Guardan tanto cuando se:

- Eliminan
- Crear
- Mueven
- Cambian de nombre
- Quien ha hecho el commit
- Fecha i hora
- **Commentario que ponemos al hacerlo**

Cada commit tiene su Hash que es un algoritmo que crea un codigo unico en este caso para cada commit.
## Merge
Nos permite combinar ramas. Se usa sobretodo cuando queremos aplicar alguna funcion un tanto arriesgada y para ello creamos una rama, una vez la funcionalidad esta aplicada y probada y todo funciona correctamente podemos hacer el merge para volver a fusionar la rama en la que hemos hecho esta funcionalidad con el proyecto principal.

Es un proceso que permite combinar varias lineas independientes de desarrollo en una sola rama una vez ya no necesitamos esas ramas sobre las que hemos hecho esos cambios experimentales. **Para fusionar ramas tienes que estar en la rama que RECIBIRA el merge**.
## GitBash
Es una herramienta que permite ejecutar comandos de Git, es una linea de comandos que se instala automaticamente al instalar Git, este sera el acceso que tenemos entre nosotros (desarrollador) y el proyecto (repositorio).