FROM nginx:latest

RUN mkdir -p /var/www/kanboard \
    && rm /etc/nginx/conf.d/default.conf

WORKDIR /var/www/kanboard

COPY --chown=www-data:www-data ./kanboard .

COPY ./nginx/kanboard.conf /etc/nginx/conf.d/

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
