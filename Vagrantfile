Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |v|
	v.memory = 2056
	v.cpus = 2
  end
  config.vm.define "master" do |master|
	master.vm.network "private_network", ip: "192.168.50.10",
    virtualbox__intnet: "net1"
	master.vm.hostname = "master"

  end
  config.vm.define "slave" do |slave|
	slave.vm.network "private_network", ip: "192.168.50.11",
    virtualbox__intnet: "net1"
	slave.vm.hostname = "slave"
	config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbook.yml"
      end
end
end
