FROM surrealdb/surrealdb:latest
LABEL author="Stefanuk12" maintainer="stefanukpadd@gmail.com"

## Setup the container
USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
RUN chown -R /entrypoint.sh
RUN chmod +x /entrypoint.sh

## Starting the container
ENTRYPOINT []
CMD	["/bin/bash", "/entrypoint.sh"]