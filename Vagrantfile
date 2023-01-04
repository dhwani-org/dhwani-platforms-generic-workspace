Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = "box.demo.dhwani.org"

  config.vm.provider :virtualbox do |v|
    v.gui = true
    v.memory = 4096
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # Set the static IP for the vagrant box
  # config.vm.network "private_network", ip: "192.168.56.5

  # Forward the ports from the guest VM to the local host machine
  # Forward more ports, as needed
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 6111, host: 6111
  config.vm.network "forwarded_port", guest: 6112, host: 6112 

  # Currently "ubuntu/bionic64" on VirtualBox requires `type: "virtualbox"`
  # to make synced folder works.
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
end