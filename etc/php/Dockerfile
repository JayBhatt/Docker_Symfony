FROM ubuntu:16.04

# Install PHP
RUN apt-get clean && \
	apt-get -y update && \
	apt-get install -y locales \
	curl \ 
	software-properties-common \ 
	git && \
	locale-gen en_AU.UTF-8	 
RUN LC_ALL=en_AU.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update
RUN apt-get install -y --force-yes php7.1-bcmath \ 
				php7.1-bz2 \ 
				php7.1-cli \
				php7.1-common \
				php7.1-curl \
                php7.1-cgi \ 
                php7.1-dev \
                php7.1-fpm \
                php7.1-gd \
                php-ldap \
                php7.1-gmp \
                php7.1-intl \
                php7.1-json \
                php7.1-mbstring \
                php7.1-mcrypt \
                php7.1-mysql \
                php-sqlite3 \
                php7.1-opcache \
                php7.1-phpdbg \
                hp7.1-pspell \
                php7.1-readline \
                php7.1-recode \ 
                php7.1-soap \ 
                php7.1-tidy \
                php7.1-xml \
                php7.1-xmlrpc \
                php7.1-xsl \
                php7.1-zip \
                php-xdebug
                
# Install Composer
RUN curl https://getcomposer.org/installer > composer-setup.php && php composer-setup.php && mv composer.phar /usr/local/bin/composer && rm composer-setup.php

# Clean files
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Run PHP-FPM
CMD ["php-fpm7.1"]