# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/ubuntu1604-desktop"

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    # update
    sudo apt-get update
    sudo apt-get dist-upgrade -y

    # install git, vim and curl
    sudo apt-get install -y git vim curl

    # install atom
    wget https://github.com/atom/atom/releases/download/v1.10.0/atom-amd64.deb
    sudo dpkg -i atom-amd64.deb
    rm -f atom-amd64.deb

    # install visual studio code
    wget https://go.microsoft.com/fwlink/?LinkID=760868 -O code.deb
    sudo dpkg -i code.deb
    rm -f code.deb

    # install go
    sudo curl -O https://storage.googleapis.com/golang/go1.7.linux-amd64.tar.gz
    sudo tar -xvf go1.7.linux-amd64.tar.gz
    sudo mv go /usr/local
    export PATH=$PATH:/usr/local/go/bin
  SHELL
end
