# -*  mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # See https://docs.vagrantup.com/v2/synced-folders/basic_usage.html
  config.vm.synced_folder ".", "/usr/src/app" # don't blame me, /usr/src/app is what the Docker provided rails app is configured to use

  config.vm.define 'test-app' do |r|
    r.vm.provider 'docker' do |d|
        d.name      = "test-app" # for easier interaction with the container via docker commands
	d.build_dir = "."
	d.ports     = ["3000:3000"]
	# See https://docs.vagrantup.com/v2/docker/configuration.html for other Docker specific options
    end
  end
end
