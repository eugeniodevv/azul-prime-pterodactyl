FROM azul/prime-debian:8

LABEL author="eugeniodevv"

LABEL org.opencontainers.image.source="https://github.com/eugeniodevv/azul-prime-pterodactyl"
LABEL org.opencontainers.image.licenses=WTFPL

RUN apt update -y \
	&& apt install -y \
		curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 libstdc++6 libargon2-dev

RUN useradd -d /home/container -m container

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./../entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]