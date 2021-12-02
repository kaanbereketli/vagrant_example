# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "web1" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = "webserver1.test"
    #web.vm.network :private_network, ip: "172.16.20.5"
    web.vm.network :public_network, ip: "192.168.1.160"
    web.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
    SHELL
  end

  config.vm.define "web2" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = "webserver2.test"
    #web.vm.network :private_network, ip: "172.16.20.6"
    web.vm.network :public_network, ip: "192.168.1.161"
    web.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
    SHELL
  end

  config.vm.define "db" do |db|
    db.vm.box = "centos/7"
    db.vm.hostname = "database.test"
    #db.vm.network :private_network, ip: "172.16.20.55"
    db.vm.network :public_network, ip: "192.168.1.162"
    db.vm.provision "shell", inline: <<-SHELL
      yum update
      yum install sqlite -y
    SHELL
  end

  config.vm.define "slave" do |slave|
    slave.vm.box = "centos/7"
    slave.vm.hostname = "slave.test"
    #slave.vm.network :private_network, ip: "172.16.20.55"
    slave.vm.network :public_network, ip: "192.168.1.163"
    slave.vm.provision "shell", inline: <<-SHELL
      yum update
    SHELL
  end
end
