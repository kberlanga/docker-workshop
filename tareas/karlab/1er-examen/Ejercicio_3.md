# Ejercicio 3

Crea un volumen que se llame `mongo_volume` y que utilice el driver por default para los `Docker` volumes.

Ejecuta un contenedor de [`MongoDB`](https://hub.docker.com/_/mongo) que se llame `mongo` y que monte el volumen creado en el paso anterior, y una vez que todo este listo ejecuta los siguientes pasos:


- Corre el script [`populate.py`](ejercicio-3/populate.py)
- Luego corre el otro script [`find.py`](ejercicio-3/find.py), deberías de obtener una salida como la siguiente:

``` shell
##### RECORDS #####
{'_id': ObjectId('5fbf475bece16a8442cfe774'), 'first_name': 'foo', 'last_name': 'bar', 'email': 'foo@mail.com'}
{'_id': ObjectId('5fbf475bece16a8442cfe775'), 'first_name': 'foo', 'last_name': 'baz', 'email': 'baz@mail.com'}
{'_id': ObjectId('5fbf475bece16a8442cfe776'), 'first_name': 'bar', 'last_name': 'baz', 'email': 'bar@mail.com'}
{'_id': ObjectId('5fbf475bece16a8442cfe777'), 'first_name': 'fulano', 'last_name': 'mengano', 'email': 'fulano@mail.com'}
{'_id': ObjectId('5fbf475bece16a8442cfe778'), 'first_name': 'zultano', 'last_name': 'perengano', 'email': 'zultano@mail.com'}
```

Ahora detén y borra el contenedor de `mongo`, y levanta un nuevo contenedor que también ejecute un servidor de `MongoDB` y que utilice el mismo volumen de `mongo_volume` previamente creado, pero que en esta ocasión se llame `mongo2`.

Vuelve a ejecutar el script de [`find.py`](ejercicio-3/find.py) y contesta a la siguiente pregunta: ¿Cuál fue nuestra salida en esta ocasión?

# SOLUCIÓN
- 1er contenedor:
`docker run -d -p 27017:27017 --name mongo -v mongo_volume:/data/db mongo`

- 2do contenedor:
`docker run -d -p 27017:27017 --name mongo2 -v mongo_volume:/data/db mongo`

**Respuesta**
La salida es la misma que cuando ejecutamos por primera el contenedor con el nombre `mongo`, esto se debe a que los volumenes hacen que los datos permanezcan, para este caso, cuando se crea el primer contenedor con el volumen `mongo_volume` y ejecutó el [archivo](/populate.py) se creo la base de datos y se insertaron registros, cuando se creó el segundo contenedor en base al mismo volumen, la base vive en el mismo volumen, por lo tanto los registros se mantienen. Adjunto [evidencia](./captura_ejercicio3.png)