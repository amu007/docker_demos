FROM nginx:latest

MAINTAINER licz <licz1984@gmail.com>

RUN apt-get update && apt-get install -y supervisor
RUN mkdir -p /var/log/supervisor

COPY jdk-8u144-linux-x64.tar.gz /var/www/webapp/
COPY target/switcher-provider-0.0.1-SNAPSHOT.jar /var/www/webapp
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN cd /var/www/webapp \
	&& tar -zxvf jdk-8u144-linux-x64.tar.gz

ENV JAVA_HOME /var/www/webapp/jdk1.8.0_144


CMD ["/usr/bin/supervisord"]
