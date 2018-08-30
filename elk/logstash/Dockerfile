FROM ubuntu-java8:latest

MAINTAINER licz <licz1984@gmail.com>


RUN groupadd -r logstash && useradd  -c 'ElasticSearch user' -m  -d /home/logstash -s /bin/bash --no-log-init -r -g logstash -G root logstash \
	&& chown -R logstash:logstash /home/logstash 

COPY logstash-5.6.0.tar.gz /home/logstash/



USER logstash
WORKDIR /home/logstash

#RUN cd /home/logstash/ \
#	&& tar -zxvf logstash-5.6.0.tar.gz




#CMD cd /home/logstash/logstash-5.6.0.tar.gz/ \
#	&& bin/elasticsearch

CMD ["bash"]
