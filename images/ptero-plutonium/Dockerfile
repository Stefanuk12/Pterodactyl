FROM ghcr.io/stefanuk12/ptero-debian-wine:dev

# Installing IW4M Admin Dependencies
RUN if [ ${IW4MA_ENABLED} ];\
    then\
    apt update && apt install -y wget apt-transport-https dotnet-sdk-6.0 dotnet-runtime-6.0 curl unzip zip\
    wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb\
    dpkg -i packages-microsoft-prod.deb\
    dotnet --version;\
    fi

#
ENV DOTNET_CLI_TELEMETRY_OPTOUT=1

USER container
WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]