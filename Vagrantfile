Vagrant.configure("2") do |config|
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bullseye64"
    venus.vm.hostname = "venus.sistema.test"
    venus.vm.network :private_network, ip: "192.168.57.102"
    venus.vm.provision "shell", inline: <<-COMAND
     apt-get update 
     apt-get install -y bind9
     cp /vagrant/venus/named.conf.options /etc/bind/named.conf.options 
     cp /vagrant/venus/named.conf.local /etc/bind/named.conf.local 
     systemctl restart bind9
    COMAND
  end

  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "debian/bullseye64"
    tierra.vm.hostname = "tierra.sistema.test"
    tierra.vm.network :private_network, ip: "192.168.57.103"
    tierra.vm.provision "shell", inline: <<-COMAND
     apt-get update
     apt-get install -y bind9
     cp /vagrant/tierra/named.conf.options /etc/bind/named.conf.options 
     cp /vagrant/tierra/named.conf.local /etc/bind/named.conf.local 
     cp /vagrant/tierra/db.tierra.sistema.test /var/lib/bind/db.tierra.sistema.test 
     systemctl restart bind9
    COMAND
  end
end
