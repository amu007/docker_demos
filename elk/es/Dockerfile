FROM ubuntu-java8:latest

MAINTAINER licz <licz1984@gmail.com>

#RUN useradd es -u 1000 -s /bin/bash 
#RUN apt-get update \
#        && apt-get install --no-install-recommends --no-install-suggests -y sudo curl vim

USER root

#RUN groupadd -r es && useradd  -c 'ElasticSearch user' -m -d /home/es -s /bin/bash --no-log-init -r -g es es \
#RUN useradd -c 'ElasticSearch user' -m -d /home/es -s /bin/bash es \

RUN groupadd -r es && useradd  -c 'ElasticSearch user' -m  -d /home/es -s /bin/bash --no-log-init -r -g es -G root es \
#	&& usermod -g es es \
	&& chown -R es:es /home/es 
#	&& chgrp -R es /home/es

USER es
WORKDIR /home/es


COPY elasticsearch-5.6.0.tar.gz /home/es/
#COPY jdk-8u144-linux-x64.tar.gz /home/es/
ADD elasticsearch.yml /home/es


#RUN cd /home/es/ \
#	&& tar -zxvf elasticsearch-5.6.0.tar.gz

#COPY elasticsearch.yml /home/es/elasticsearch-5.6.0/config/



CMD cd /home/es/ \
	&& tar -zxvf elasticsearch-5.6.0.tar.gz \
	&& cp /home/es/elasticsearch.yml /home/es/elasticsearch-5.6.0/config/ \
	&& cd /home/es/elasticsearch-5.6.0/ \
	&& bin/elasticsearch
#CMD ["bash"]
