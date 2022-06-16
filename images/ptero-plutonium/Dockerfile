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

# Installing other node
RUN curl -fsSL https://deb.nodesource.com/setup_current.x | bash -
RUN apt-get install -y nodejs
RUN mkdir "/home/container/.npm-packages"
RUN npm config set prefix "/home/container/.npm-packages"

#
USER container
ENV DOTNET_CLI_TELEMETRY_OPTOUT=1
ENV PATH="$PATH:/home/container/.npm-packages/bin"

WORKDIR	/home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD	["/bin/bash", "/entrypoint.sh"]