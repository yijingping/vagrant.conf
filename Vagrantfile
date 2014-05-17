# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define :puppetserver do |puppetserver|
    puppetserver.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--name", "puppetserver", "--memory", "256"]
    end
    puppetserver.vm.box = "base"
    puppetserver.vm.hostname = "puppetserver"
    puppetserver.vm.network :private_network, ip: "11.11.1.9"
  end

  config.vm.define :web do |web|
    web.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--name", "web", "--memory", "512"]
    end
    web.vm.box = "base"
    web.vm.hostname = "web"
    web.vm.network :private_network, ip: "11.11.1.10"
    web.vm.network :forwarded_port, guest: 80, host: 8080
    web.vm.network :forwarded_port, guest: 443, host: 8443

    web.vm.network :forwarded_port, guest: 8001, host: 8001
    web.vm.network :forwarded_port, guest: 8002, host: 8002
    web.vm.network :forwarded_port, guest: 8003, host: 8003
    web.vm.network :forwarded_port, guest: 8004, host: 8004
    web.vm.network :forwarded_port, guest: 8005, host: 8005
  end

  config.vm.define :db do |db|
    db.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--name", "db", "--memory", "512"]
    end
    db.vm.box = "base"
    db.vm.hostname = "db"
    db.vm.network :private_network, ip: "11.11.1.11"
  end

end
