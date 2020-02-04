FROM maven:3.6.3-jdk-11-slim AS myapp-build
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME


COPY sample-application-http-api-server/pom.xml ./sample-application-http-api-server/pom.xml
COPY pom.xml ./pom.xml
COPY sample-application-http-api-server/src ./src


RUN mvn clean verify

# Run
FROM openjdk:11-jre-slim
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME
COPY --from=myapp-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar

EXPOSE 8080

ENTRYPOINT java -jar myapp.jar