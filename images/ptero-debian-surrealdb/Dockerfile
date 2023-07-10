FROM ghcr.io/parkervcp/yolks:alpine
LABEL author="Stefanuk12" maintainer="stefanukpadd@gmail.com"

## Install dependencies
USER root
RUN apk update \
    && apk upgrade \
    && apt add curl

## Installing SurrealDB
RUN curl -sSf https://install.surrealdb.com | sh

## Finishing up
USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]