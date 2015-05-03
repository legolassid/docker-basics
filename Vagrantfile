
Vagrant.configure("2") do |config|
  config.vm.define "ubuntu", primary: true do |machine|
      machine.vm.box = "ubuntu/trusty64"
      machine.vm.hostname = "ubuntu.dockerbasics.org"
      machine.vm.network :private_network, ip: "192.168.33.20"
      machine.vm.synced_folder "./", "/vagrant", disabled: true
      machine.vm.synced_folder "docker-config/", "/vagrant/docker-config"

      machine.vm.provision "bootstrap", type: "ansible"  do |ansible|
        ansible.inventory_path = "hosts"
        ansible.playbook = "provisioning/ubuntu.yml"
        ansible.sudo = true
      end
  end

  config.vm.define "centos" do |machine|
      machine.vm.box = "chef/centos-7.0"
      machine.vm.hostname = "centos.dockerbasics.org"
      machine.vm.network :private_network, ip: "192.168.33.21"
      machine.vm.provision "bootstrap", type: "ansible"  do |ansible|
        ansible.inventory_path = "hosts"
        ansible.playbook = "provisioning/centos.yml"
        ansible.sudo = true
      end
  end

end
