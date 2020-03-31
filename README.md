# Ansible script to build the Pleak development virtual machine

Step 1: Install Ansible [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html), Vagrant [here](https://www.vagrantup.com/downloads.html) and VirtualBox [here](https://www.virtualbox.org/wiki/Downloads)

Step 2: Add your SSH key to GitHub so you can clone with SSH.

Step 3: Clone this repository with all the subrepositories using:

```
git clone --recurse-submodules git@github.com:pleak-tools/pleak-ansible.git
```
Step 4: Start your Vagrant machine by running in pleak-ansible folder:

    vagrant up
This will take some time when run for the first time, as the virtual machine is downloaded and dependencies installed.

Once the machine is up frontend can be accessed on localhost:8000, backend on localhost:8080 and leaks-when analyser on: localhost:3000

#### Using the virtual machine

The repository's root folder is mapped to /vagrant_data folder in the virtual machine. So any change you make will be reflected in the virtual machine.

To log into the virtual machine using SSH, use the `vagrant ssh` command.

To stop the virtual machine, use `vagrant halt`

To restart the virtual machine, use `vagrant reload`

The virtual machine uses three servers to provide all necessary functionalities. These servers are automatically set up by services named `pleak-backend`, `pleak-frontend` and `pleak-leakswhen`. Use `sudo systemctl stop pleak-leakswhen` and `sudo systemctl restart pleak-leakswhen` commands to stop and restart these services or `sudo systemctl status pleak-leakswhen` command to check the status of the service (replace pleak-leakswhen with needed service name).
