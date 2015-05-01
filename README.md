# Introducción

Este repositorio alberga un *contenedor Docker* para montar PostfixAdmin, está automatizado en el Registry Hub de Docker [luispa/base-postfixadmin](https://registry.hub.docker.com/u/luispa/base-postfixadmin/) conectado con el proyecto en [GitHub base-postfixadmin](https://github.com/LuisPalacios/base-postfixadmin)

Consulta este [apunte técnico sobre varios servicios en contenedores Docker](http://www.luispa.com/?p=172) para acceder a otros contenedores Docker y sus fuentes en GitHub.

## Ficheros

* **Dockerfile**: Para crear la base de servicio.
* **do.sh**: Para arrancar el contenedor creado con esta imagen.


# Personalización

### Volumen


Directorio persistente para configurar el Timezone. Crear el directorio /Apps/data/tz y dentro de él crear el fichero timezone. Luego montarlo con -v o con fig.yml

    Montar:
       "/Apps/data/tz:/config/tz"  
    Preparar: 
       $ echo "Europe/Madrid" > /config/tz/timezone


## Instalación de la imagen

Para usar la imagen desde el registry de docker hub

    totobo ~ $ docker pull luispa/base-postfixadmin


## Clonar el repositorio

Si quieres clonar el repositorio lo encontrarás en Github, este es el comando poder trabajar con él directamente

    ~ $ clone https://github.com/LuisPalacios/docker-postfixadmin.git

Luego puedes crear la imagen localmente con el siguiente comando

    $ docker build -t luispa/base-postfixadmin ./
