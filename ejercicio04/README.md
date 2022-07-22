## Se crea la imagen de Docker
	docker build -t passwordapi .

## Se corre la imagen previamente creada
	docker run -p 8080:8080 passwordapi

## Se etiqueta la imagen
	docker tag passwordapi lucianopalmieri/passwordapi:1

## Se publica la imagen en Docker Hub
	docker push lucianopalmieri/passwordapi:1

## Link Docker Hub
https://hub.docker.com/layers/258030656/lucianopalmieri/passwordapi/1/images/sha256-ebaaa96783f1cbb374ae989d61f2f95aa40cf3b7b1e73b3fd1ac2bc73073238e?context=repo