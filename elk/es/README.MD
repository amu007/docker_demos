docker build -t elk-es .



docker run -itd -p 9300:9300 -p 9200:9200 elk-es

docker run -itd elk-es

docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua-my/tools:/var/www/webapp/ nginx-lua-my


docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua/servers:/etc/nginx/conf.d -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua-my/tools:/var/www/webapp/ nginx-lua-my



                                