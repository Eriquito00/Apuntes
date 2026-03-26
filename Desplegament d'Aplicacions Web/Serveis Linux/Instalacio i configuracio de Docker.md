# Instalacio i configuracio de Docker
Instal·lar un servei nginx (1r port meu - 2n port del servei)
```bash
docker container run -d -p 8083:80 nginx
```

Instal·lar un servei posant uns arxius locals a la imatge ($PWD és on estàs ara)
```bash
docker container run -d -p 8083:80 -v $PWD:/(url a on nginx carrega les webs) --name (nom) nginx
```

Correr un container de docker i fer que despres d'executarse s'elimini
```bash
docker container run --rm (nom del contenidor)
```

Mostrar els contenidors encesos que tenim a docker (podem afegir -a per mostrar els apagats)
```bash
docker container ps
```

Eliminar un contenidor que ja no volem
```bash
docker container rm (nom del contenidor)
```

Aturar un contenidor de docker
```bash
docker container stop (nom del contenidor)
```

Engegar un contenidor de docker
```bash
docker container start (nom del contenidor)
```

Per poder veure el contenidor i l'estructura del contenidor podem fer el següent
```bash
docker container exec -it (nom del contenidor) /bin/bash
```

## Creació i ús d'imatges

Creació i ús d'imatges Crear un fitxer de docker
```bash
gedit Dockerfile
```

Posar el contingut següent
```dockerfile
FROM httpd:latest

ADD (site en .tar o .gz) (ruta on surten les webs al servei)
ADD web.tar /usr/local/apache2/htdocs
```

Crear una imatge
```bash
docker image build -t (nom de la imatge):(tag de la imatge) (on és el DockerFile)

docker image build -t miweb:v1 .
```

Ara crearem un contenidor amb la nostra imatge
```bash
docker container run -d -p 9000:80 --name miweb miweb:v1
```

Mirar las imagenes que tenemos
```bash
docker images
```