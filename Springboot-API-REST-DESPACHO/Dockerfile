FROM maven:3.8.8-eclipse-temurin-17-alpine AS builder

WORKDIR /app

COPY pom.xml .

RUN mnv dependency:go-offline -B || ./mvnw dependency:go-offline -B || true

COPY src ./src

RUN mvn clean package -DskipTests || ./mvnw clean package -DskipTests

FROM eclipse-temurin:17-jre-alpine

WORKDIR /app

RUN addgroup -S api-group && adduser -S api-user -G api-group

COPY --from=builder /app/target/*.jar app.jar

RUN chown -R api-user:api-group /app

USER api-user


EXPOSE 8082

ENTRYPOINT ["java", "-jar", "app.jar"]