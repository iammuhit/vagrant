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

  # Configure git using inline shell commands
  config.vm.provision "shell" do |s|
    s.name   = "Git Configuration"
    s.inline = <<-SHELL
      git config --global user.name "Nurul Amin Muhit"
      git config --global user.email "me@muhit.me"
      git config --global init.defaultBranch "master"
    SHELL
  end

  # Verify git installation
  config.vm.provision "shell" do |s|
    s.name   = "Git Install Verification"
    s.inline = "git --version"
  end

  # Verify git configuration
  config.vm.provision "shell" do |s|
    s.name   = "Git Config Verification"
    s.inline = "git config $@"
    s.args   = ["--global", "--list", "--show-origin"]
  end
end
