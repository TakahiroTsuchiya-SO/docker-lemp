FROM centos:7
RUN yum -y update
RUN yum install -y php php-fpm
RUN mkdir -p /run/php-fpm

COPY php.ini /usr/local/etc/php/
COPY www.conf /etc/php-fpm.d/www.conf
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN useradd nginx
WORKDIR /var/www/