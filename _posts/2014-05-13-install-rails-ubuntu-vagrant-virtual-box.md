---
layout: post
title: Install Rails on Ubuntu 14 Vagrant Virtual Box
tags:
- Vagrant
- Rails
- Ruby
- Ubuntu 14
- Virtual Box
featured_image: rails
link1_title: rbenv Source and Install
link1_url: https://github.com/sstephenson/rbenv
link2_title: Ruby Buil Install
link2_url: https://github.com/sstephenson/ruby-build#installation
link3_title: Digital Ocean Install Ruby/Rails on Ubuntu
link3_url: https://www.digitalocean.com/community/articles/how-to-install-ruby-on-rails-on-ubuntu-12-04-lts-with-rbenv--2
link3_title: rbenv Multiple Versions of Ruby
link3_url: http://www.lauradhamilton.com/how-to-use-rbenv-to-manage-multiple-versions-of-ruby
excerpt: I wanted to install rails on my Ubuntu 14.04 vagrant virtual box
---
I wanted to install rails on my Ubuntu 14.04 vagrant virtual box just to keep it on a nice development environment and to keep it separate from my MacOSX environment. In all seriousness I think through it all I wanted some sort of bragging rights on something like this. The steps following are what I have compiled from the resources that I have read which are linked to below. Please let me know if you have any issues with the install so I can update this post. My Ubuntu environment was created with vagrant and ansible. If you would like the same setup you can get it here [vagrant-nginx](https://github.com/icemancast/vagrant-nginx). Enjoy!

1. ssh into your vagrant box
		
		$ vagrant ssh

2. Update and install prerequisites
		
		$ sudo apt-get install python-software-properties
		$ sudo apt-get -y install curl git-core nodejs
		$ sudo apt-get install gcc make libsqlite3-dev
		$ sudo apt-get install libssl-dev libtool libxslt libksba openssl
		$ sudo apt-get install postgresql postgresql-contrib
		$ sudo apt-get install build-essential
		$ sudo apt-get -y update
		$ sudo apt-get upgrade

3. clone repo

		$ git clone https://github.com/sstephenson/rbenv.git ~/.rbenv

4. Add path to bash
		
		$ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc

5. Add rbenv init to commands
		
		$ echo 'eval "$(rbenv init -)"' >> ~/.bashrc

6. Reload shell with new bash profile updates

		$ source ~/.bashrc

7. Check if install, should print out rbenv function to terminal

		$ type rbenv

8. install ruby-build so you can use rbenv install

		$ git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

9. Check available ruby versions

		$ rbenv install -l

10. Install ruby version. I installed latest :)

		$ rbenv install 2.1.2
		$ rbenv rehash

11. set global ruby version
	
		$ rbenv global 2.1.2

12. Install bundler and rake. If they are already installed just hit "N" so you don't overwrite them. No need to overwrite it

		$ gem install rdoc
		$ gem install bundler
		$ gem install rake 
		$ rbenv rehash

13. Install rails

		$ gem install rails

14. Reload shell with new bash profile updates

		$ source ~/.bashrc

15. Go to sites directory and create new app

		$ cd /vagrant/sites
		$ rails new test_app
		$ cd test_app

16. Run bundler

		$ bundle update
		$ bundle install
		
17. Start rails server and designate port.

		$ rails s -p 5050

18. Go to rails app via your browser. Go to the ip address of your vagrant box and add the port number used above. See example url below:

	###http://192.168.77.77:5050

19. Write some code :)

View the resources I used to compile this below:

