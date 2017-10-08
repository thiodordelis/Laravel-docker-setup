# Docker-PHP7-MariaDB

Forked from https://github.com/shameerc/docker-php7

A boilerplate for a future Laravel project. This is made specific for local development.

# Why
* OS X El Capitan comes with php 5. Newest Laravel need php 7
* There is no need (at least for me) to install/setup Homestead(or Vagrant)

# How to use
* `git clone https://github.com/thiodordelis/Laravel-blog-Docker-setup.git`
* `cd Laravel-blog-Docker-setup`
* `docker-compose up`
* `docker run --rm -v $(pwd):/app composer/composer create-project --prefer-dist laravel/laravel blog` This will install laravel using an alternative method.
* `cd blog`
* Rename Laravel's `.env.example` to `.env`
* Configure `DB_*` settings inside `.env`
* `docker exec <CONTAINER_ID> php artisan key:generate`
* Navigate to `http://localhost:8080/`

# What is included
* Latest nginx, MariaDB, php 7.1, Laravel 5.5
