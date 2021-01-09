## Ejercicio 3

Crea 2 contenedores por medio del cliente `CLI` de `docker`:

- El **1er contenedor** ejecutará un servidor de [`Redis`](https://hub.docker.com/_/redis) y su nombre deberá de ser `redis`

- Comando docker run -d -p 6379:6379 --net=t4_3 --name redis kberlanga/redis --protected-mode no

- El **2do contenedor** deberá de ejecutar un servidor de [`Redis Commander`](https://hub.docker.com/r/rediscommander/redis-commander) el cual tiene que estar protegido con usuario y contraseña para poder acceder a él. El contenedor debe de llamarse `commander`

- Comando docker run -d -p 8081:8081 --net=t4_3 --name commander rediscommander/redis-commander --env HTTP_USER=admin HTTP_PASSWORD=karlitabb

- Comando docker run -d -p 8081:8081 --name commander rediscommander/redis-commander -e COMMANDER_USER=admin COMMANDER_USER_PWD=karlitabb

docker run -d -p 8081:8081 --net=t4_3 --name commander rediscommander/redis-commander

Asegúrate de probar que todo funciona correctamente y que el servidor de `redis-commander` puede contectarse al de `redis` sin problema alguno visitando la URL correcta. Utiliza `docker networks` para llevar a cabo este proceso.

Anexa los comandos utilizados para llevar a cabo este ejercicio, así como screenshots de evidencia de que llevaste este ejercicio a cabo en tu equipo.