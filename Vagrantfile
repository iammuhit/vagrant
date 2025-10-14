# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.compatibility_mode = "2.0"
  end
end
