FROM maven:4.0.0-rc-5-eclipse-temurin-17-noble AS build
WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn clean package -DskipTests

FROM eclipse-temurin:25.0.1_8-jre-noble
WORKDIR /app
COPY --from=build /app/target/pedidos-0.0.1-SNAPSHOT.jar .
CMD [ "java", "-jar","pedidos-0.0.1-SNAPSHOT.jar" ]
