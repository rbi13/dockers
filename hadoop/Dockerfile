FROM openjdk:7-jre-alpine

MAINTAINER rbi13

ENV \
  HADOOP_VERSION="2.7.3" \
  HADOOP_MIRROR=http://www-eu.apache.org/dist/hadoop/common/stable/
ENV \
  HADOOP_PKG="hadoop-${HADOOP_VERSION}" \
  HADOOP_HOME="/opt/hadoop-${HADOOP_VERSION}"

# add bash (hadoop scripts seem sh incompatible)
RUN apk upgrade --update &&\
  apk add --update bash openssh rsync 

# download hadoop
ADD "${HADOOP_MIRROR}/${HADOOP_PKG}.tar.gz /

# install hadoop
RUN \
  tar xfz ${HADOOP_PKG}.tar.gz &&\
  mkdir /opt && mv ${HADOOP_PKG} /opt/ &&\
  rm "${HADOOP_PKG}.tar.gz"

# exec
WORKDIR $HADOOP_HOME
#CMD [""]
