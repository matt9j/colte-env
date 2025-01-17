# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define :colte, primary: true do |colte|
    colte.vm.box = "debian/bullseye64"
    colte.vm.hostname = "colte"
    colte.vm.network "forwarded_port", guest: 3000, host: 3000
    colte.vm.network "forwarded_port", guest: 7998, host: 7998
    colte.vm.network "forwarded_port", guest: 7999, host: 7999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.56.99"
    # colte.vm.network "public_network", ip: "169.254.1.16"

    colte.vm.synced_folder '.', '/vagrant', disabled: true
    colte.vm.synced_folder "./colte/" , "/home/vagrant/colte", type: "nfs", nfs_version: 4, nfs_udp: false
    colte.vm.synced_folder "./open5gs/" , "/home/vagrant/open5gs", type: "nfs", nfs_version: 4, nfs_udp: false
    colte.vm.synced_folder "./haulage/" , "/home/vagrant/haulage", type: "nfs", nfs_version: 4, nfs_udp: false
    colte.vm.synced_folder "./colte-release/" , "/home/vagrant/colte-release", type: "nfs", nfs_version: 4, nfs_udp: false
    colte.vm.synced_folder "./commgestion-web/" , "/home/vagrant/commgestion-web", type: "nfs", nfs_version: 4, nfs_udp: false
    colte.vm.synced_folder "./moshell/" , "/home/vagrant/moshell", type: "nfs", nfs_version: 4, nfs_udp: false

    colte.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--memory", "8192"]
      vb.customize ["modifyvm", :id, "--cpus", "6"]

    end

    colte.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.host_key_checking = false
      ansible.playbook = "ansible/colte.yml"
      ansible.raw_arguments = ['--timeout=20']
      ansible.verbose = 'v'
    end

  end


  config.vm.define :colteBuster, primary: true do |colte|
    colte.vm.box = "debian/buster64"
    colte.vm.hostname = "colteBuster"
    colte.vm.network "forwarded_port", guest: 3000, host: 3000
    colte.vm.network "forwarded_port", guest: 7998, host: 7998
    colte.vm.network "forwarded_port", guest: 7999, host: 7999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.56.2"
    # colte.vm.network "public_network", ip: "169.254.1.16"

    colte.vm.synced_folder '.', '/vagrant', disabled: true
    colte.vm.synced_folder "./colte/" , "/home/vagrant/colte", type: "nfs", nfs_version: 4
    colte.vm.synced_folder "./open5gs/" , "/home/vagrant/open5gs", type: "nfs", nfs_version: 4
    colte.vm.synced_folder "./haulage/" , "/home/vagrant/haulage", type: "nfs", nfs_version: 4
    colte.vm.synced_folder "./colte-release/" , "/home/vagrant/colte-release", type: "nfs", nfs_version: 4
    colte.vm.synced_folder "./commgestion-web/" , "/home/vagrant/commgestion-web", type: "nfs", nfs_version: 4
    colte.vm.synced_folder "./moshell/" , "/home/vagrant/moshell", type: "nfs", nfs_version: 4

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


  config.vm.define :colteBionic, autostart: false do |colte|
    colte.vm.box = "ubuntu/bionic64"
    colte.vm.hostname = "colteU"
    colte.vm.network "forwarded_port", guest: 3000, host: 6000
    colte.vm.network "forwarded_port", guest: 7998, host: 6998
    colte.vm.network "forwarded_port", guest: 7999, host: 6999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.56.3"

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

  config.vm.define :colteFocal, autostart: false do |colte|
    colte.vm.box = "ubuntu/focal64"
    colte.vm.hostname = "colteU2"
    colte.vm.network "forwarded_port", guest: 3000, host: 5000
    colte.vm.network "forwarded_port", guest: 7998, host: 5998
    colte.vm.network "forwarded_port", guest: 7999, host: 5999
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    colte.vm.network "private_network", ip: "192.168.56.4"

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
