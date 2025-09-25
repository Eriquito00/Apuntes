# Áreas de Git
## Directorio de trabajo
Es la carpeta del proyecto que contiene los archivos y el directorio .git del repositorio, básicamente es lo que vemos nosotros desde la interfaz del sistema operativo. Los archivos que están en esta área se consideran archivos modificados.
## Área de preparación
Esta área está entre el directorio de trabajo y el repositorio. Es el conjunto de archivos y cambios que serán incluidos en el próximo commit. Es decir, si hay cambios que hemos hecho, pero aún no los queremos incluir al repositorio, podemos conservarlos en el área de preparación. Los archivos que están en esta área se consideran archivos preparados.
## Repositorio
En el repositorio se aplicarán los cambios establecidos en el commit, es decir, lo que no se haya incluido en el commit no se subirá al repositorio. Es el directorio que incluye los metadatos y las versiones del proyecto, junto a eso todos los cambios que se han hecho cada commit.

También es la parte del repositorio que se clona cuando hacemos un clon de algún repositorio de GitHub, por ejemplo, y también es el área más importante de las tres. Los archivos que están en esta área se consideran archivos confirmados.

## Estados de los archivos
Podemos ver que archivo está en cada área como modificada o preparada usando git status.
### Modificada
Se considera que la versión del archivo contiene cambios que no están en el repositorio y no se han añadido al área de preparación.
### Preparados
Si la versión del archivo contiene cambios que no están en el repositorio, pero ha sido añadido al área de preparación, se considera preparado.
### Confirmados
Si la versión del archivo ya está en el directorio de Git se considera que está confirmado.