FROM debian:stretch-slim

RUN apt-get update \
    && apt-get install -y php-fpm php-curl \
    php-json php-xml php-xml php-zip \
    php-mysql php-sqlite3 php-pgsql php-mbstring php-bcmath \
    php-gd php-mcrypt php-ldap

RUN mkdir -p /var/www/kanboard \
    && mkdir -p /var/run/php \
    && mkdir -p /var/log \
    && sed -i -e 's/listen = \/run\/php\/php7.0-fpm.sock/listen = 9000/g' /etc/php/7.0/fpm/pool.d/www.conf

WORKDIR /var/www/kanboard

COPY --chown=www-data:www-data ./kanboard .

STOPSIGNAL SIGQUIT

EXPOSE 9000

CMD ["/usr/sbin/php-fpm7.0", "-F"]
