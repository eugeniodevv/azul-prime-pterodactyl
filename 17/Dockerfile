FROM azul/prime-debian:17

LABEL author="eugeniodevv"

RUN apt update -y \
	&& apt install -y \
		curl lsof ca-certificates openssl git tar sqlite3 fontconfig tzdata iproute2 libfreetype6

RUN useradd -m -d /home/container -s /bin/bash container
USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./../entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]