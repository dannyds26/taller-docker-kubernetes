
# Ejercicio 7

JobVacancy docker-compose


## Authors

- [@dannyds26](https://www.github.com/dannyds26)


## ¿Cuántos contenedores se están ejecutando? (pueden verlo en el archivo docker-compose.yml y también ejecutando docker ps)
Se ejecutan 2 contenedores, unos con la aplicación web y otro con la base de datos:

CONTAINER ID   IMAGE                            COMMAND                  CREATED         STATUS         PORTS                                       NAMES
ca1a5e680645   nicopaez/jobvacancy-ruby:1.3.0   "/jobvacancy/start_a…"   5 minutes ago   Up 3 minutes   0.0.0.0:3000->3000/tcp, :::3000->3000/tcp   ejercicio07-web-1
9d40ea119906   postgres:14.4-alpine             "docker-entrypoint.s…"   5 minutes ago   Up 3 minutes   5432/tcp                                    ejercicio07-db-1

## ¿Cuales son las imágenes en las que están basados los mencionados contenedores?
Las imágenes son las siguientes:

* nicopaez/jobvacancy-ruby:1.3.0
* postgres:14.4-alpine

## ¿Puedes leer el docker-compose.yml y describir lo que hace cada una de sus lineas?
* version: '2' -> Versión del compose
* services: -> Lista de servicios que se van a levantar con el compose
*   web: -> Nombre del servicio web
*     image: nicopaez/jobvacancy-ruby:1.3.0 -> imágen a utilizar
*     links: -> Lista los servicios que deben comunicarse en la misma red. Esta campo esta deprecado en favor de usar `networks`
*       - db -> el servicio al cual necesita tener un enlace en común
*     ports: -> los puertos que expone el contenedor
*       - "3000:3000" ': se asigna puerto 3000 del host con el puerto 3000 del contenedor
*     environment: -> lista de variables de entorno a inicializar en el contenedor
*       PORT: "3000" -> variable de entorno PORT
*       RACK_ENV: "production" -> variable de entorno RACK_ENV
*       DATABASE_URL: "postgres://postgres:Passw0rd!@db:5432/postgres" -> variable de entorno DATABASE_URL
*     depends_on: -> los servicios de los que depende este servicio.
*       - db
*   db: -> nombre del servicio db
*     image: postgres:14.4-alpine -> imágen a utilizar
*     environment: -> lista de variables de entorno a inicializar en el contenedor
*       POSTGRES_PASSWORD: Passw0rd! -> variable de entorno POSTGRES_PASSWORD

## Dado que cada contenedor corre en forma aislada ¿Cómo es posible que esos contenedores se vean entre sí?

Docker compose genera por defecto una red común y cada servicio al ser levantado se une a esa red por defecto. El nombre del servicio definido en el descriptor se convierte en un hostname que puede ser usado en cada contenedor para hacer referencia a nivel de red a otro contenedor.