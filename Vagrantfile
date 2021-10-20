Vagrant.configure("2") do |config|
  config.vm.box = "centos/8"
  config.vm.network "private_network", ip: "192.168.10.20"
  config.vm.hostname = "researchdata.test"
  #
  # Run Ansible from the Vagrant Host
  #
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
