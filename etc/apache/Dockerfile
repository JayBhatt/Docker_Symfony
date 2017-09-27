#Get the base image
FROM ubuntu:16.04

#Install Apache
RUN apt-get update && \
    apt-get dist-upgrade -y && \
    apt-get install -y \
      apache2 \
      apache2-utils

# Enable modules
RUN a2enmod rewrite
RUN a2enmod proxy
RUN a2enmod proxy_fcgi

# Add user to www-data
RUN groupadd 1000
RUN usermod -a -G 1000 www-data
RUN usermod -a -G staff www-data

RUN service apache2 restart

# Run config
ENTRYPOINT [ "/usr/sbin/apache2ctl" ]
CMD [ "-D", "FOREGROUND" ]