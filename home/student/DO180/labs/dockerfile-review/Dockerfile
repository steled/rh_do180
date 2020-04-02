FROM ubi7/ubi:7.7

MAINTAINER Stephan Leddin <stephan.leddin@unbelievable-machine.com>

ENV PORT 8080

RUN yum install -y httpd

RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
    chown -R apache:apache /etc/httpd/logs/ && \
    chown -R apache:apache /run/httpd/

USER apache

EXPOSE 8080

COPY ./src/ /var/www/html

CMD ["httpd", "-D", "FOREGROUND"]
