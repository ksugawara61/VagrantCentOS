# -*- mode: ruby -*-
# vi: set ft=ruby :

# constraint variables
VAGRANT_API_VERSION = "2"

# setting variables for instance
$vm_memory = 1024
$vm_cpus = 1

Vagrant.configure("2") do |config|

  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  config.vm.box = "centos/7"

  config.vm.network "forwarded_port", guest: 80,  host: 80
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "setup.yml"
  end

  config.vm.provider :virtualbox do |vb|
    vb.memory = $vm_memory
    vb.cpus = $vm_cpus
  end

end
