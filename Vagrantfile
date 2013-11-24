# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.host_name = "cassandra-node1"
  config.vm.network :private_network, ip: "192.168.10.2"

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "ruby_build"
    chef.add_recipe "cassandra"
 
    # You may also specify custom JSON attributes:
    # chef.json = { :mysql_password => "foo" }
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.berkshelf.enabled = true

end
