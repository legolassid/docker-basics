
Vagrant.configure("2") do |config|
  config.vm.define "ubuntu", primary: true do |machine|
      machine.vm.box = "ubuntu/trusty64"
      machine.vm.hostname = "ubuntu.dockerbasics.org"
      machine.vm.network :private_network, ip: "192.168.33.10"
  end

  config.vm.define "centos" do |machine|
      machine.vm.box = "chef/centos-7.0"
      machine.vm.hostname = "centos.dockerbasics.org"
      machine.vm.network :private_network, ip: "192.168.33.11"
  end

end
