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

RUN wget https://sourceforge.net/projects/biblatex-biber/files/biblatex-biber/2.17/binaries/Linux/biber-linux_x86_64.tar.gz/download \
    && tar -xzvf download biber \
    && mv biber /bin \
    && rm -rf download
RUN wget https://github.com/tectonic-typesetting/tectonic/releases/download/tectonic%400.12.0/tectonic-0.12.0-x86_64-unknown-linux-musl.tar.gz \
    && tar -xzvf tectonic-0.12.0-x86_64-unknown-linux-musl.tar.gz tectonic \
    && mv tectonic /bin \
    && rm -rf tectonic-0.12.0-x86_64-unknown-linux-musl.tar.gz

RUN wget https://github.com/cmhughes/latexindent.pl/releases/download/V3.19.1/latexindent-linux \
    && chmod +x latexindent-linux \
    && mv latexindent-linux /bin/latexindent
