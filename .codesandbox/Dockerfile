FROM ubuntu AS build
RUN apt update -y && apt install -y apache2
# Install PHP & Composer
RUN apt update -y && DEBIAN_FRONTEND=noninteractive apt install -y curl php-cli php-mbstring git unzip && \
    cd ~ && \
    curl -sS https://getcomposer.org/installer -o composer-setup.php && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    composer --version

RUN apt update -y && apt install -y php-dom
RUN apt update -y && apt install -y php-curl

# COPY apache2/site.conf /etc/apache2/sites-available/site.conf
# RUN a2ensite site
# RUN service apache2 restart