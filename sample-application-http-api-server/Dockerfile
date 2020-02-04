


# Run
FROM openjdk:11-jre-slim

COPY target/*-exec.jar /opt/myapp/myapp.jar

RUN ls -l

RUN ls -l  /opt/myapp/

EXPOSE 8080

ENTRYPOINT java -jar myapp.jar