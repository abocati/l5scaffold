# Laravel 5.4 Scaffold Generator

![Laravel5.4](https://img.shields.io/badge/Laravel-5.4-red.svg)
[![Build Status](https://travis-ci.org/imasami/l5scaffold.svg?branch=develop)](https://travis-ci.org/imasami/l5scaffold)
[![Packagist](https://img.shields.io/packagist/dt/imasami/l5scaffold.svg?style=flat-square)](https://packagist.org/packages/imasami/l5scaffold)

# install

```
composer require --dev imasami/l5scaffold:dev-develop
```

# Usage

## with foreign

```
$ php artisan make:scaffold Shelf \
      --schema='title:string'

$ php artisan make:scaffold Book \
      --schema='title:string, shelf_id:integer:foreign'
```

## generation

```
APP_ROOT
  `-- app/
  |    `-- Book.php
  |    `-- Shelf.php
  |    `-- Http/
  |         `-- Controllers/
  |              `-- BookController.php
  |              `-- ShelfController.php
  |
  `-- database/
  |    `-- migrations/
  |    |    `-- yyyy_mm_dd_his_create_shelves_table.php
  |    |    `-- yyyy_mm_dd_his_create_books_table.php
  |    |
  |    `-- seeds
  |         `-- BookTableSeeder.php
  |         `-- ShelfTableSeeder.php
  |
  `-- routes/
  |    `-- web.php
  |
  `-- resources
       `-- views/
       |    `-- books/
       |    |    `-- create.blade.php
       |    |    `-- edit.blade.php
       |    |    `-- index.blade.php
       |    |    `-- show.blade.php
       |    |
       |    `-- shelves/
       |         `-- create.blade.php
       |         `-- edit.blade.php
       |         `-- index.blade.php
       |         `-- show.blade.php
       |
       `-- error.blade.php
       `-- layout.blade.php
```

```
//  `-- routes/
//       `-- web.php
  
Route::resource('shelves', 'ShelfController');
Route::resource('books', 'BookController');
```

# Testing

```
$ composer update

$ vendor/bin/phpunit -c phpunit.xml
```
