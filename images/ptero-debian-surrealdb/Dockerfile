FROM surrealdb/surrealdb:latest
LABEL author="Stefanuk12" maintainer="stefanukpadd@gmail.com"

## Setup the container
USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
ENTRYPOINT [ "/bin/bash", "/entrypoint.sh" ]