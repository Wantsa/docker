FROM ruby:2.3

ENV TERM=xterm PATH=/app/bin:$PATH DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y xmlsec1 \
 && curl -sL https://deb.nodesource.com/setup_8.x | bash - \
 && apt-get install -y nodejs \
 && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
 && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
 && apt-get update && apt-get install yarn \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
 && useradd --create-home --user-group --uid 1000 --shell `which bash` user

RUN mkdir -p /app && chown -R user:user /app

USER user
WORKDIR /app
