FROM ubuntu:16.10
MAINTAINER jmvilarinho@gmail.com

RUN apt-get update && \
 apt-get install -y apache2  php7.0-mysql && \
 apt-get clean && \
 rm -rf /var/lib/apt/lists/*

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

ENV APACHE_LOCK_DIR /var/lock
ENV APACHE_PID_FILE /var/run/apache2

EXPOSE 80

#COPY 000-default.conf /etc/apache2/sites-available

RUN ln -sf /proc/self/fd/1 /var/log/apache2/access.log && \
    ln -sf /proc/self/fd/1 /var/log/apache2/error.log

ENTRYPOINT ["/usr/sbin/apache2", "-D", "FOREGROUND"]

