FROM openjdk:11.0.7-jre-slim-buster

COPY java-webserver.jar ./

RUN touch one

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "java-webserver.jar" ]
