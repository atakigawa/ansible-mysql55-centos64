# Install mysql5.5 on CentOS6 by ansible.

An ansible version of [this site](http://blog.iphoting.com/blog/2012/06/19/upgrading-to-mysql-5-dot-5-on-centos-6), so check it out for further understandings of each task.

This playbook only does minimum stuff, not meant to be used as is in serial applications.
Intended be copied into other playbook and modified as needed.

The Vagranfile in this repository is a memo, just to show an example setting.

write something like below in your Vagrantfile and call ```vagrant provision```

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/vagrant.yml"
    # comment in for debugging
    # ansible.verbose = "vvv"
  end

To run the playbook manually, add neccessary host information to the inventory file(path for ssh key, for example), then call something like

  ansible-playbook -i vagrant_ansible_inventory_default provisioning/vagrant.yml

Tested in
  vagrant v1.4.1 with [CentOS 6.4 x86_64](https://github.com/2creatives/vagrant-centos/releases/tag/v0.1.0)
  ansible v1.6
