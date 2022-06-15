FROM ghcr.io/stefanuk12/ptero-debian-wine:dev

# Installing IW4M Admin Dependencies
USER root
RUN wget https://packages.microsoft.com/config/debian/11/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN dpkg -i packages-microsoft-prod.deb
RUN rm packages-microsoft-prod.deb

#
ENV DOTNET_CLI_TELEMETRY_OPTOUT=1

USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]