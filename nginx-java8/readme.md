docker build -t nginx-java8 .

docker run -itd -p 802:80 --name nginx-java nginx-java8

docker run -itd -p 802:80 -p 8031:8030 -v /Users/lichengzhou/docker/nginx_server2:/etc/nginx/conf.d --name nginx-java nginx-java8
