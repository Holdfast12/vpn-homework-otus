# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.vm.box = "almalinux/8"
  config.vm.box_check_update = false
  #config.vm.synced_folder "/home/michael/dnf_cache", "/var/cache/dnf/"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end
  config.vm.define "server" do |server|
  server.vm.hostname = "server.loc"
  server.vm.network "private_network", ip: "192.168.56.10", adapter: 2
  end
  config.vm.define "client" do |client|
  client.vm.hostname = "client.loc"
  client.vm.network "private_network", ip: "192.168.56.20", adapter: 2
  end
  end