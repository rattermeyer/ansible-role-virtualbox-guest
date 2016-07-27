# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
  config.vm.provision "shell", inline: <<-SHELL
  # check if ansible is already installed by using hash function
    if hash ansible-playbook 2> /dev/null; then
          echo "ansible already installed"
    else
          echo "installing ansible"
          grep -q -F 'deb' /etc/apt/sources.list.d/ansible.list || echo 'deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main' >>    /etc/apt/sources.list.d/ansible.list
          apt-add-repository -y ppa:ansible/ansible
          apt-get update
          apt-get install -y --force-yes ansible
    fi
  SHELL
end
