FROM registry.redhat.io/redhat-openjdk-18/openjdk18-openshift
COPY passwordapi.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
