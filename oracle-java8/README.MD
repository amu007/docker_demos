1. volumes-from的用法

docker run -itd --name java81 --volumes-from=nginx1 lwieske/java-8:jdk-8u111


2. 挂载程序image
	a. 先执行这个java-demo. 它不会启动。但会在docker ps -a中存在
		docker run -itd --name java-demo1 java-demo
	b. 再加volumes-from 启动
	    docker run -itd -p 8080:8080 --name java81 --volumes-from=java-demo1 lwieske/java-8:jdk-8u111 java -jar /var/www/webapp/redirectDemo-0.0.1-SNAPSHOT.jar
	    
	    docker run -itd -p 8080:8080 --name java81 --volumes-from=java-demo1 lwieske/java-8:jdk-8u111 java -jar /var/www/webapp/switcher-0.0.1-SNAPSHOT.jar

3. 参考文档http://blog.csdn.net/chancein007/article/details/50645199
