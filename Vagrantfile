Vagrant.require_version ">= 1.7.0"

Vagrant.configure("2") do |config|
  # Use official Ubuntu 16.04 LTS (Xenial Xerus)
  config.vm.box = "ubuntu/xenial64"

  config.vm.hostname = "xenial64-lemp"

  # Do not generate ubuntu/xenial64 console log
  # https://groups.google.com/d/topic/vagrant-up/eZljy-bddoI
  config.vm.provider "virtualbox" do |vb|
    vb.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
  end

  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3306, host: 33060

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant_playbook.yml"
    ansible.compatibility_mode = "2.0"
    # Use ubuntu/xenial64 default python3 instead of Ansible preferred python2
    ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
  end
end
