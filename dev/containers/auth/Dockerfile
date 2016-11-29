FROM hope/nodejs:6

MAINTAINER Sergey Sadovoi <sergey@hope.ua>

ENV \
    APP_VERSION 0.2.1

WORKDIR /data/app

RUN \
    apk add --no-cache --virtual=build-dependencies git python make g++ && \
    git clone --depth 1 https://github.com/HopeUA/auth.rest.git . && \
    npm install && \
    apk del build-dependencies

COPY rootfs/config.local.json /data/app/server/config.local.json
COPY rootfs/datasources.local.json /data/app/server/datasources.local.json

EXPOSE 3000

ENTRYPOINT ["npm"]
CMD ["start"]