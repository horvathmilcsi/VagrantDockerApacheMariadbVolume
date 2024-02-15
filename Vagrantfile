# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

  config.vm.define "managed_1_r9" do |managed_1_r9|
    managed_1_r9.vm.box = "bento/rockylinux-9"
    managed_1_r9.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end
    managed_1_r9.vm.network "private_network", ip: "192.168.56.221"
    managed_1_r9.vm.synced_folder "./Megosztas", "/Megosztas"
    managed_1_r9.vm.provision "shell", path: "provisioners/docker.sh"
    managed_1_r9.vm.provision "shell", path: "provisioners/compose.sh"
    managed_1_r9.vm.provision "shell", inline: "hostnamectl set-hostname rocky9-docker"
  end
end
