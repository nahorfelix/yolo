# -*- mode: ruby -*-
# vi: set ft=ruby :


config.vm.provision "ansible" do |ansible|
  ansible.playbook = "playbook.yml"
config.vm.network "forwarded_port", guest: 3000, host: 3000  
  end
end
