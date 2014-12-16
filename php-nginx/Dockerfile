FROM ubuntu
MAINTAINER raphael.messner@gmail.com

RUN apt-get update && apt-get install -y php5-cli php5-common php5-mysql php5-gd php5-fpm php5-cgi php-pear php5-memcache php-apc nginx supervisor

COPY symfony.conf /etc/nginx/sites-enabled/symfony.conf

RUN echo "daemon off;" >> /etc/nginx/nginx.conf

RUN mkdir /src 

COPY Symfony/ /src/

RUN chown -R www-data:www-data /src

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 8080

CMD ["/usr/bin/supervisord"]
