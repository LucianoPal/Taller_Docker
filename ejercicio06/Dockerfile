FROM registry.access.redhat.com/redhat-openjdk-18/openjdk18-openshift as java

COPY ./passwordapi/passwordapi.jar /tmp/passwordapi.jar

CMD ["java", "-jar", "/tmp/passwordapi.jar"]

EXPOSE 8080