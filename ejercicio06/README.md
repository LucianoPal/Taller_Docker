## Se crea la imagen de Docker
	docker build -t passwordapi .

## Se corre la imagen previamente creada
	docker run -p 8080:8080 passwordapi

## Se etiqueta la imagen
	docker tag passwordapi lucianopalmieri/passwordapi:2

## Se publica la imagen en Docker Hub
	docker push lucianopalmieri/passwordapi:2