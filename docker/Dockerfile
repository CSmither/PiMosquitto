FROM raspbian/stretch:041518

LABEL author="Smither - callum [at] smither [dot] org"

RUN apt-get clean && apt-get update && apt-get dist-upgrade -y

RUN apt-get install -y \
    vim \
    libc-ares-dev \
    uuid-dev \
    libwebsockets-dev \
    libssl-dev

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN wget http://repo.mosquitto.org/debian/pool/main/m/mosquitto/mosquitto_1.5.8.orig.tar.gz

RUN tar -xvf mosquitto_1.5.8.orig.tar.gz

RUN cd mosquitto-1.5.8

RUN ./configure && make

RUN make install



ADD entrypoint.sh /entrypoint.sh

ENTRYPOINT ["/entrypoint.sh"]