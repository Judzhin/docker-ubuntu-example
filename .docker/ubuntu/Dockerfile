FROM ubuntu:bionic-20210930

ENV TZ=Europe/Kiev

RUN ln -sf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone \
    # Update and Install ext
    && apt update && apt install -y curl wget mc bash-completion strace telnet imagemagick tcpdump ufw \
    # http server
    nginx \
    # Setup php
    php7.2-fpm php7.2-common php7.2-mbstring php7.2-xmlrpc php7.2-soap php7.2-gd php7.2-xml php7.2-cli php7.2-curl \
    php7.2-zip php7.2-intl php7.2-bcmath \
    # Setup MySQL
    # mysql_secure_installation
    # mysql-server mysql-client php7.2-mysql \
    mariadb-server mariadb-client php7.2-mysql \
    # Setup Memcached
    memcached php7.2-memcache \
    # Setup Redis
    redis-server php7.2-redis

ADD .docker/ubuntu/etc/nginx/sites-available/001-htmly.conf /etc/nginx/sites-available/001-htmly.conf
RUN ln -snf /etc/nginx/sites-available/001-htmly.conf /etc/nginx/sites-enabled/001-htmly.conf

    # Set work directory
WORKDIR /var/www/html

    # Create and install demo project
RUN wget https://github.com/danpros/htmly/releases/download/v2.7.4/installer.php -P /var/www/html/htmly \
    # && chown -R www-data:www-data /var/www/html/htmly/ \
    && chmod -R 0777 /var/www/html/htmly/

CMD ["sleep", "infinity"]