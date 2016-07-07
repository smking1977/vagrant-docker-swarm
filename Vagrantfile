# -*- mode: ruby -*-
# vi: set ft=ruby :

CAERUS_SOURCE_CODE_PATH = "/Users/stevek/projects/caerus/caerus-football/"
$script = <<-SCRIPT
      sudo groupadd docker
      sudo usermod -a -G docker vagrant
      sudo yum update -y
      sudo yum install -y wget git
      curl -fsSL https://test.docker.com/ | sh
    SCRIPT

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  
   #
  # Set-up master
  #
  config.vm.define "master" do |master|

   master.vm.box = "centos/7"

    #using a specific IP.
    master.vm.network "private_network", ip: "192.168.99.100"

    master.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
       vb.cpus = "1"
     end
    

    ###  config docker 
    master.vm.provision "shell", inline: $script


  end


  #
  # Set-up worker1
  #
  config.vm.define "worker1" do |worker1|

   worker1.vm.box = "centos/7"

    #using a specific IP.
    worker1.vm.network "private_network", ip: "192.168.99.101"

    worker1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
       vb.cpus = "1"
     end
    

   ###  config docker 
    worker1.vm.provision "shell", inline: $script
  end

  #
  # Set-up worker2
  #
  config.vm.define "worker2" do |worker2|

   worker2.vm.box = "centos/7"

    #using a specific IP.
    worker2.vm.network "private_network", ip: "192.168.99.102"

    worker2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
       vb.cpus = "1"
     end
    

    ###  config docker 
    worker2.vm.provision "shell", inline: $script
  end






end
