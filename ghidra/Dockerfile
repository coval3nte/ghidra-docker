FROM alpine:latest
ENV USERS="admin"
ARG VERSION="10.3"
ENV VERSION=${VERSION}

ARG DATE="20230510"
ENV DATE=${DATE}

RUN apk add --no-cache -q \
        java-jdk \
        ca-certificates \
        unzip \
        wget \
        bash

RUN wget -O /ghidra.zip "https://github.com/NationalSecurityAgency\
/ghidra/releases/download/\
Ghidra_${VERSION}_build/\
ghidra_${VERSION}_PUBLIC_${DATE}.zip" && \
    unzip /ghidra.zip && \
    rm /ghidra.zip

RUN apk del --no-cache -q \
        unzip \
        wget

COPY ./init /init
RUN chmod +x /init

WORKDIR /ghidra_${VERSION}_PUBLIC/
VOLUME ["/repositories"]
ENTRYPOINT ["/init"]