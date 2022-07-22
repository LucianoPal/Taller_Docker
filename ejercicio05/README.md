## HEALTHCHECK
La instrucción HEALTHCHECK se utiliza para que Docker pueda comprobar que un contenedor sigue funcionando. Esto puede detectar casos como un servidor web que está atascado en un bucle infinito y no puede manejar nuevas conexiones, aunque el proceso del servidor todavía se está ejecutando.
Cuando se utiliza la instrucción HEALTHCHECK el contenedor creado tiene un estado de salud además de su estado normal. Este estado es inicialmente de starting. Cada vez que pasa una verificación de estado, se convierte en healthy. Después de un cierto número de fallas consecutivas, se vuelve unhealthy.
The command’s exit status indicates the health status of the container. The possible values are:
	0: success - the container is healthy and ready for use
	1: unhealthy - the container is not working correctly
	2: reserved - do not use this exit code

## ONBUILD
La instrucción ONBUILD agrega a la imagen trigger que se ejecutará en un momento posterior, cuando la imagen se use como base para otra construcción. El activador se ejecutará en el contexto de la compilación descendente, como si se hubiera insertado inmediatamente después de la instrucción FROM en el Dockerfile descendente.
Esto es útil si está creando una imagen que se utilizará como base para crear otras imágenes, por ejemplo, un entorno de creación de aplicaciones o un demonio que se puede personalizar con una configuración específica del usuario.
La instrucción funciona de la siguiente manera:
	1: Cuando encuentra una instrucción ONBUILD, el constructor agrega un trigger a los metadatos de la imagen que se está construyendo. La instrucción no afecta de otro modo a la compilación actual.
	2: Al final de la compilación, se almacena una lista de todos los triggers en el manifiesto de la imagen, bajo la clave OnBuild. Se pueden inspeccionar con el comando docker inspect.
	3: Posteriormente, la imagen puede usarse como base para una nueva compilación, utilizando la instrucción FROM. Como parte del procesamiento de la instrucción FROM, el constructor descendente busca triggers ONBUILD y los ejecuta en el mismo orden en que se registraron. Si alguno de los activadores falla, la instrucción FROM se aborta, lo que a su vez hace que la compilación falle. Si todos los disparadores tienen éxito, la instrucción FROM se completa y la compilación continúa como de costumbre.
	4: Los triggers se borran de la imagen final después de ejecutarse. En otras palabras, no son heredados por construcciones de "nietos".

## VOLUME
La instrucción VOLUME crea un punto de montaje con el nombre especificado y lo marca como que contiene volúmenes montados externamente desde un host nativo u otros contenedores. El valor puede ser una matriz JSON, VOLUME ["/var/log/"] o una cadena sin formato con varios argumentos, como VOLUME /var/log o VOLUME /var/log /var/db.
El comando docker run inicializa el volumen recién creado con cualquier dato que exista en la ubicación especificada dentro de la imagen base.