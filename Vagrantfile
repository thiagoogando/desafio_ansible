Vagrant.configure("2") do |config|
 config.vm.provider "virtualbox" do |vb|
  vb.name = "host2"
  vb.memory = 1024
  vb.cpus = 1
 end

  config.vm.box = "hashicorp/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8091
  config.vm.network "public_network"
  config.vm.provision "shell", path: "script.sh"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/main.yml"
  end
end

