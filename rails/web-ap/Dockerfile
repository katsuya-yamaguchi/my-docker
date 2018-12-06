FROM ruby:2.3

RUN apt-get update && apt-get install -y --no-install-recommends systemd \
nginx \
postgresql-client

COPY ./nginx/nginx.conf /etc/nginx/
COPY ./nginx/sslcert/server.crt /etc/nginx/
COPY ./nginx/sslcert/private.pem /etc/nginx/

CMD systemctl start nginx

