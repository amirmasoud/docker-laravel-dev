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
    image: amirmasoud32/laravel-docker-dev:[version]
    ports:
      - 8080:8080
    working_dir: /var/www/html
    volumes:
      - .:/var/www/html
```

# Default user?

`nobody`
