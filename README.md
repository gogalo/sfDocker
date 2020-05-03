# Aplicación symfony 4.4 dockerizada. 

Utilizando la imagen oficial de php:7.2 como base, se genera y utiliza una imagen propia con los requisitos mínimos para poder ejecutar la aplicación web.

Aparte también se instala el cliente de symfony para poder instalar las dependencias (symfony composer) desde el contenedor de php, sin la necesidad de instalar nada en el sistema anfitrión.

### Installation

Crear directorio del proyecto y clonar el repositorio.

```sh
$ mkdir sfDocker
$ cd sfDocker
$ git clone https://github.com/gogalo/sfDocker.git .
```

### Docker compose

*IMPORTANTE*: Es necesario tener instalado Docker y Docker Compose. Si no los tienes instalados antes de seguir instálalos en tu sistema. Para ello sigue las instrucciones de la documentación oficial.

1. [Docker](https://docs.docker.com/get-docker/)
2. [Docker compose](https://docs.docker.com/compose/install/)

Una vez instalados, podremos lanzar y parar los contenedores con docker compose.

1. Fichero .env

Variables de entorno para Docker Compose. Cualquier cambio es necesario parar y borrar los contenedores. Dependiendo del cambio puede ser necesario volver a realizar el build al levantar los contenedores.

2. Levantar contenedores. --build *(opcional)* primera vez o cambios en fichero .env y -d *(opcional)* para lanzar en backgroung

```sh
$ docker-compose up [-d] [--build]
```

3. Parar/borrar contenedores

```sh
$ docker-compose down
```

### App Web 

*IMPORTANTE*: antes de abrir la aplicación en el navegador web, es necesario instalar las dependencias del proyecto. Para ello utilizamos el cliente de symfony del contenedor, especificando el directorio en el que está ubicado el código de symfony (/path/a/sfDocker/htdocs)

```sh
$ docker-compose exec php symfony composer install -d ./htdocs
```

Ver la aplicación.

[http://localhost:8000](http://localhost:8000)
