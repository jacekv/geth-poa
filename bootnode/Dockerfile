FROM --platform=linux/amd64 ubuntu:focal

RUN apt-get update \
     && apt-get install -y wget \
     && rm -rf /var/lib/apt/lists/* 

WORKDIR "/opt"
ARG BINARY="geth-alltools-linux-amd64-1.13.5-916d6a44.tar.gz"
RUN wget "https://gethstore.blob.core.windows.net/builds/$BINARY"
RUN tar -xzvf $BINARY --strip 1
RUN rm $BINARY

ENV nodekeyhex=""
CMD exec ./bootnode -nodekeyhex $nodekeyhex -addr $bootnodeIp:30301

EXPOSE 30301/udp
EXPOSE 30303/udp
