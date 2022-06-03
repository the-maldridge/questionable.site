FROM busybox
WORKDIR /srv/www
COPY index.html index.html
ENTRYPOINT ["/bin/busybox", "httpd", "-f", "-p", "8080"]
EXPOSE 8080/tcp
