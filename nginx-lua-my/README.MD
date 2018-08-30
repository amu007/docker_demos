docker build -t nginx-lua-my .

docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua-my/tools:/var/www/webapp/ nginx-lua-my


docker run -itd -p 803:80 -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua/servers:/etc/nginx/conf.d -v /Users/lichengzhou/code/lab/docker_demos/nginx-lua-my/tools:/var/www/webapp/ nginx-lua-my



cd debian
docker build -t nginx-lua-debian .
docker run -itd --name debian nginx-lua-debian








2. 挂载程序image
        a. 先执行这个java-demo. 它不会启动。但会在docker ps -a中存在
                docker run -itd --name java-demo1 java-demo
        b. 再加volumes-from 启动
            docker run -itd -p 8080:8080 --name java81 --volumes-from=java-demo1 lwieske/java-8:jdk-8u111 java -jar /var/www/webapp/redirectDemo-0.0.1-SNAPSHOT.jar
            
            docker run -itd -p 8080:8080 --name java81 --volumes-from=java-demo1 lwieske/java-8:jdk-8u111 java -jar /var/www/webapp/switcher-0.0.1-SNAPSHOT.jar