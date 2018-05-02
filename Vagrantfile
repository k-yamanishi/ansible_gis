# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.box_url = "https://app.vagrantup.com/centos/boxes/7"
  config.proxy.http = ""
  config.proxy.https = ""
  config.proxy.no_proxy = "localhost,127.0.0.1" 
  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = 1024
  end

  config.vm.define "gis" do |server|
    server.vm.hostname = "gis"
    server.vm.network "forwarded_port", guest: 80, host: 10080
    server.vm.network "forwarded_port", guest: 5432, host: 15432
    server.vm.network "forwarded_port", guest: 4848, host: 14848
    server.vm.network "forwarded_port", guest: 8080, host: 18080
  end
end
