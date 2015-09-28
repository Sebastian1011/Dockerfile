#Version: 0.0.1

# from daocloud get the basic image
FROM daocloud.io/php:5.6-apache

#install Laravel PHP dependencies 
RUN apt-get update \
    && apt-get install -y \
        libmcrypt-dev \
        libz-dev \
        git \
        wget \
    && docker-php-ext-install \
        mcrypt \
        mbstring \
        pdo_mysql \
        zip \

#clear the install package
	&& apt-get clean \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \

#install Composer, tools of package management

	&& curl -sS https://getcomposer.org/installer \
        | php -- --install-dir=/usr/local/bin --filename=composer

# creat Laravel menu

RUN a2enmod rewrite \
    && mkdir -p /app \
    && rm -fr /var/www/html \
    && ln -s /app/public /var/www/html

WORKDIR /app

# preload Composer dependencies
COPY ./composer.json /app/
COPY ./composer.lock /app/
RUN composer install  --no-autoloader --no-scripts

#copy code to app

COPY . /app

#Composer auto load

RUN composer install \
    && chown -R www-data:www-data /app \
    && chmod -R 0777 /app/storage

#docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d daocloud.io/mysql:5.5
#docker run --name some-app --link some-mysql:mysql -d app-that-uses-mysql


