# Ejercicio 2

Crea 2 contenedores por medio del cliente `CLI` de `docker`:

- El **1er contenedor** ejecutará un servidor de [`MongoDB`](https://hub.docker.com/_/mongo) y su nombre deberá de ser `m1`
- El **2do contenedor** ejecutará un cliente de [`Mongo Express`](https://hub.docker.com/_/mongo-express) el cual se llame `mexpress` y que se conectará al contenedor `m1` creado en el punto anterior. Otro requisito más es que este cliente tiene que estar protegido por medio de las siguientes credenciales:
  - Usuario: `DAS`
  - Password: `extra123`

Anexa los comandos utilizados en el proceso

# SOLUCIÓN

**Respuesta**
- Se crea una network con el comando:
`docker network create examen`

- 1er contenedor, comando:
`docker run -d -p 27017:27017 --net=examen --name m1 mongo`

- 2do contenedor
`docker run --name mexpress -d -p 8081:8081 --net=examen -e ME_CONFIG_MONGODB_SERVER=m1 -e ME_CONFIG_BASICAUTH_USERNAME=DAS -e ME_CONFIG_BASICAUTH_PASSWORD=extra123 mongo-express`