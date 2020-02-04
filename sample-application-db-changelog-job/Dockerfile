  
# Build
FROM maven:3.6.3-jdk-11-slim AS myapp-build2
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME

COPY sample-application-db-changelog-job ./sample-application-db-changelog-job
COPY pom.xml ./pom.xml


RUN mvn clean verify

# Run
FROM openjdk:11-jre-slim
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME
COPY --from=myapp-build2 $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar

EXPOSE 8080

ENTRYPOINT java -jar myapp.jar