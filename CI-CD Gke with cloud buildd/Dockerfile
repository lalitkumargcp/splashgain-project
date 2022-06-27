FROM ubuntu:18.04
ARG httpd=apache2
RUN apt-get update -y
RUN apt-get upgrade -y
RUN DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt-get -y install tzdata
RUN apt-get install $httpd -y
RUN apt-get install php php-mysql -y
RUN rm -rf /var/www/html/index.html
COPY index.php /var/www/html/index.php
EXPOSE 80
WORKDIR /var/www/html/
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
