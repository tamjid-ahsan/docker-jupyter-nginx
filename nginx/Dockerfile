FROM ubuntu:22.10

RUN apt-get update && apt-get -y install nginx
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 8000
ENTRYPOINT ["/usr/sbin/nginx"]