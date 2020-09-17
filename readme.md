
Vagrantfile 内容 

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



启动过程 :

C:\Users\Administrator>e:

E:\>cd vbox

E:\vbox>cd lnmp

E:\vbox\lnmp>vagrant box add lnmp centos7.8.box
==> box: Box file was not detected as metadata. Adding it directly...
==> box: Adding box 'lnmp' (v0) for provider:
    box: Unpacking necessary files from: file://E:/vbox/lnmp/centos7.8.box
    box:
==> box: Successfully added box 'lnmp' (v0) for 'virtualbox'!


E:\vbox\lnmp>vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Vagrant has detected a configuration issue which exposes a
==> default: vulnerability with the installed version of VirtualBox. The
==> default: current guest is configured to use an E1000 NIC type for a
==> default: network adapter which is vulnerable in this version of VirtualBox.
==> default: Ensure the guest is trusted to use this configuration or update
==> default: the NIC type using one of the methods below:
==> default:
==> default:   https://www.vagrantup.com/docs/virtualbox/configuration.html#default-nic-type
==> default:   https://www.vagrantup.com/docs/virtualbox/networking.html#virtualbox-nic-type
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
    default: Adapter 2: bridged
==> default: Forwarding ports...
    default: 22 (guest) => 5510 (host) (adapter 1)
==> default: Running 'pre-boot' VM customizations...
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:5510
    default: SSH username: vagrant
    default: SSH auth method: private key
    default: Warning: Connection aborted. Retrying...
    default: Warning: Connection reset. Retrying...
    default: Warning: Remote connection disconnect. Retrying...
    default: Warning: Connection aborted. Retrying...
    default: Warning: Connection reset. Retrying...
    default: Warning: Connection aborted. Retrying...
    default: Warning: Remote connection disconnect. Retrying...
    default: Warning: Connection reset. Retrying...
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: Configuring and enabling network interfaces...
==> default: Mounting shared folders...
    default: /phpwww => D:/www
    default: /vagrant => E:/vbox/lnmp

E:\vbox\lnmp>
E:\vbox\lnmp>

