FROM httpd:2.4.34-alpine

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-alpine-linux-amd64-$DOCKERIZE_VERSION.tar.gz

COPY httpd.conf.tmpl /etc/dockerize-templates/

CMD dockerize -template /etc/dockerize-templates/httpd.conf.tmpl:/usr/local/apache2/conf/httpd.conf httpd-foreground
