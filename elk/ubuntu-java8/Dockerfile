FROM ubuntu:14.04

MAINTAINER licz <licz1984@gmail.com>

RUN apt-get update \
        && apt-get install --no-install-recommends --no-install-suggests -y sudo curl vim


COPY jdk-8u144-linux-x64.tar.gz /home/software/


RUN cd /home/software/ \
	&& tar -zxvf jdk-8u144-linux-x64.tar.gz


ENV JAVA_HOME /home/software/jdk1.8.0_144/
ENV PATH $PATH:$JAVA_HOME/bin


CMD ["bash"]
