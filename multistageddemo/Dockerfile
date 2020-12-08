FROM maven:3-openjdk-8 As packaging
RUN git clone https://github.com/openmrs/openmrs-core.git
RUN cd /openmrs-core/ && mvn package

FROM openjdk:8u272-slim
COPY --from=packaging /openmrs-core/liquibase/target/openmrs-liquibase-2.5.0-SNAPSHOT-tests.jar /openmrs.jar
EXPOSE 8080
CMD ["java", "-jar", "/openmrs.jar"] 
