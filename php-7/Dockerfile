FROM php:7.1-fpm

RUN docker-php-source extract \
	&& apt-get update \
	&& apt-get install curl php5-cli git -y \
	&& curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && apt-get install autoconf g++ make openssl libssl-dev libcurl4-openssl-dev pkg-config libsasl2-dev libpcre3-dev libmcrypt-dev libldap2-dev nano -y \
	&& rm -rf /var/lib/apt/lists/* \
	&& docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu \
	&& docker-php-ext-install mbstring ldap pdo pdo_mysql \
	&& docker-php-ext-install -j$(nproc) mcrypt \
	&& docker-php-source delete