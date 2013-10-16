Vagrant.configure("2") do |config|

	config.vm.box = "centos64tcmug"
	config.vm.network :private_network, ip: "33.33.33.123"

	config.vm.provider :virtualbox do |vb|
		vb.customize ["modifyvm", :id, "--memory", "4000", "--ioapic", "on", "--rtcuseutc", "on", "--cpus", "2"]
		vb.name = "ansible"
	end

	config.vm.provision "ansible" do |ansible|
		ansible.verbose = "v"
		ansible.playbook = "ansible/site.yml"
		ansible.inventory_path = "ansible/inventory"
	end

end
