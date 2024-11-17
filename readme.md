# Ansible playbooks

## Playbooks

### install_docker.yml
This playbook automates the entire process of installing Docker on a Debian server, making it easy to set up and manage Docker environments across multiple servers.

### new_server.yml
This playbook is designed to set up a new Debian server with essential security and configuration settings.
- Hostname
- Updates
- Automatic security updates
- Configure SSH
    - Disable ROOT login
    - Disable password login
- Enable UFW
    - Allow OpenSSH
    - Default deny incoming
    - Default allow outgoing

### update_servers.yml
This playbook performs a two-step process on specified Debian servers: first, it updates the package cache, and then it upgrades all installed packages to ensure that the servers are running the latest software versions. This is an essential maintenance task for keeping systems secure and up to date.


## Hosts
Remember to create a hosts file with a list of hosts you want to interact with. 

## Commands to run
### Run a playbook
Run the following command to execute a playbook:
```sh
ansible-playbook -i <hosts_file> playbooks/<playbook>.yml
```

### SUDO playbooks
If you want to run a playbook as root, you need to add the following flag:
```sh
--ask-become-pass
```

## Install Ansible
### Debian
1. Update your system’s package database and install the necessary dependencies:
```sh
sudo apt update && sudo apt install -y python3-pip git
```
2. Install Ansible with pip:
```sh
python3 -m pip install --user ansible
```
3. Verify that Ansible is installed correctly by running the following command:
```sh
ansible --version
```

### MacOS
1. Install Homebrew:
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
2. Install Ansible with brew:
```sh
brew install ansible
```
3. Verify that Ansible is installed correctly by running the following command:
```sh
ansible --version
```