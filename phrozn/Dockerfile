FROM ubuntu:14.04
MAINTAINER Casey Strouse <casey.strouse@gmail.com>

RUN apt-get update
RUN apt-get install -y php5 php-pear curl git tree wget

# Install Composer
RUN curl -s https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

# Install Phrozn
RUN composer create-project Pawka/phrozn phrozn
WORKDIR phrozn
RUN ln -s `pwd`/bin/phrozn.php /usr/local/bin/phr

# Create an initial site
RUN phr init

WORKDIR /phrozn/.phrozn/

CMD ["/bin/bash"]
