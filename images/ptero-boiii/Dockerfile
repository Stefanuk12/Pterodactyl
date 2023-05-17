FROM ghcr.io/stefanuk12/ptero-debian-wine:dev

# Installing IW4M Admin Dependencies
USER root
RUN wget https://packages.microsoft.com/config/debian/11/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
RUN dpkg -i packages-microsoft-prod.deb
RUN rm packages-microsoft-prod.deb
RUN apt-get update; \
    apt-get install -y apt-transport-https && \
    apt-get update && \
    apt-get install -y dotnet-sdk-3.1 aspnetcore-runtime-3.1

# Installing other dependencies
RUN apt-get install unzip

# Setting up container user
USER container
ENV DOTNET_CLI_TELEMETRY_OPTOUT=1
WORKDIR	/home/container

# Installing steamcmd
RUN curl -sqL "https://steamcdn-a.akamaihd.net/client/installer/steamcmd_linux.tar.gz" | tar zxvf -

# Copy over entrypoint
COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]