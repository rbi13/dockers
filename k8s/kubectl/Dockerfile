FROM alpine:3.4

MAINTAINER rbi13

ENV version=v1.4.6

ADD https://storage.googleapis.com/kubernetes-release/release/${version}/bin/linux/amd64/kubectl /usr/local/bin/kubectl

RUN \
    apk add --no-cache curl ca-certificates && \
    chmod +x /usr/local/bin/kubectl

CMD ["kubectl"]