FROM openjdk:11-jre-slim-buster
WORKDIR /myapp

COPY /target/*.jar /myapp/api-cursos.jar
COPY opentelemetry/opentelemetry-javaagent.jar /myapp/opentelemetry-javaagent.jar

RUN rm -f /etc/localtime && \
    ln -s /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

CMD ["java","-Duser.timezone=UTC-3", "-javaagent:opentelemetry-javaagent.jar","-jar","api-cursos.jar"]
