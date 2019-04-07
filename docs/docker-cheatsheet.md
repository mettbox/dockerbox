# Docker cheatsheet

Start containers in the background (detached):

```bash
docker-compose up -d
``` 

Start containers on the foreground:

```bash
docker-compose up
``` 

You will see a stream of logs for every running container.

Stop containers:

```bash
docker-compose stop
``` 

Kill containers:

```bash
docker-compose kill
``` 

View container logs:

```bash
docker-compose logs
``` 

Execute command inside of container:

```bash
docker exec -it SERVICE_NAME COMMAND
``` 

**Examples**

Shell into the PHP container:

```bash
docker -it exec laravel-php-fpm bash
``` 

Open a mariadb shell:

```bash
docker exec -it laravel-mariadb mysql -uroot -proot`
``` 

Use Artisan commands:

```bash
docker -it exec php-fpm bash
``` 

and run `php artisan migrate` for example.
