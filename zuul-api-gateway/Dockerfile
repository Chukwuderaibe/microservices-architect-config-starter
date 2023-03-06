FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk:11.0.10-jre
WORKDIR /app
COPY --from=buld /app/target/zuul-0.0.1-snapshot.jar /app
EXPOSE 9999
CMD ["java","-jar","zuul-0.0.1-snapshot.jar"]