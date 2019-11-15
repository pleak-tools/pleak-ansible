Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"

  config.vm.synced_folder ".", "/vagrant_data"

  config.vm.network :forwarded_port, guest: 8000, host: 8000, id: 'www-frontend'
  config.vm.network :forwarded_port, guest: 8080, host: 8080, id: 'www-backend'
  config.vm.network :forwarded_port, guest: 3000, host: 3000, id: 'www-leakswhen'


  config.vm.provider "virtualbox" do |vb|
     # Display the VirtualBox GUI when booting the machine
     # vb.gui = true

     # Customize the amount of memory on the VM:
      vb.memory = "3048"
  end

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook.yml"
      ansible.become = true
  end

  config.vm.provision :shell, :inline => "sudo systemctl start pleak-frontend", run: "always"
  config.vm.provision :shell, :inline => "sudo systemctl start pleak-backend", run: "always"
  config.vm.provision :shell, :inline => "sudo systemctl start pleak-leakswhen", run: "always"

end
