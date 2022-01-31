# syntax=docker/dockerfile:1

FROM nginx:mainline-alpine

# replace default configuration file with one for EveAssist
WORKDIR /etc/nginx/conf.d
RUN rm default.conf
COPY conf.d/default.conf .

RUN apk add openssl && \
	mkdir /etc/ssl/private && \
	openssl req -x509 -nodes -days 365 -subj "/C=CA/ST=QC/O=Company, Inc./CN=mydomain.com" -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt;

WORKDIR /
