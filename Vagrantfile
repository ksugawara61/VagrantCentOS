# -*- mode: ruby -*-
# vi: set ft=ruby :

# constraint variables
VAGRANT_API_VERSION = "2"

# setting variables for instance
$node_ip = "172.16.1.170"
$node_hostname = "node001"
$node_vm_memory = 2048
$node_vm_cpus = 2

Vagrant.configure(VAGRANT_API_VERSION) do |config|

  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  config.vm.box = "centos/7"

  config.vm.hostname = $node_hostname
  config.vm.network "forwarded_port", guest: 80,  host: 80
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "private_network", ip: $node_ip

  config.vm.synced_folder "./dev", "/home/vagrant/dev", owner: "vagrant", group: "vagrant"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "setup.yml"
  end

  config.vm.provider :virtualbox do |vb|
    vb.memory = $node_vm_memory
    vb.cpus = $node_vm_cpus
  end

end
