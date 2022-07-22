FROM amazoncorretto:8 as java

COPY ./passwordapi/passwordapi.jar /tmp/passwordapi.jar

CMD ["java", "-jar", "/tmp/passwordapi.jar"]

EXPOSE 8080