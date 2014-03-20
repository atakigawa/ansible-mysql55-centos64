# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos64"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "192.168.xxx.xxx"

  config.vm.provider :virtualbox do |vb|
     vb.gui = false
     #add memory if you want
     #vb.customize ["modifyvm", :id, "--memory", "1024"]
     vb.customize ["modifyvm", :id, "--natdnsproxy1", "off"]
     vb.customize ["modifyvm", :id, "--natdnshostresolver1", "off"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/vagrant.yml"
    #verbose output if you want
    #ansible.verbose = "vvvv"
  end
end
