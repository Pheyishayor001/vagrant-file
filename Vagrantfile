# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.ssh.insert_key = false

    # Web Server
    config.vm.define "website-server" do |web|
        web.vm.hostname = "website-server"
        web.vm.box = "bento/ubuntu-18.04"
        web.vm.network "private_network", ip: "192.168.56.154"

        # Increase memory and CPU for the web server
        web.vm.provider :virtualbox do |vb|
            vb.customize ["modifyvm", :id, "--memory", "4096"]  # Set memory to 4 GB
            vb.customize ["modifyvm", :id, "--cpus", "2"]       # Set CPUs to 2 cores
        end
    end


    # Database Server
    config.vm.define "database-server" do |db|
        db.vm.hostname = "database-server"
        db.vm.box = "bento/ubuntu-18.04"
        db.vm.network "private_network", ip: "192.168.56.155"

        # Optionally, you can also increase the resources for the database server
        db.vm.provider :virtualbox do |vb|
             vb.customize ["modifyvm", :id, "--memory", "1024"]
             vb.customize ["modifyvm", :id, "--cpus", "1"]
         end
    end
end
