FROM node:lts-stretch-slim
MAINTAINER Yadwinder Paul Singh <yadwinderpaul@gmail.com>

# due to debian bug, postgresql-client fails
RUN mkdir -p /usr/share/man/man1 && mkdir -p /usr/share/man/man7

RUN apt-get update && \
  apt-get install -y --no-install-recommends \
    curl ca-certificates build-essential postgresql-client \
    postgresql-autodoc git graphviz && \
  rm -rf /var/lib/apt/lists/*

# install cpanm and pg_prove
RUN curl -LO http://xrl.us/cpanm \
  && chmod +x cpanm \
  && ./cpanm TAP::Parser::SourceHandler::pgTAP
