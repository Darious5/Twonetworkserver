# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2 
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
  SHELL

  # DHCP SERVER
  config.vm.define "DHCP" do |dhcp|
    dhcp.vm.hostname = "dhcp"
    dhcp.vm.network "private_network", ip: "192.168.56.1"
    dhcp.vm.network "private_network", ip: "192.168.57.1", virtualbox__intnet: "intnet1"
    dhcp.vm.network "private_network", ip: "192.168.58.1", virtualbox__intnet: "intnet2"
    dhcp.vm.provision "shell", inline: <<-SHELL
      sudo apt-get install -y isc-dhcp-server
      cp /vagrant/configs/dhcpd.conf /etc/dhcp/dhcpd.conf
      cp /vagrant/configs/isc-dhcp-server /etc/default/isc-dhcp-server
      sudo systemctl restart isc-dhcp-server
    SHELL
  end

  # SWITCH1
  config.vm.define "switch-1" do |sw1|
    sw1.vm.hostname = "switch-1"
    sw1.vm.network "private_network", type:"dhcp",mac:"001AA0E8C239", virtualbox__intnet: "intnet1"
  end

  # SWITCH2
  config.vm.define "switch-2" do |sw2|
    sw2.vm.hostname = "switch-2"
    sw2.vm.network "private_network", type:"dhcp",mac:"001AA0E6094A", virtualbox__intnet: "intnet2"
  end

  # CLIENT1
  config.vm.define "client-1" do |cl1|
    cl1.vm.hostname = "client-1"
    cl1.vm.network "private_network", type:"dhcp",mac:"001AA0E5F5D2", virtualbox__intnet: "intnet1"
  end

  # CLIENT2
  config.vm.define "client-2" do |cl2|
    cl2.vm.hostname = "client-2"
    cl2.vm.network "private_network", type:"dhcp",mac:"001AA0E906CF", virtualbox__intnet: "intnet2"
  end
end
