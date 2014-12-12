FROM centos:centos7

RUN yum install -y php curl php-xml php-pdo

RUN sed -i 's/;date.timezone =/date.timezone = Europe\/Paris/g' /etc/php.ini

RUN curl -LsS http://symfony.com/installer > symfony.phar

RUN mv symfony.phar /usr/local/bin/symfony

RUN chmod a+x /usr/local/bin/symfony

RUN /usr/local/bin/symfony new src

EXPOSE 8000

CMD cd /src && php app/console server:run 0.0.0.0:8000
