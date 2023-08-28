FROM azul/prime-debian:8

LABEL author="eugeniodevv"

RUN apt update -y \
	&& apt install -y \
		curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6 \
		libargon2-0-dev

RUN useradd -m -d /home/container -s /bin/bash container
USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./../entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]