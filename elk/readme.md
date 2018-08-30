docker build -t ubuntu-java8


docker build -t elk-es es/



docker run --rm -itd -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  --name elk-es-instance elk-es 



docker build -t elk-logstash logstash/


docker run -itd -v /Users/lichengzhou/code/lab/docker_demos/elk/logstash/custom-config:/home/logstash/custom-config --name=elk-logstash-instance --link=elk-es-instance:elk-es-instance-bridge elk-logstash



======================




# docker run -itd -p 9300:9300 -p 19200:9200 --name elk-es-instance elk-es -Des.network.host=0.0.0.0
# docker run --rm -itd -p 9300:9300 -p 19200:9200 --name elk-es-instance elk-es 


docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  --name elk-es-instance elk-es 


docker run --rm -itd -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node"  --name elk-es-instance elk-es 



docker run --rm -itd -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elk-es 

docker build -t elk-logstash logstash/


docker run -itd -v /Users/lichengzhou/code/lab/docker_demos/elk/logstash/custom-config:/home/software/custom-config --name=elk-logstash-instance --link=elk-es-instance:elk-es-instance-bridge elk-logstash


docker run -d -p 9200:9200 -p 9300:9300 --name=elk-es-instance elk-es:latest -Ds.network.host=0.0.0.0