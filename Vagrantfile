Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  config.vm.network :forwarded_port, guest: 80, host: 8081
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network :public_network

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/hosts"
    ansible.limit = 'all'
  end
end
