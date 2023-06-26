Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.provider "virtualbox" do |v|
   v.name = "Projeto-Vagrant-Ansible-Zabbix-Zabbix"
  end


  config.vm.network "public_network", ip: "192.168.1.67"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.synced_folder "ansible/", "/ansible"
  config.vm.provision "shell", inline: <<-SHELL 
  apt update -y 
  apt install ansible -y
  hostnamectl set-hostname Projeto05
  ansible-playbook --connection=local /ansible/playbook.yml
  SHELL

  

  
end
