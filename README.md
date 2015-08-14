## How to start wordpress

step1: 

    docker run --name mariadb-data -v /var/lib/mysql:/var/lib/mysql:rw mariadb true
    docker run --name mariadb-app -d -p 3306:3306 --volumes-from=mariadb-data -e MYSQL_ROOT_PASSWORD=password mariadb

step2:

    Download wordpress to /home/wordpress
    Extract wordpress.tar.gz to /home/wordpress/wordpress

step3: 

    docker run --name wordpress -v /home/wordpress/wordpress:/var/www/html -p 80:80 -d apache/php
