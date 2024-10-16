Vagrant.configure("2") do |config|
  config.vm.define "venus" do |venus|
    venus.vm.box = "debian/bullseye64"
    venus.vm.hostname = "venus.sistema.test"
    venus.vm.network :private_network, ip: "192.168.57.102"
    venus.vm.provision "shell", inline: <<-COMAND
     apt-get update 
    COMAND
  end

  config.vm.define "tierra" do |tierra|
    tierra.vm.box = "debian/bullseye64"
    tierra.vm.hostname = "tierra.sistema.test"
    tierra.vm.network :private_network, ip: "192.168.57.103"
    tierra.vm.provision "shell", inline: <<-COMAND
     apt-get update 
    COMAND
  end
end
