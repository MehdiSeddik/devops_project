# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.ssh.insert_key = false 
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/bionic64"
    web.vm.hostname = "web"
    config.vm.network "forwarded_port", guest: 80, host: 9090
    web.vm.provision "ansible" do |ansible|
      ansible.playbook = "./ansible-web/playbook-web.yml"
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/bionic64"
    db.vm.hostname = "db"

  end
end

