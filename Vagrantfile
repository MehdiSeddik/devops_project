# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.ssh.insert_key = false 
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/bionic64"
    web.vm.hostname = "web"
    web.vm.network :forwarded_port, guest: 80, host: 45372, ip: "192.168.33.13"
    web.vm.provision "ansible" do |ansible|
      ansible.playbook = "./ansible-web/playbook-web.yml"
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/bionic64"
    db.vm.hostname = "db"
    db.vm.network :forwarded_port, guest: 3306, host: 3306, ip: "192.168.33.14"
    db.vm.provision "ansible" do |ansible|
      ansible.playbook = "./ansible-db/playbook-db.yml"
    end
  end
end