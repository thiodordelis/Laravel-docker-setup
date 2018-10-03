# Docker-PHP7-MariaDB

Forked from https://github.com/shameerc/docker-php7

A Laravel 5.5+ setup for local development without Homestead / Vagrant or installed PHP 7.

# Why
* OS X El Capitan comes with php 5. Latest Laravel 5.5+ needs PHP 7
* You don't have to set up Homestead or Vagrant.

# How to use
* `mkdir myapp`
* `cd myapp`
* `git clone https://github.com/thiodordelis/Laravel-blog-Docker-setup.git .`
* `docker-compose up -d`
* `docker run --rm \-v $(pwd):/opt \-w /opt \shippingdocker/php-composer:latest \composer create-project laravel/laravel app` This will install the latest laravel using an alternative method inside the directory `app`
* `cd app`
* Rename Laravel's `.env.example` to `.env` (if needed)
* Configure `DB_*` settings inside `.env`
* `docker exec <CONTAINER_ID> php artisan key:generate` (if needed)
* Navigate to `http://localhost:8080/`

#Extras
* To run `php artisan` commands -> `docker exec -it php php artisan <command>`
* Update Laravel and all the packages with composer -> `docker run --rm \-v $(pwd):/opt \-w /opt \shippingdocker/php-composer:latest \composer update`

# What is included
* Latest nginx, MariaDB, PHP 7, Laravel 5.6
