FROM httpd:latest
LABEL description "Example Webserver"
WORKDIR /usr/local/apache2/conf
RUN sed -i '/Listen 80/s/80/8080/' httpd.conf
RUN sed -i '/httpd-ssl.conf/s/#//' httpd.conf
RUN sed -i '/LoadModule socache_shmcb_module/s/#//' httpd.conf
RUN sed -i '/LoadModule ssl_module/s/#//' httpd.conf
RUN sed -i '/#ServerName/s/.*/ServerName localhost/' httpd.conf
COPY ./server.crt .
COPY ./server.key .
RUN chown root:www-data ./server.*
EXPOSE 8080
EXPOSE 443
ENTRYPOINT ["httpd", "-D", "FOREGROUND"]
