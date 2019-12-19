# pleak-ansible

Step 1: Install Ansible [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html), Vagrant [here](https://www.vagrantup.com/downloads.html) and VirtualBox [here](https://www.virtualbox.org/wiki/Downloads)

Step 2: Add your ssh key to github so you can clone with ssh. 

Step 3: Clone this repo with all the subrepos using:

```
git clone --recurse-submodules git@github.com:pleak-tools/pleak-ansible.git
```
Step 4: Start your vagrant machine by running in pleak-ansible folder:

    vagrant up
This will take some time when run for the first time, as the virtual machine is downloaded and dependencies installed.

Once the machine is up frontend can be accessed on localhost:8000, backend on localhost:8080 and leaks-when on: localhost:3000

#### Using the virtual machine

The repo root folder is mapped to /vagrant_data folder in the virtual machine. So any change you make will be reflected in the virtual machine.

To log into the virtual machine using ssh, use the `vagrant ssh` command.

To stop the virtual machine, use `vagrant halt`

To restart the virtual machine, use `vagrant reload`
