# What is this?

A bare bones example for developing a Rails app using Vagrant and Docker

# Getting up and running

Pre-requisites

* Be running on Linux. I used an Ubuntu 14.04 Linux VM running in VMWare Workstation on a Windows 8.1 host.
* Install Vagrant - http://www.vagrantup.com/downloads - make sure you install 1.6+. Ubuntu's package will be too old, so get the dpkg from the URL listed.
* Install Docker - https://docs.docker.com/installation/
* Install nsenter - https://github.com/jpetazzo/nsenter - optional, but useful for easier console sessions within your Docker container


Then

* `git clone http://github.com/muness/vagrant-docker-rails-example`
* `cd vagrant-docker-rails-example`
* `vagrant up` # to start your container including a rails server
* `docker-enter test-app` # to get a bash session in your container via nsenter. Your app is at /usr/src/app. You can then `cd /usr/src/app ; rails c` to get a rails console
* `vagrant reload` # restart your rails server
* `vagrant destroy` # to kill your image


