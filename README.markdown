# What is this?

A bare bones example for developing a Rails app using Vagrant and Docker

# Getting up and running

Set up your pre-requisites

* Be running on Linux. I used an Ubuntu 14.04 Linux VM running in VMWare Workstation on a Windows 8.1 host. I did have chruby and ruby installed too, so those may be needed too.
* Install Vagrant - http://www.vagrantup.com/downloads - make sure you install 1.6+. Ubuntu's package are too old, so get the dpkg from the URL listed.
* Install Docker - https://docs.docker.com/installation/
* Install nsenter - https://github.com/jpetazzo/nsenter - optional, but useful for easier console sessions within your Docker container

Then to try this example

* `declare -x VAGRANT_DEFAULT_PROVIDER="docker"` # Set the environment variable VAGRANT_DEFAULT_PROVIDER to docker
* `git clone http://github.com/muness/vagrant-docker-rails-example`
* `cd vagrant-docker-rails-example`
* `vagrant up` # to start your container including a rails server. this will run bundle install too on boot up
* `vagrant up --debug | tee logs/vagrant-up.log` # you'll need this sooner or later. ;)
* `docker-enter test-app` # get a bash session in your container via nsenter. Your app is at /usr/src/app. You can then `cd /usr/src/app ; rails c` to get a rails console
* `vagrant reload` # restart your rails server
* `vagrant destroy` # to kill your image

# Details

See `Vagrantfile` and `Dockerfile` . Hope they save you some time the first time you try to get this working.
