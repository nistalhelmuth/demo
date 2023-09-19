ARG     TAG_VERSION
FROM    nginx:1.19.1-alpine as certs
WORKDIR /certs
RUN     apk update && apk add --no-cache openssl
RUN     openssl req -newkey rsa:2048 -sha256 -nodes -x509 -days 3650 -subj "/CN=rewardsweb.com" -addext "subjectAltName=DNS:localhost,IP:127.0.0.1" -keyout private.key -out certificate.crt
FROM    registry.access.redhat.com/ubi8/openjdk-17:${TAG_VERSION}
ENV     LANGUAGE='en_US:en'
COPY    --from=certs --chown=185 certs/ /opt/ssl/
EXPOSE  8443

ENV     JAVA_OPTS="-Dquarkus.http.host=0.0.0.0 -Djava.util.logging.manager=org.jboss.logmanager.LogManager -Dquarkus.http.ssl.certificate.files=/opt/ssl/certificate.crt -Dquarkus.http.ssl.certificate.key-files=/opt/ssl/private.key"
ENV     JAVA_APP_JAR="/deployments/quarkus-run.jar"
USER    185