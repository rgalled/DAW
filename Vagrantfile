# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "master" do |master|
    master.vm.box = "debian/bullseye64"
    master.vm.network "forwarded_port", guest: 80, host: 8090
    master.vm.network :private_network, ip: "192.168.57.10"
    master.vm.provision "shell", inline: <<-COMAND
     apt-get update 
     apt-get istall -y nginx python3-flask
     cp /vagrant/nfinx.conf /etc/nginx
     systemctl reload nginx
    COMAND
  end

end
