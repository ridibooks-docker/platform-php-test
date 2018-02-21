FROM ridibooks/php:7.1
MAINTAINER js.park@ridi.com

RUN apt-get update -y

# install ansible
RUN apt-get install software-properties-common -yqq
RUN apt-add-repository ppa:ansible/ansible -y
RUN LC_ALL=C.UTF-8 apt-add-repository ppa:ondrej/php -y

RUN apt-get update -y

RUN apt-get install ansible -yqq

# install provision package
RUN apt-get install apache2 sudo -yqq && \
	apt-get install php7.1 php7.1-cli php7.1-curl php7.1-gd php7.1-mbstring php7.1-mcrypt \
		php7.1-mysql libapache2-mod-php7.1 php-apcu php7.1-intl php-imagick php7.1-bcmath \
		php7.1-xml php7.1-zip -yqq && \
	apt-get install zip imagemagick gifsicle jpegoptim optipng poppler-utils -yqq

# install node
RUN curl --silent --show-error https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install nodejs -yqq

# enable php ext
RUN apt-get install -y zlib1g-dev libicu-dev g++ && \
	docker-php-ext-configure intl && \
	docker-php-ext-install sockets pdo_mysql intl zip bcmath shmop && \
	pecl install xdebug && docker-php-ext-enable xdebug

# install phpunit
ADD https://phar.phpunit.de/phpunit.phar /usr/local/bin/phpunit 
RUN chmod +x /usr/local/bin/phpunit
