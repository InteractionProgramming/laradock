## Install Docker
## Clone laradock

````git clone https://github.com/InteractionProgramming/laradock.git````

## Change laradock .env

The `.env` file contains the configuration for all containers.
The .env file in this repository is preconfigured for the mooc setup.

## Build images (every time you change .env) 

```` 
docker-compose build apache2 mysql redis mongo workspace
````

## Start containers (in daemon mode)
```
docker-compose up -d apache2 mysql redis mongo workspace
```

## View container logs
```
docker-compose logs -f
```

## Install dependencies via Composer, NPM and Bower

```
docker-compose exec -w /var/www/lumen workspace composer install
docker-compose exec -w /var/www/admin workspace npm install
docker-compose exec -w /var/www/admin workspace bower install
docker-compose exec -w /var/www/editor workspace npm install
docker-compose exec -w /var/www/editor workspace bower install
```

## Create database schema and add test data

```
docker-compose exec -w /var/www/lumen workspace php artisan migrate --seed
```

## Start MOOC server
```
docker-compose exec -w /var/www/node workspace node server.js
```

## Start Admin dashboard on port 3000

```
docker-compose exec -w /var/www/admin workspace gulp
```

## Login

Open `http://localhost:3000` in your browser and login

## Start Editor dashboard on port 3000

- Stop Admin dashboard with Ctrl+C in your terminal
- Start Editor

```
docker-compose exec -w /var/www/editor workspace gulp
```

Open `http://localhost:3000` in your browser and login
