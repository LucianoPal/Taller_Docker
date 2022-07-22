## Se crea la imagen de Docker
	docker build -t passwordapi .

## Se corre la imagen previamente creada
	docker run -p 8080:8080 passwordapi

## Se etiqueta la imagen
	docker tag passwordapi lucianopalmieri/passwordapi:2

## Se publica la imagen en Docker Hub
	docker push lucianopalmieri/passwordapi:2

## Link Docker Hub
https://hub.docker.com/layers/258123452/lucianopalmieri/passwordapi/2/images/sha256-90832fcc137140899417f0a553306dc3deed064faa65a199b1655d8f42e1a28f?context=repo