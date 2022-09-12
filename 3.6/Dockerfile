FROM  openjdk:19-jdk-alpine3.16
LABEL maintainer="chris@kairostechnologies.us"
# OpenRefine 3.6.0

ENV OR_URL "https://oss.sonatype.org/service/local/artifact/maven/content?r=releases&g=org.openrefine&a=openrefine&v=3.6.1&c=linux&p=tar.gz"

WORKDIR /app

RUN set -xe \
    && apk add --no-cache bash curl grep tar \
    && curl -sSL ${OR_URL} | tar xz --strip 1

VOLUME /data
WORKDIR /data

EXPOSE 3333

ENTRYPOINT ["/app/refine"]
CMD ["-i", "0.0.0.0", "-d", "/data"]
