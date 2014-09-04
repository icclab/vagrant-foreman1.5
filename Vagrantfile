# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu1204"

  config.vm.network :private_network, ip: "192.168.57.10"
  config.vm.hostname = "foreman.cloudcomplab.ch"
  config.vm.synced_folder "src/", "/tmp/files-to-go"

  config.vm.provider :virtualbox do |vb|
    vb.gui = false
    vb.name = "foreman1.5"
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision     :shell, :path => "src/script.sh"
end
