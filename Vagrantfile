# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "minimal/centos7"

  config.vm.define "node01" do |centos|
     centos.vm.hostname = "node01.centos"
     centos.vm.synced_folder ".", "/vagrant", disabled: true
     centos.vm.network :forwarded_port, id: "ssh", guest: 22, host: 2222
     centos.vm.network "private_network", ip: "192.168.33.101"#, virtualbox__intnet: "intra"
     config.vm.provision "shell", run: "always", inline: "systemctl restart network.service"
  end

  #config.vm.define "node02" do |centos|
  #   centos.vm.hostname = "node02.centos"
  #   centos.vm.synced_folder ".", "/vagrant", disabled: true
  #   centos.vm.network :forwarded_port, id: "ssh", guest: 22, host: 2223
  #   centos.vm.network "private_network", ip: "192.168.33.102"#, virtualbox__intnet: "intra"
  #   config.vm.provision "shell", run: "always", inline: "systemctl restart network.service"
  #end
end
