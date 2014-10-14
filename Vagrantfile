# -*  mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.synced_folder ".", "/usr/src/app" # don't blame me, /usr/src/app is what the Docker provided rails app is configured to use

  config.vm.define 'test-app' do |r|
    r.vm.provider 'docker' do |d|
        d.name = "test-app"
	d.build_dir = "."
	d.ports     = ["3000:3000"]
    end
  end
end
