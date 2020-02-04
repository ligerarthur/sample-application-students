
# Run
FROM openjdk:11-jre-slim
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME
COPY $MYAPP_HOME/sample-application-http-api-server/target/*.jar $MYAPP_HOME/myapp.jar

EXPOSE 8080

ENTRYPOINT java -jar myapp.jar