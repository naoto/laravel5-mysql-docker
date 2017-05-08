FROM        amazonlinux:latest
MAINTAINER  Naoto SHINGAKI <n.shingaki@gmail.com>

# Install dependency packages
RUN  yum groupinstall -y "Development Tools"
RUN  yum install -y apr-util-devel pcre-devel openssl-devel
RUN  yum install -y mysql56 telnet

# Install PHP packages
RUN  yum install -y \
      php56 \
      php56-common \
      php56-mbstring \
      php56-mysqlnd \
      php56-pdo \
      php56-jsonc \
      php56-xml \
      php56-gd \
      php56-process \
      php56-cli \
      php56-pecl-imagick \
      php56-pecl-redis \
      php56-pecl-igbinary \
      php56-pecl-apcu \
      php56-opcache \
      php-pear

# Install Composer
RUN  curl -sS https://getcomposer.org/installer | php && \
     mv composer.phar /usr/local/bin/composer

# Composer parallel install plugin https://github.com/hirak/prestissimo
RUN  composer global require "hirak/prestissimo:^0.3"

WORKDIR /var/www/html

EXPOSE     80
ENTRYPOINT ["/usr/sbin/httpd"]
CMD        ["-D", "FOREGROUND"]
