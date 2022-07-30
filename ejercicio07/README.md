## ¿Cuántos contenedores se están ejecutando? (pueden verlo en el archivo docker-compose-jobvacancy.yml y también ejecutando docker ps)

Se puede observar que se están ejecutando dos contenedores

## ¿Cuales son las imágenes en las que están basados los mencionados contenedores?

Las imágenes en las que están basados los mencionados contenedores son:

	nicopaez/jobvacancy-ruby:1.3.0
	postgres:14.4-alpine

## ¿Puedes leer el docker-compose-jobvacancy.yml y describir lo que hace cada una de sus lineas?

* linea 1 se puede observar la version de docker-compose que se utiliza
* lineas 3 y 15 se puede observar cual será el nombre del contenedor
* lineas 4 y 16 se puede observar la imagen que se utilzará para dicho contenedor
* lineas 5 y 6 se definen los alias adicionales mediante los cuales se puede acceder a un servicio desde otro servicio
* lineas 7 y 8 se puede observar los puertos que se exponen haciendo accesible al servicio tanto de manera interna como externa
* lineas entre 9 y 12 y lineas 17 y 18 se pueden observar las variables de entorno que se definen
* lineas 13 y 14 se definen las dependencias con el resto de los servicios

## Dado que cada contenedor corre en forma aislada ¿Cómo es posible que esos contenedores se vean entre sí?

Esto se debe que al utilizar docker-compose se crea una nueva red definida donde se conectan los diferentes contenedores