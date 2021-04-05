FROM node:lts-alpine as local

WORKDIR /var/www/html

COPY package*.json ./

RUN npm install

COPY . ./

FROM locals

EXPOSE 8080

CMD [ "node", "server.js" ]
