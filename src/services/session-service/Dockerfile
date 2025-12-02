FROM eclipse-temurin:11-jdk-alpine

WORKDIR /app

RUN apk add --no-cache maven

COPY pom.xml .
COPY src src

RUN mvn clean package -DskipTests

EXPOSE 8081

CMD ["java", "-jar", "target/session-service-0.0.1-SNAPSHOT.jar"]