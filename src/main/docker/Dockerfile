FROM openjdk:8-jre-alpine

ENV SPRING_OUTPUT_ANSI_ENABLED=ALWAYS \
    JHIPSTER_SLEEP=0 \
    JAVA_OPTS=""

# Add a jhipster user to run our application so that it doesn't need to run as root
RUN adduser -D -s /bin/sh alpha
WORKDIR /home/alpha

ADD entrypoint.sh entrypoint.sh
RUN chmod 755 entrypoint.sh && chown alpha:alpha entrypoint.sh
USER alpha

ADD *.jar app.jar

ENTRYPOINT ["./entrypoint.sh"]


EXPOSE 8080

