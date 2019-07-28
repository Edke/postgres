FROM postgres:9.6.7-alpine

RUN set -x \
  && apk add --update --no-cache ca-certificates openssl

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz

COPY osm /usr/local/bin/osm
COPY postgres-tools.sh /usr/local/bin/postgres-tools.sh

ENTRYPOINT ["postgres-tools.sh"]
