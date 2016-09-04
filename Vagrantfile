# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "box-cutter/ubuntu1404-desktop"

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    # update
    sudo apt-get update
    # sudo apt-get dist-upgrade -y

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

    # install gvm, go
    sudo apt-get install -y bison libreadline-dev
    bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
    source /home/vagrant/.gvm/scripts/gvm
    gvm install go1.4.3
    gvm use go1.4.3
    gvm install go1.7
    gvm use go1.7 --default
  SHELL
end
