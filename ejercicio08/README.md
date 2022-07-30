## Inicio

Para iniciar los contenedores para este ejercicio es necesario correr el siguiente comando
	docker-compose up

## Pruebas

Para realizar las pruebas se realizaron varias veces la siguiente consulta vía navegador:
	http://localhost:3000/health

Al realizarlas pudimos observar las siguientes respuestas

Respuesta 1:

	{"host":"ba66e32d9a4c","loadavg":[0.109375,0.2255859375,0.16748046875],"freemem":9908129792,"appversion":"1.0.0"}

Respuesta 2:

	{"host":"58279ffe060f","loadavg":[0.109375,0.2255859375,0.16748046875],"freemem":9909436416,"appversion":"1.0.0"}

Podemos observar como cambian los hosts en las diferentes respuestas funcionando correctamente el balanceador