# A lightweight Laravel development environment using Docker

A fork from [TrafeX/docker-php-nginx](https://github.com/TrafeX/docker-php-nginx)

## What's included?

* PHP 7.3
* Alpine 3.12

Extenstion:
* OPcache
* json
* OpenSSL
* Curl
* ZLib
* XML
* Phar
* intl
* dom
* xmlreader
* ctype
* session
* mbstring
* gd
* sockets
* zip
* bz2
* pcntl
* bcmath
* fileinfo
* tokenizer

Tools:
* composer
* curl
* supervisor

Databases:
* SQLite
* PostgreSQL
* MySQL

⚠️ These are `pdo` extensions, you  should add actual database image(s).

Also:
* Memcached
* Redis

⚠️ These are php extensions to enable working with theses tools, you should add actual redis or memcached image(s).

## Features

* Out of the box queue worker and task scheduler
* Lightweight 127MB

## How to use?

docker-compose.yml:

```yml
version: "3.2"

services:
  app:
    image: amirmasoud32/docker-laravel-dev:[version]
    ports:
      - 8080:8080
    working_dir: /var/www/html
    volumes:
      - .:/var/www/html
```

## Default user?

`nobody`

## composer & artisan

`docker-compose exec app composer [command]`
`docker-compose exec app php artisan [command]`

or ssh into container first:

`docker-compose exec app sh`

and then run your command.

## working directory

`/var/www/html`

for example if you want to use SQLite if you have created `database\database.sqlite`
file your `.env` database section should look like below:

```
DB_CONNECTION=sqlite
DB_DATABASE=/var/www/html/database/database.sqlite
```

If you are facing permission problem after when running database relatd command
after setting SQLite you should:

1. `docker exec -it --user root [container_name] sh`
2. `chown nobody:nobody database/database.sqlite`
3. run your database command

## root user

`docker exec -it --user root [container_name] sh`
