# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  config.vm.hostname = "local.magento2"
  config.vm.network "private_network", ip: "192.168.33.11"
  config.vm.synced_folder ".", "/vagrant", type: 'virtualbox'
  config.vm.synced_folder "./magento2", "/home/vagrant/repos/", type: 'virtualbox'

  # Provisioning
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.verbose = "vvvv"
    ansible.extra_vars = "ansible/group_vars/dev.yml"
  end
end
