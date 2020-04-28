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

1. Levantar contenedores

```sh
$ docker-compose up -d
```

2. Parar/borrar contenedores

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
