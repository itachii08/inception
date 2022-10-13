FROM debian:buster
EXPOSE 443

RUN apt-get update
RUN apt-get install -y nginx 
COPY ./conf/default /etc/nginx/sites-available/
COPY ./conf/zoizmer.crt /etc/nginx
COPY ./conf/zoizmer.key /etc/nginx
RUN rm -rf /var/www/html/*

ENTRYPOINT ["nginx", "-g", "daemon off;"]
