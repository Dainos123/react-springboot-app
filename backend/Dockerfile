FROM 3.8.6-eclipse-temurin-8-alpine AS build

WORKDIR /app 

COPY . .

RUN mvn -f /app/pom.xml clean package -DskipTest=true

FROM openjdk:16-alpine3.13

WORKDIR: /jp

COPY --from=build /app/target/studentsystem-0.0.1-SNAPSHOT.jar /jp/java.jar

EXPOSE: 8080

CMD ["java","-jar","/jp/java.jar"]
