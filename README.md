
##Overview

This dockerfile allows you to build a container that is suitable for running and testing PHP applications that use Mongo as a Data store.


##Components

- Base: Ubuntu 14.04
- PHP: 5.5x
- Mongo PHP driver (PECL install): 1.6x
- PHP composer
- MongoDB 3.2x binaries 
- Apache 2.4 with mod_rewrite enabled
- XDebug
- nano editor


##Running & Building
###Using this container as a base 
Use this container as a base for your application. Below is an example Dockerfile in which we add a VHost to the apache config:

    FROM antoniom/apache-php-mongo-composer-xdebug

    ADD MyVhost.conf /etc/apache2/sites-enabled/

    CMD ["/run.sh"]
    
###Running
    
        docker run \
         -dit \
         -p 8080:80 \
         -v $(pwd):/var/www \
         antoniom/apache-php-mongo-composer-xdebug;

##Copyright
Released under the Apache 2.0 License
