# https://hub.docker.com/r/lnhcode/openjdk/tags
FROM ghcr.io/linianhui/openjdk:11.0.13

WORKDIR /app

COPY target/producer-1.jar app.jar

ENV JAVA_OPTIONS='-XX:+UseG1GC -XX:+UseContainerSupport -XX:MaxRAMPercentage=75.00'

ENV JAVA_DEBUG_OPTIONS='-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:5005'

ENTRYPOINT ["/bin/bash", "-c", "java $JAVA_OPTIONS $JAVA_DEBUG_OPTIONS -jar app.jar"]

EXPOSE 80
