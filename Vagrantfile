# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define :colte do |colte|
    colte.vm.box = "debian/contrib-buster64"
    colte.vm.hostname = "colte"
    colte.vm.network "forwarded_port", guest: 3000, host: 3000
    colte.vm.network "forwarded_port", guest: 7998, host: 7998
    colte.vm.network "forwarded_port", guest: 7999, host: 7999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.40.200"

    colte.vm.synced_folder "./colte/" , "/home/vagrant/colte", type: "virtualbox"
    colte.vm.synced_folder "./open5gs/" , "/home/vagrant/open5gs", type: "virtualbox"
    colte.vm.synced_folder "./haulage/" , "/home/vagrant/haulage", type: "virtualbox"
    colte.vm.synced_folder "./colte-release/" , "/home/vagrant/colte-release", type: "virtualbox"

    colte.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "4096"]
      vb.customize ["modifyvm", :id, "--cpus", "3"]

    end

    colte.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.host_key_checking = false
      ansible.playbook = "ansible/colte.yml"
      ansible.raw_arguments = ['--timeout=20']
      ansible.verbose = 'v'
    end

  end


  config.vm.define :colteU do |colte|
    colte.vm.box = "ubuntu/bionic64"
    colte.vm.hostname = "colteU"
    colte.vm.network "forwarded_port", guest: 3000, host: 6000
    colte.vm.network "forwarded_port", guest: 7998, host: 6998
    colte.vm.network "forwarded_port", guest: 7999, host: 6999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.41.200"

    colte.vm.synced_folder "./colte/" , "/home/vagrant/colte", type: "virtualbox"
    colte.vm.synced_folder "./open5gs/" , "/home/vagrant/open5gs", type: "virtualbox"
    colte.vm.synced_folder "./haulage/" , "/home/vagrant/haulage", type: "virtualbox"
    colte.vm.synced_folder "./colte-release/" , "/home/vagrant/colte-release", type: "virtualbox"

    colte.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "4096"]
      vb.customize ["modifyvm", :id, "--cpus", "3"]

    end

    colte.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.host_key_checking = false
      ansible.playbook = "ansible/colte.yml"
      ansible.raw_arguments = ['--timeout=20']
      ansible.verbose = 'v'
    end

  end

  config.vm.define :colteS do |colte|
    colte.vm.box = "debian/contrib-stretch64"
    colte.vm.hostname = "colteS"
    colte.vm.network "forwarded_port", guest: 3000, host: 9000
    colte.vm.network "forwarded_port", guest: 7998, host: 9998
    colte.vm.network "forwarded_port", guest: 7999, host: 9999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.42.200"

    colte.vm.synced_folder "./colte/" , "/home/vagrant/colte", type: "virtualbox"
    colte.vm.synced_folder "./open5gs/" , "/home/vagrant/open5gs", type: "virtualbox"
    colte.vm.synced_folder "./haulage/" , "/home/vagrant/haulage", type: "virtualbox"
    colte.vm.synced_folder "./colte-release/" , "/home/vagrant/colte-release", type: "virtualbox"

    colte.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "4096"]
      vb.customize ["modifyvm", :id, "--cpus", "3"]

    end

    colte.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.host_key_checking = false
      ansible.playbook = "ansible/colte.yml"
      ansible.raw_arguments = ['--timeout=20']
      ansible.verbose = 'v'
    end

  end


end