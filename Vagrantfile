# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

$script = <<SCRIPT
  echo I am provisioning...
  sudo yum install vim
SCRIPT

Vagrant.configure("2") do |config|
  

  config.vm.define "mongo1" do |mongo1|
    mongo1.vm.box = "centos/7"
    mongo1.vm.host_name = 'mongoddb-01'
    mongo1.vm.network "forwarded_port", guest: 80, host: 8010
    mongo1.vm.network "forwarded_port", guest: 22, host: 2224
    mongo1.vm.network "private_network", ip: "10.10.10.11"
    
    mongo1.vm.provision "shell", inline: $script # Just install it

    # Increase memory for Parallels Desktop
    mongo1.vm.provider "parallels" do |p, o|
      p.memory = "1024"
    end

    # Increase memory for Virtualbox
    mongo1.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
    end
  end

  config.vm.define "mongo2" do |mongo2|
    mongo2.vm.box = "centos/7"
    mongo2.vm.host_name = 'mongoddb-02'
    mongo2.vm.network "forwarded_port", guest: 80, host: 8011
    mongo2.vm.network "forwarded_port", guest: 22, host: 2225
    mongo2.vm.network "private_network", ip: "10.10.10.12"
    
    mongo2.vm.provision "docker" # Just install it

    # Increase memory for Parallels Desktop
    mongo2.vm.provider "parallels" do |p, o|
      p.memory = "1024"
    end

    # Increase memory for Virtualbox
    mongo2.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
    end
  end

  config.vm.define "mongo3" do |mongo3|
    mongo3.vm.box = "centos/7"
    mongo3.vm.host_name = 'mongoddb-03'
    mongo3.vm.network "forwarded_port", guest: 80, host: 8012
    mongo3.vm.network "forwarded_port", guest: 22, host: 2226
    mongo3.vm.network "private_network", ip: "10.10.10.13"
    
    mongo3.vm.provision "docker" # Just install it

    # Increase memory for Parallels Desktop
    mongo3.vm.provider "parallels" do |p, o|
      p.memory = "1024"
    end

    # Increase memory for Virtualbox
    mongo3.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
    end
  end

end