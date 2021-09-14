FROM openjdk:11.0.7-jre-slim-buster

COPY java-webserver.jar ./

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "java-webserver.jar" ]