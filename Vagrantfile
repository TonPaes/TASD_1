# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.define "vm1" do |vms|
    vms.vm.network "public_network"
  	vms.vm.hostname = "monitoringHost"
  	vms.vm.provider "virtualbox" do |vb|
      		vb.memory = "4096"
    	  	vb.name = "vm1"
  	end
    vms.vm.provision "shell", inline: <<-SHELL
    	echo "Installing Docker"
  	 	sudo apt update
	 		sudo apt upgrade
	 		sudo apt -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
	 		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
	 		sudo apt-key fingerprint 0EBFCD88
	 		sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
	 		sudo apt update
	 		sudo apt -y install docker-ce docker-ce-cli containerd.io
	 		sudo usermod -aG docker $USER
	 		sudo systemctl start docker
   	 	git clone https://github.com/dcomp-leris/slice-enablers.git
			sudo apt-get install python3
			sudo apt install python3-pip
			pip3 install flask
			pip install tinydb
			SHELL
	end
	config.vm.box = "ubuntu/bionic64"
  config.vm.define "vm2" do |vms|
    vms.vm.network "public_network"
  	vms.vm.hostname = "monitoringHost"
  	vms.vm.provider "virtualbox" do |vb|
      		vb.memory = "2048"
    	  	vb.name = "vm2"
  	end
    vms.vm.provision "shell", inline: <<-SHELL
    	echo "Installing Docker"
  	 	sudo apt update
	 		sudo apt upgrade
	 		sudo apt -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
	 		curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
	 		sudo apt-key fingerprint 0EBFCD88
	 		sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
	 		sudo apt update
	 		sudo apt -y install docker-ce docker-ce-cli containerd.io
	 		sudo usermod -aG docker $USER
	 		sudo systemctl start docker
   	 	git clone https://github.com/dcomp-leris/slice-enablers.git
			sudo apt-get install python3
			sudo apt install python3-pip
			pip3 install flask
			SHELL
	end
end