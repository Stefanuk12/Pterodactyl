FROM ptero-debian-wine

USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]