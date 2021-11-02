FROM ubuntu:bionic-20210930

    # Update and Install ext
RUN apt update && apt install -y mc bash-completion  strace telnet imagemagick tcpdump curl wget \
    # http server
    nginx \
    # Setup php
    php7.2-fpm php7.2-common php7.2-mbstring php7.2-xmlrpc php7.2-soap php7.2-gd php7.2-xml php7.2-cli php7.2-curl \
    php7.2-zip php7.2-intl php7.2-bcmath \
    # Setup MySQL
    mysql-client php7.2-mysql \
    # Setup Memcached
    memcached php7.2-memcache \
    # Setup Redis
    redis-server php7.2-redis

    # Set work directory
WORKDIR /var/www/html

    # Create and install demo project
RUN wget https://github.com/danpros/htmly/releases/download/v2.7.4/installer.php

CMD ["sleep", "infinity"]