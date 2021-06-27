FROM nginx:alpine as local

ADD ./infrastructure/conf/nginx-service.conf /etc/nginx/conf.d/default.conf

FROM local

WORKDIR /var/www/html/public

# create link to public storage
RUN ln -s ../storage/app/public ./storage
