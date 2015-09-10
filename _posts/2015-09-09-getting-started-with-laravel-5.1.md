---
layout: post
title: Getting Started with Laravel 5.1
tags:
- Laravel
- Artisan
- Composer
- PHP 
featured_image: laravel
excerpt: Laravel is a php mvc framework that has gained a lot of popularity in the php community. With laravel you can create custom applications and get up in running a shorter amount of time.
---
Laravel is a php mvc framework that has gained a lot of popularity in the php community. With laravel you can create custom applications and get up in running a shorter amount of time.

I was asked to speak at a local PHP Meetup. Even better yet I was asked to speak about Laravel. So I took advantage of this opportunity and wanted to introduce Laravel 5.1 to the community. I recorded the full meeting and in video and posted it on youtube. Below is also my guideline that you see in the video. Watch the [Getting Started with Laravel 5.1](https://www.youtube.com/watch?v=B7FJV9KIn58) [time: 1:12:00] video now!

### MVC

### Installing composer

Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

[https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)

```
$ curl -sS https://getcomposer.org/installer | php
```

Now you can run `php composer.par` to install packages. Doing the below command you only need to run composer without php and `.phar` part of the command. This moves our composer to our bin so can can just call `composer` from now on.

```
$ mv composer.phar /usr/local/bin/composer
```


### Add the laravel command

Once composer is intalled we can easily install the laravel with the folowing:

```
composer global require "laravel/installer=~1.1"
```

### Make sure laravel command is in our system path

```
subl .bash_profile
PATH="~/.composer/vendor/bin:$PATH"
```

### What's next?
So after those are installed we no longer need to install or start up composer or laravel command anymore. They now belong to our system and can just run them whenever we need.

### Start a new application

To start a laravel 

```
$ laravel new blog
```

Or alternatively you can run:

```
$ composer create-project laravel/laravel blog --prefer-dist
```

### Start the laravel server

```
$ php artisan serve
```
Now you are enter `http://localhost:8000` into your browswer and see the laravel 5 welcome screen. So you can continue to develop 
using the artisan server for your development. You would still need to install mysql for any database usage. For my example I have what is called a virtual box where I can have a hosted development environment. 

### Routes

Routes control the what url entered in the browser displays what information. Below we are just returning a string in the browser.

```
Route::get('/test', function() {
    return 'something here';
});
```

We really won't be returning strings in our browser so lets point this route to a controller that can handle our views.

```
Route::get('/hello', 'WelcomeController@hello');
```
#### Controllers

Create a blank controller with the following command.

```
$ php artisan make:controller WelcomeController --plain
```

## Views

Blade templating basics

## Migration

```
php artisan migrate:make create_posts_table --create=posts
```
