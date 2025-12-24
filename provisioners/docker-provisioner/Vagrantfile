# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision :docker do |d|
    d.run "web",
      image: "nginx:latest",
      args: "-p 8080:80",
      restart: "always"
  end
end
