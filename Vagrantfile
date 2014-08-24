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
          v.customize ["modifyvm", :id, "--name", "web", "--memory", "768"]
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
          v.customize ["modifyvm", :id, "--name", "db", "--memory", "1024"]
    end
    db.vm.box = "base"
    db.vm.hostname = "db"
    db.vm.network :private_network, ip: "11.11.1.11"
    db.vm.network :forwarded_port, guest: 3306, host: 3306 
  end

  config.vm.define :db2 do |db2|
    db2.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--name", "db2", "--memory", "768"]
    end
    db2.vm.box = "base"
    db2.vm.hostname = "db2"
    db2.vm.network :private_network, ip: "11.11.1.12"
  end

  config.vm.define :ripple do |ripple|
    ripple.vm.provider "virtualbox" do |v|
          v.customize ["modifyvm", :id, "--name", "ripple", "--memory", "1024"]
    end
    ripple.vm.box = "ubuntu"
    ripple.vm.hostname = "ripple"
    ripple.vm.network :private_network, ip: "11.11.1.20"

    ripple.vm.network :forwarded_port, guest: 4001, host: 4001
    ripple.vm.network :forwarded_port, guest: 4002, host: 4002
    ripple.vm.network :forwarded_port, guest: 4003, host: 4003
  end


end
