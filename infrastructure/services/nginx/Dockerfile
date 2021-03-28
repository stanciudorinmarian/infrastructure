FROM nginx:alpine as local

ADD ./infrastructure/conf/nginx-service.conf /etc/nginx/conf.d/default.conf

FROM local

ADD ./public /var/www/html/public
