FROM ghcr.io/stefanuk12/ptero-debian-wine:dev

USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]