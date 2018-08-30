docker build -t nginx-lua .

docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua/servers:/etc/nginx/conf.d nginx-lua


docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua/servers://nginx/conf/servers/* nginx-lua
