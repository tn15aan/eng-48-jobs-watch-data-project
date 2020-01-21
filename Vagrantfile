# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.10.150"
  config.hostsupdater.aliases = ["database.local"]

  # provision
  config.vm.provision 'chef_solo' do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe 'dev_env'
    chef.nodes_path = 'nodes'
    chef.arguments = '--chef-license=accept'

  end
end
