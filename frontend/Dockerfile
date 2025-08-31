FROM node:24-alpine
COPY . /opt/
WORKDIR /opt
ENV BACKEND=54.80.161.173    
RUN npm install && npm run build
RUN apk update && apk add apache2
RUN rm -rf /var/www/localhost/htdocs/*
RUN cp -rf dist/* /var/www/localhost/htdocs
EXPOSE 80
ENTRYPOINT ["httpd","-D","FOREGROUND"]
