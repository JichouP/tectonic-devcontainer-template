FROM ubuntu:latest

LABEL maintainer="JichouP"
LABEL version="0.1.0"
LABEL description="Docker Image for using texlive"

WORKDIR /workdir

RUN apt update && apt upgrade -y
RUN apt install -y \
    git \
    curl \
    wget

ENV TECTONIC_VERSION=0.12.0
ENV BIBER_VERSION=2.17
ENV LATEXINDENT_VERSION=3.19.1

RUN wget https://github.com/tectonic-typesetting/tectonic/releases/download/tectonic%40${TECTONIC_VERSION}/tectonic-${TECTONIC_VERSION}-x86_64-unknown-linux-musl.tar.gz \
    && tar -xzvf tectonic-${TECTONIC_VERSION}-x86_64-unknown-linux-musl.tar.gz tectonic \
    && mv tectonic /bin \
    && rm -rf tectonic-${TECTONIC_VERSION}-x86_64-unknown-linux-musl.tar.gz

RUN wget https://sourceforge.net/projects/biblatex-biber/files/biblatex-biber/${BIBER_VERSION}/binaries/Linux/biber-linux_x86_64.tar.gz/download \
    && tar -xzvf download biber \
    && mv biber /bin \
    && rm -rf download

RUN wget https://github.com/cmhughes/latexindent.pl/releases/download/V${LATEXINDENT_VERSION}/latexindent-linux \
    && chmod +x latexindent-linux \
    && mv latexindent-linux /bin/latexindent
