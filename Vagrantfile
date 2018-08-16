Vagrant.configure("2") do |config|
  config.vm.box = "debian/jessie64"

  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |v|
    v.name = "raspberry"
    v.memory = 1024
    v.cpus = 2
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.hostname = "raspberry"
  config.vm.network :private_network, ip: "192.168.33.33"

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "testing/inventory"
    ansible.limit = "all"
    #ansible.verbose = "vvv"
  end
end
