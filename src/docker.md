#Docker
Este es una guía muy básica de Docker

## 1. Instalar Docker
Se puede utilizar los repositorios 

>sudo apt-get install docker

#### Nota:
Es necesario tener instalado curl (porque es muy útil).

>sudo apt-get install curl

## 1.bis Docker-compose

Si deseamos utilizar docker-compose que parece ser también muy útil.

> sudo curl -L https://github.com/docker/compose/releases/download/v[VERSION]/docker-compose-linux-$(uname -m) -o /usr/local/bin/docker-compose


Reemplazar [VERSION] con la última, por ejemplo 2.1.1

Luego aplicamos los permisos de ejecución

> sudo chmod u+x /usr/local/bin/docker-compose

Y comprobamos la version

> docker-compose --version


## Sigue 

https://guias.donweb.cloud/como-instalar-y-usar-docker-compose-en-ubuntu-20-04/

