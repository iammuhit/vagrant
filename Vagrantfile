# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  # Install git using an external shell script
  config.vm.provision "shell" do |s|
    s.name = "Git Installation"
    s.path = "scripts/git-install.sh"
    s.env  = { "DEBIAN_FRONTEND" => "noninteractive" }
    s.privileged = true
  end
end
