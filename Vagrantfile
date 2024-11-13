# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
  SHELL

  # DHCP SERVER
  config.vm.define "DHCP" do |dhcp|
    dhcp.vm.hostname = "dhcp"
    dhcp.vm.network "private_network", ip: "192.168.10.1", virtualbox__intnet: "intnet1"
    dhcp.vm.network "private_network", ip: "192.168.20.1", virtualbox__intnet: "intnet2"
    dhcp.vm.provision "shell", inline: <<-SHELL
      sudo apt-get install -y isc-dhcp-server
      sudo systemctl restart isc-dhcp-server
    SHELL
  end

  # SWITCH1
  config.vm.define "switch-1" do |sw1|
    sw1.vm.hostname = "switch-1"
    sw1.vm.network "private_network", ip: "192.168.10.2", virtualbox__intnet: "intnet1"
  end

  # SWITCH2
  config.vm.define "switch-2" do |sw2|
    sw2.vm.hostname = "switch-2"
    sw2.vm.network "private_network", ip: "192.168.20.2", virtualbox__intnet: "intnet2"
  end

  # CLIENT1
  config.vm.define "client-1" do |cl1|
    cl1.vm.hostname = "client-1"
    cl1.vm.network "private_network", ip: "192.168.10.3", virtualbox__intnet: "intnet1"
  end

  # CLIENT2
  config.vm.define "client-2" do |cl2|
    cl2.vm.hostname = "client-2"
    cl2.vm.network "private_network", ip: "192.168.20.3", virtualbox__intnet: "intnet2"
  end
end