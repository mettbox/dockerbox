# Tacho API

## Dependencies

- [Docker](https://docs.docker.com/engine/installation)  
- [Docker compose](https://docs.docker.com/compose/install/)  

## How to run

1. Clone this Repository  
2. `cd application` and install dependencies using the composer image

```bash
docker run --rm -v $(pwd):/app composer install
```

3. Setup Database credentials in your `.env` file  

```bash
cp .env.example .env
```

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laradev
DB_USERNAME=dbuser
DB_PASSWORD=dbpassword
``` 

4. Once you're done:

```bash
cd ..
docker-compose up
```

This will initialise and start all the containers. 

5. Set Application Key. 

```bash
# Open an interactive bash inside the running php container
docker exec -it laradev-php-fpm bash

# and run:
php artisan key:generate
```

6. Open your Browser: `http://localhost:8080`  

## Services exposed outside your environment

Webserver: [localhost:8080](http://localhost:8080)  
MariaDB: 127.0.0.1:3306  

## php.ini

Set up your PHP environment in `./docker/php-fpm/php-ini-overrides.ini`.
