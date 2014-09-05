# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise64"

  config.vm.network :private_network, ip: "192.168.57.10"
  config.vm.hostname = "foreman.cloudcomplab.ch"
  config.vm.synced_folder "src/", "/tmp/files-to-go"

  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.name = "foreman1.5"
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provider "vmware_fusion" do |vw|
    vw.gui = false
    vw.vmx['memsize'] = '1024'
    vw.vmx['vhv.enable'] = "TRUE"
    vw.vmx['mks.enable3d'] = "FALSE"
  end

  config.vm.provision :shell, :path => "src/script.sh"
end
