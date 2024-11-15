FROM openjdk:19-jdk-alpine
RUN apk update
RUN apk add maven
WORKDIR /src/
COPY java_applic/ .
RUN mvn clean package


FROM tomcat:9.0.97-jre8-temurin-jammy
COPY --from=0 /src/target/*.war /usr/local/tomcat/webapps/
EXPOSE 8080
CMD ["catalina.sh" , "run"]


