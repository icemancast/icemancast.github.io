---
layout: post
title: Getting Started with Laravel Homestead
tags:
- Laravel
- Artisan
- Composer
- PHP 
- Homestead
featured_image: laravel
link1_title: Watch Laravel Homestead Video
link1_url: https://www.youtube.com/watch?v=NcIPANwBghU
excerpt: Laravel is a php mvc framework that has gained a lot of popularity in the php community. With laravel you can create custom applications and get up in running a shorter amount of time.
---
Laravel Homestead is Laravel's virtual machine setup that can run an entire laravel site setup. Not only that but in this video you can also see that you can add multiple local sites to install. I have been developing my own virtual machine with ansible that I maintain and keep up with for all my dev projects before homestead came about. Reading over the documention for homestead and filling in the the gaps from my own virtual machine experience, I recorded a video showing how to install
Laravel Homestead. [Watch the Laravel Homestead video](https://www.youtube.com/watch?v=NcIPANwBghU)
and leave me a comment below.

## My notes from the video

The instructions below are for installing homestead on a mac machine. Most of these may cary over to a pc but there may be some different inputs that are better covered on the Laravel Docs for homestead.

First make sure you install vagrant and virtual box. After that run the following. Note it may take a while since you will be downloading the box to your computer.

## Why a virtual machine

A virtual machine gives you the ability to be as close as you can to the actual production environment. Not only that but because it is so cheap/easy to spin up a virtual machine that if the box breaks you can either provision it or start a new one easily.

## Prerequisites

### Subl command

    ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl

### Composer

    curl -sS https://getcomposer.org/installer | php
    mv composer.phar /usr/local/bin/composer

### Sequel Pro

  [Download sequel pro](http://www.sequelpro.com/). It's a great tool for mysql administration.

### SSH Keys

[Generate your SSH Keys](https://help.github.com/articles/generating-ssh-keys/)

## Vagrant and Virtualbox which you can install with the following:

### Install homebrew

Homebrew allows you to install other applications easily at the command line.

  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

### Install Cask

This allows you to install Cask which helps with install Mac Applications.

    brew install caskroom/cask/brew-cask

### Install Vagrant and Virtualbox

    brew cask install vagrant
    brew cask install virtualbox

## Installing homestead

    $ cd ~
    $ vagrant box add laravel/homestead

Next we need to install the homestead recipe for our server. The yaml file that gets installed will help you manage your own local domains.

    $ git clone https://github.com/laravel/homestead.git vagrant-homestead
Next run the initialization script for homestead

    $ cd vagrant-homestead
    $ bash init.sh

Open the following file in your favor editor:

    /Users/(yourUser)/.homestead/Homestead.yml

I modified the folders to have "nfs" type because I noticed a better performance with the tie to my local folder. So my yaml file looks like below

    folders:
        - map: ~/Sites
          to: /home/vagrant/Code
          type: "nfs"
    
    sites
        - map: homestead.app
          to: /home/vagrant/Code/homestead.app/public

I left my ssh keys alone since they are same ones I use for most stuff. so yours should be:

    ~/.ssh/id_rsa.pub

If you have not setup your ssh keys just yet you should now. Here are the instructions to do so. [Setup SSH Keys](https://help.github.com/articles/generating-ssh-keys/).

## Run vagrant up

    cd ~
    vagrant up

## Edit your local vhost

Edit your hosts file in your favorite editor.

    $ sudo vi /etc/hosts
    192.168.10.10  homestead.app

## Install a laravel site

    $ composer create-project --prefer-dist laravel/laravel homestead.app

    $ composer install
