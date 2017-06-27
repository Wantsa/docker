FROM ruby:2.3

ENV TERM=xterm PATH=/app/bin:$PATH DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y xmlsec1 \
 && curl -sL https://deb.nodesource.com/setup_6.x | bash - \
 && apt-get install -y nodejs \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
 && useradd --create-home --user-group --uid 1000 --shell `which bash` user

USER user
WORKDIR /app
