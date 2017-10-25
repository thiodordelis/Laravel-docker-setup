FROM ubuntu:latest

RUN apt-get update && apt-get install -y software-properties-common language-pack-en-base \
    && LC_ALL=en_US.UTF-8 add-apt-repository -y ppa:ondrej/php \
    && apt-get update \
    && apt-get install -y php7.1 php7.1-fpm php7.1-mysql mcrypt php7.1-gd curl \
       php7.1-curl php-redis php7.1-mbstring sendmail supervisor \
    && mkdir /run/php \
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

RUN sed -i -e 's/listen = \/run\/php\/php7.1-fpm.sock/listen = 0.0.0.0:9000/g' /etc/php/7.1/fpm/pool.d/www.conf \
    && sed -i -e 's/;daemonize = yes/daemonize = no/g' /etc/php/7.1/fpm/php-fpm.conf \
    && sed -i "s|;*upload_max_filesize =.*|upload_max_filesize = 50M|i" /etc/php/7.1/fpm/php.ini \
    && sed -i "s|;*max_file_uploads =.*|max_file_uploads = 200|i" /etc/php/7.1/fpm/php.ini \
    && sed -i "s|;*post_max_size =.*|post_max_size = 100M|i" /etc/php/7.1/fpm/php.ini 


WORKDIR /var/app

EXPOSE 9000

CMD ["/usr/bin/supervisord"]
