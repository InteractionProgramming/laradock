## Install Docker
## Clone laradock

````git clone ...````

## Change laradock .env

APACHE_WEB_...

## Start containers

````docker-compose up -d apache2 mysql workspace````
## Install dependencies via Composer

````
docker-compose exec workspace bash
composer install
````

bind-address=0.0.0.0??

mysql version 5.7
createdb.sql

ports in laradock

node_version 11.15

bower in workspace container?

node server with SQL config

php artisan migrate --seed

docker-compose exec workspace bash -itc "cd node && node server.js"
docker-compose exec -w /var/www/node workspace node server.js

docker-compose exec -w /var/www/admin workspace npm i
docker-compose exec -w /var/www/admin workspace bower i
docker-compose exec -w /var/www/admin workspace gulp
