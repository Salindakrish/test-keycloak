# FROM quay.io/keycloak/keycloak:latest as builder

# ENV KC_HEALTH_ENABLED=true
# ENV KC_METRICS_ENABLED=true
# ENV KC_FEATURES=token-exchange
# ENV KC_DB=postgres
# # Install custom providers
# # RUN curl -sL https://github.com/aerogear/keycloak-metrics-spi/releases/download/2.5.3/keycloak-metrics-spi-2.5.3.jar -o /opt/keycloak/providers/keycloak-metrics-spi-2.5.3.jar
# RUN /opt/keycloak/bin/kc.sh build

# FROM quay.io/keycloak/keycloak:latest
# COPY --from=builder /opt/keycloak/ /opt/keycloak/
# WORKDIR /opt/keycloak
# # for demonstration purposes only, please make sure to use proper certificates in production instead
# RUN keytool -genkeypair -storepass password -storetype PKCS12 -keyalg RSA -keysize 2048 -dname "CN=server" -alias server -ext "SAN:c=DNS:localhost,IP:127.0.0.1" -keystore conf/server.keystore
# # change these values to point to a running postgres instance
# # ENV KC_DB_URL=<DBURL>
# # ENV KC_DB_USERNAME=<DBUSERNAME>
# # ENV KC_DB_PASSWORD=<DBPASSWORD>
# RUN 
# ENV KC_HOSTNAME=localhost
# RUN echo KC_HOSTNAME
# ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
# CMD [ "start-dev", "--auto-build","--db=postgres" ] 


# # FROM registry.access.redhat.com/ubi8-minimal

# # ENV KEYCLOAK_VERSION 18.0.2
# # ENV JDBC_POSTGRES_VERSION 42.3.3
# # ENV JDBC_MYSQL_VERSION 8.0.22
# # ENV JDBC_MARIADB_VERSION 2.5.4
# # ENV JDBC_MSSQL_VERSION 10.2.1.jre11

# # ENV LAUNCH_JBOSS_IN_BACKGROUND 1
# # ENV PROXY_ADDRESS_FORWARDING false
# # ENV JBOSS_HOME /opt/jboss/keycloak
# # ENV LANG en_US.UTF-8

# # ARG GIT_REPO
# # ARG GIT_BRANCH
# # ARG KEYCLOAK_DIST=https://github.com/keycloak/keycloak/releases/download/19.0.1/keycloak-19.0.1.tar.gz

# # USER root

# # RUN microdnf update -y && microdnf install -y glibc-langpack-en gzip hostname java-11-openjdk-headless openssl tar which && microdnf clean all

# # ADD tools /opt/jboss/tools
# # RUN /opt/jboss/tools/build-keycloak.sh

# USER 1000

# EXPOSE 8080
# EXPOSE 8443

# # ENTRYPOINT [ "/opt/jboss/tools/docker-entrypoint.sh" ]

# # CMD ["-b", "0.0.0.0"]

FROM quay.io/keycloak/keycloak:latest as builder
ENV KC_HOSTNAME localhost
RUN echo KC_HOSTNAME