#FROM debian:stretch-slim
FROM ubuntu:14.04

MAINTAINER NGINX Docker Maintainers "docker-maint@nginx.com"

COPY tools/LuaJIT-2.0.5.tar.gz /home/software/
COPY tools/nginx-1.13.4.tar.gz /home/software/
COPY tools/v0.10.10.tar.gz /home/software/
COPY tools/v0.3.0.tar.gz /home/software/
COPY tools/nginx.conf /home/software/



RUN apt-get update \
	&& apt-get install --no-install-recommends --no-install-suggests -y g++ gcc make build-essential autoconf libtool libpcre3-dev asciidoc xmlto libev-dev libudns-dev automake libssl-dev zlib1g-dev vim \
	&& cd /home/software/ \
	&& tar -zxvf /home/software/LuaJIT-2.0.5.tar.gz \
	&& tar -zxvf /home/software/nginx-1.13.4.tar.gz \
	&& tar -zxvf /home/software/v0.10.10.tar.gz \
	&& tar -zxvf /home/software/v0.3.0.tar.gz \

	&& cd /home/software/LuaJIT-2.0.5 \
	&& make PREFIX=/home/lib/lj2 && make install PREFIX=/home/lib/lj2 \
	&& export LUAJIT_LIB=/home/lib/lj2/lib/ \
	&& export LUAJIT_INC=/home/lib/lj2/include/luajit-2.0/ \

	&& cd /home/software/nginx-1.13.4 \
	&& ./configure --prefix=/opt/nginx --with-ld-opt="-Wl,-rpath,/home/lib/lj2/lib" --add-module=/home/software/ngx_devel_kit-0.3.0 --add-module=/home/software/lua-nginx-module-0.10.10  --with-http_addition_module --with-http_auth_request_module --with-http_dav_module --with-http_flv_module --with-http_gunzip_module --with-http_gzip_static_module --with-http_mp4_module --with-http_random_index_module --with-http_realip_module --with-http_secure_link_module --with-http_slice_module --with-http_ssl_module --with-http_stub_status_module --with-http_sub_module --with-http_v2_module --with-mail --with-mail_ssl_module --with-stream --with-stream_realip_module --with-stream_ssl_module --with-stream_ssl_preread_module \
	&& make && make install \
	&& cp /home/software/nginx.conf /opt/nginx/conf \
	&& mkdir /opt/nginx/conf/servers




CMD ["/opt/nginx/sbin/nginx", "-g", "daemon off;"]