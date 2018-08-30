
nginx.conf 目录 /etc/nginx

默认include 目录 /etc/nginx/conf.d/*.conf

启动	 
docker run -itd -p 801:80 nginx

docker run -itd -p 801:80 -v /Users/lichengzhou/docker/nginx_server:/etc/nginx/conf.d nginx

docker run -itd -p 801:80 -v /Users/lichengzhou/docker/nginx_server:/etc/nginx/conf.d --name nginx1 nginx

link container
docker run -itd -p 801:80 -v /Users/lichengzhou/docker/nginx_server:/etc/nginx/conf.d --name=nginx1 --link=java81  nginx

docker run -itd -p 801:80 -v /Users/lichengzhou/docker/nginx_server:/etc/nginx/conf.d --name=nginx1 --link=java81:java81  nginx

--link=容器名:hosts名
:后面的名字会出现在container的/etc/hosts后面。访问的时候用hosts名来访问


docker ps 显示所有 docker任务

docker stop cid 停用docker任务

docker rm cid 删除docker任务
