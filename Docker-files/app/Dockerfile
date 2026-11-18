FROM maven:3.10.0-eclipse-temurin-17 AS build
WORKDIR /app
COPY . .
RUN mvn install


FROM eclipse-temurin:21-jre AS run
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar
CMD ["java", "-jar", "app.jar"]