#FROM openjdk:8-jdk-alpine
#VOLUME /tmp
#EXPOSE 8765
#ADD target/*.jar app.jar
#ENV JAVA_OPTS=""
#ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]

FROM maven:3.6.0-jdk-8-alpine
WORKDIR /
ADD src /src
ADD pom.xml /
#ADD Dockerfile /
EXPOSE 8765
RUN mvn clean package
RUN cp target/*.jar app.jar
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]