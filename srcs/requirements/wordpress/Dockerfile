FROM debian:buster
EXPOSE 9000
RUN apt-get update
RUN apt-get install -y php-fpm php-mysql wget
RUN mkdir -p /var/www/html
RUN wget https://wordpress.org/latest.tar.gz
RUN tar -xzvf latest.tar.gz
COPY ./conf/wp-config.php /wordpress/
COPY ./conf/www.conf /etc/php/7.3/fpm/pool.d/
COPY ./conf/php-fpm.conf /etc/php/7.3/fpm/
COPY ./tools/start.sh /
ENTRYPOINT ["sh", "start.sh"]