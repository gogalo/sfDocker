### Installation

Crear directorio del proyecto y clonar el repositorio.

```sh
$ mkdir sfDocker
$ cd sfDocker
$ git clone https://github.com/gogalo/sfDocker.git .
```

### Docker compose

Es necesario tener instalado Docker y Docker Compose. 
Si no los tienes instalado antes de seguir instalalos en tu sistema, para ello sigue las instrucciones en:

1. [Docker](https://docs.docker.com/get-docker/)
2. [Docker compose](https://docs.docker.com/compose/install/)

Una vez instalados, lanzar contenedores con docker compose.

```sh
$ docker-compose up -d
```

### Symfony

Instalar las dependecias utilizando el cliente de symfony del contenedor y especificando el directorio donde está el fichero composer.json, en este caso en el directorio htdocs del proyecto (/path/a/sfDocker/htdocs)

```sh
$ docker-compose exec php symfony composer install -d ./htdocs
```

Abrir la aplicación en el navegador

[http://localhost:8000](http://localhost:8000)