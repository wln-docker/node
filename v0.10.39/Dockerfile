#
# Node.js Dockerfile
#
# https://github.com/xiechaoyi/node
#

# Pull base image.
#FROM ubuntu
FROM debian:jessie
ENV NODE_VERSION 0.10.39
ENV NPM_VERSION 2.11.3

MAINTAINER WlniaoStudio <admin@wlniao.com>

RUN apt-get update && apt-get install -y git \
    && git clone https://github.com/wlniao/node.i-simple.git /src 
    
# verify gpg and sha256: http://nodejs.org/dist/v0.10.31/SHASUMS256.txt.asc
RUN gpg --keyserver pool.sks-keyservers.net --recv-keys 7937DFD2AB06298B2293C3187D33FF9D0246406D 114F43EE0176B71C7BC219DD50A3051F888C628D

RUN buildDeps='curl ca-certificates' \
	&& set -x \
	&& apt-get install -y $buildDeps --no-install-recommends \
	&& rm -rf /var/lib/apt/lists/* \
	&& curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.gz" \
	&& curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc" \
	&& gpg --verify SHASUMS256.txt.asc \
	&& grep " node-v$NODE_VERSION-linux-x64.tar.gz\$" SHASUMS256.txt.asc | sha256sum -c - \
	&& tar -xzf "node-v$NODE_VERSION-linux-x64.tar.gz" -C /usr/local --strip-components=1 \
	&& rm "node-v$NODE_VERSION-linux-x64.tar.gz" SHASUMS256.txt.asc \
	&& apt-get purge -y --auto-remove $buildDeps \
	&& npm install -g npm@"$NPM_VERSION" \
	&& npm install -g nodemon
	
RUN apt-get update && apt-get install -y vim

ENV WLNIAO_HTTP_PORT 80
EXPOSE 80
WORKDIR /src
CMD nodemon app.js

