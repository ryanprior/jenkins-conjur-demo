Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |vbox|
    vbox.name = "jenkins-plugin-demo"
    vbox.memory = 1024*6
    vbox.cpus = 4
  end
  config.vm.network "private_network", type: "dhcp"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
  config.vm.provision "prep", type: "ansible_local" do |ansible|
    ansible.install = true
    ansible.become = true
    ansible.provisioning_path = "/vagrant/ansible"
    ansible.inventory_path = "inventory.yml"
    ansible.playbook = "site.yml"
  end
end
