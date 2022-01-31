# syntax=docker/dockerfile:1

FROM openjdk:16-alpine

WORKDIR /app
COPY app/*.jar app.jar

ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","app.jar"]
