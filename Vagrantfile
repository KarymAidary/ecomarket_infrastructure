# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = true
  config.vm.network "forwarded_port", guest: 8000, host: 8000
  config.vm.network "forwarded_port", guest: 8050, host: 8050
  config.vm.network "forwarded_port", guest: 3001, host: 3001
  config.vm.network "forwarded_port", guest: 5432, host: 15432
  config.vm.synced_folder "/Users/karim/PycharmProjects/ExpoBusiness/hairbrush", "/home/ubuntu/hairbrush",
    owner: "ubuntu",
    group: "ubuntu"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant.yml"
  end

end
