# Areas de Git
## Directorio de trabajo
Es la carpeta del proyecto que contiene los archivos y el directorio .git del repositorio, basicamente es lo que vemos nosotros desde la interfaz del sistema operativo. Los archivos que estan en esta area se consideran archivos modificados.
## Area de preparacion
Esta area esta entre el directorio de trabajo y el repositorio. Es el conjunto de archivos y cambios que seran incluidos en el proximo commit. Es decir si hay cambios que hemos hecho pero aun no los queremos incluir al repositorio podemos conservarlos en el area de preparacion. Los archivos que estan en esta area se consideran archivos preparados.
## Repositorio
En el repositorio se aplicaran los cambios establecidos en el commit, es decir lo que no se haya incluido en el commit no se subira al repositorio. Es el directorio que incluye los metadatos y las versiones del proyecto, junto a eso todos los cambios que se han hecho cada commit.

Tambien es la parte del repositorio que se clona cuando hacemos un clon de algun repositorio de GitHub por ejemplo, i tambien es el area mas importante de las tres. Los archivos que estan en esta area se consideran archivos confirmados.

## Estados de los archivos
Podemos ver que archivo esta en cada area como modificada o preparada usando git status.
### Modificada
Se considera que la version del archivo contiene cambios que no estan en el repositorio y no se han añadido al area de preparacio.
### Preparados
Si la version del archivo contiene cambios que no estan en el repositorio pero ha sido añadido al area de preparacion se considera preparado.
### Confirmados
Si la version del archivo ya esta en el directorio de Git se considera que esta confirmado.