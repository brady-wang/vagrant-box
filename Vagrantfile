Vagrant.configure("2") do |config|
 
  config.vm.box = "lnmp"
 
  config.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh", disabled: "true"
  config.vm.network "forwarded_port", guest: 22, host: 5510
  #config.vm.network "private_network", ip: "192.168.44.10"
  config.vm.network "public_network", ip: "10.10.10.55"
  config.vm.synced_folder "d:/www", "/phpwww"
 
  config.vm.provider "virtualbox" do |v|
  v.memory = 4096
  v.cpus = 4
  end
 
end