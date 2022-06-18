FROM maven:3.8.6-eclipse-temurin-17-alpine AS build

WORKDIR /build

COPY . .

RUN mvn clean package -DskipTests=true 



FROM openjdk:16-alpine3.13

WORKDIR /jvm

COPY --from=build /build/target/studentsystem-0.0.1-SNAPSHOT.jar /jvm/java.jar

EXPOSE 8080

CMD ["java","-jar","/jvm/java.jar"]

