#METODOLOGIA DO PAULO - INSTALA MAVEN E RODA MAVEN CLEAN PACKAGE
#   GERA PASTA 'TARGET' 'POR DENTRO DO CONTAINER'
FROM maven:3.6.0-jdk-8-alpine
WORKDIR /
ADD src /src
ADD pom.xml /
#ADD Dockerfile /
EXPOSE 8000
RUN mvn clean package
RUN cp target/*.jar app.jar
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]

#METODOLOGIA DO CURSO - NAO INSTALA MAVEN E NAO RODA MAVEN CLEAN PACKAGE
#   GERA PASTA 'TARGET' 'POR FORA'
#   E A COPIA PRA DENTRO DO CONTAINER
#FROM openjdk:8-jdk-alpine
#VOLUME /tmp
#EXPOSE 8000
#ADD target/*.jar app.jar
#ENV JAVA_OPTS=""
#ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]