# Docker-PHP7-MariaDB

Forked from https://github.com/shameerc/docker-php7

A boilerplate for Laravel.

# Why
* OS X El Capitan comes with php 5. Newest Laravel need php 7
* There is no need (at least for me) to install/setup Homestead(or Vagrant)

# How to use
* `mkdir myapp`
* `cd myapp`
* `git clone https://github.com/thiodordelis/Laravel-blog-Docker-setup.git .`
* `docker-compose up`
* `docker run --rm \-v $(pwd):/opt \-w /opt \shippingdocker/php-composer:latest \composer create-project laravel/laravel app` This will install the latest laravel using an alternative method inside the directory `app`
* `cd app`
* Rename Laravel's `.env.example` to `.env` (if not already renamed)
* Configure `DB_*` settings inside `.env`
* `docker exec <CONTAINER_ID> php artisan key:generate` (if not already generated)
* Navigate to `http://localhost:8080/`

# What is included
* Latest nginx, MariaDB, php 7.2, Laravel 5.6
