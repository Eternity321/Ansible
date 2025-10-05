  # -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  config.vm.provision "file", source: "files/vagrant_test.pub", destination: "/home/vagrant/.ssh/"

  config.vm.define "controlnode" do |controlnode|
    controlnode.vm.box = "ubuntu/focal64"
    controlnode.vm.hostname = "controlnode"
    controlnode.vm.network "private_network", ip: "192.168.51.10"
    controlnode.vm.synced_folder "./ansible","/home/vagrant/ansible"
    controlnode.vm.provision "file", source: "files/vagrant_test", destination: "/home/vagrant/.ssh/"
    controlnode.vm.provision "shell", inline: <<-SHELL
      sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config
      service ssh restart
      curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
      sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
      sudo apt update && sudo apt --assume-yes install ansible docker-ce docker-compose sshpass
      chmod 600 /home/vagrant/.ssh/vagrant_test
      chmod 644 /home/vagrant/.ssh/vagrant_test.pub
    SHELL
  end

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.define "server" do |server|
    server.vm.box = "ubuntu/focal64"
    server.vm.hostname = "ubuntu"
    server.vm.network "private_network", ip: "192.168.51.4"
    config.vm.provision "file", source: "files/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
    server.vm.provision "shell", inline: <<-SHELL
      chmod 600 /home/vagrant/.ssh/vagrant_test.pub
      cat /home/vagrant/.ssh/vagrant_test.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

  config.vm.define "server_no_python" do |server_no_python|
    server_no_python.vm.box = "ubuntu/focal64"
    server_no_python.vm.hostname = "no-python"
    server_no_python.vm.network "private_network", ip: "192.168.51.2"
    config.vm.provision "file", source: "files/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
    server_no_python.vm.provision "shell", inline: <<-SHELL
      chmod 600 /home/vagrant/.ssh/vagrant_test.pub
      cat /home/vagrant/.ssh/vagrant_test.pub >> /home/vagrant/.ssh/authorized_keys
      sudo apt -y remove python3 && sudo apt -y autoremove
    SHELL
  end

  config.vm.define "server_centos" do |server_centos|
    server_centos.vm.box = "bento/centos-7.5"
    server_centos.vm.hostname = "centos"
    server_centos.vm.network "private_network", ip: "192.168.51.3"
    config.vm.provision "file", source: "files/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
    server_centos.vm.provision "shell", inline: <<-SHELL
      chmod 600 /home/vagrant/.ssh/vagrant_test.pub
      cat /home/vagrant/.ssh/vagrant_test.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end

  config.vm.define "server_centos_python" do |centos_python|
    centos_python.vm.box = "bento/centos-7.5"
    centos_python.vm.hostname = "server-centos-python"
    centos_python.vm.network "private_network", ip: "192.168.51.5"
    config.vm.provision "file", source: "files/vagrant_test.pub", destination: "/home/vagrant/.ssh/"
    centos_python.vm.provision "shell", inline: <<-SHELL
      chmod 600 /home/vagrant/.ssh/vagrant_test.pub
      cat /home/vagrant/.ssh/vagrant_test.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
end
