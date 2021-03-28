FROM php:8-fpm-alpine as local

CMD ["supervisord", "-c", "/etc/supervisord.conf"]

RUN mkdir -p /var/log/supervisor
ADD ./infrastructure/conf/queue/supervisord.conf /etc/supervisord.conf
ADD ./infrastructure/conf/queue/supervisor.d /etc/supervisor.d

FROM local

COPY --chown=www-data:www-data ./ /var/www/html
