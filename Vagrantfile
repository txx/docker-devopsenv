# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"

  config.vm.synced_folder "./fiberby", "/opt/fiberby", type: "nfs"

  config.vm.provider "libvirt" do |libv|
    libv.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get full-upgrade -y 
  SHELL

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "setup.yml"
  end

end
