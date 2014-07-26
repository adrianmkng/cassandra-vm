# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "https://dl.dropboxusercontent.com/u/35364246/ubuntu-precise_x86_64.box"
  config.vm.host_name = "cassandra-node-1"
  config.vm.network :private_network, ip: "192.168.10.201"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
end
