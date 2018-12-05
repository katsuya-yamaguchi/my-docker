FROM ruby:2.3

RUN apt-get update && apt-get install -y --no-install-recommends systemd \
nginx \
postgresql-client

CMD systemctl start nginx

