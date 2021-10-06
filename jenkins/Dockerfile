FROM jenkins/jenkins

USER root
RUN apt-get update && apt-get -y install lsb-release wget
RUN apt-get -y install apt-transport-https lsb-release ca-certificates curl
RUN wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list

RUN apt-get update && apt-get -y install php7.4 php-mbstring php-xml php-bcmath php-mysql php-redis

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
