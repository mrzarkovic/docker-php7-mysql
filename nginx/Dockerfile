FROM nginx:latest

ADD conf/site.conf /etc/nginx/conf.d/site.conf

RUN apt-get update \
	&& apt-get install nano -y