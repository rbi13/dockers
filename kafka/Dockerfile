FROM openjdk:8-jre-alpine

MAINTAINER rbi13

ENV \
  KAFKA_VERSION="0.10.1.0" \
  SCALA_VERSION="2.11"
ENV \
  KAFKA_MIRROR=http://www-eu.apache.org/dist/kafka/${KAFKA_VERSION} \
  KAFKA_PKG="kafka_${SCALA_VERSION}-${KAFKA_VERSION}" \
  KAFKA_HOME="/opt/kafka_${SCALA_VERSION}-${KAFKA_VERSION}"

# add bash (kafka scripts seem sh incompatible)
  RUN apk upgrade --update &&\
    apk add --update bash

# download kafka
ADD "${KAFKA_MIRROR}/${KAFKA_PKG}.tgz /

# install kakfa
RUN \
  tar xfz ${KAFKA_PKG}.tgz &&\
  mkdir /opt && mv ${KAFKA_PKG} /opt/ &&\
  rm "${KAFKA_PKG}.tgz"

# exec
WORKDIR $KAFKA_HOME
#CMD [""]
