# Ansible playbooks

## Apps playbooks

[Install Docker](playbooks/apps/install_docker.yml)

## Server playbooks

[Configure new Debian server](playbooks/configure_new_debian_server.yml)

[Update Debian server](playbooks/update_server.yml)

## Hosts file

<details>
<summary>Create a hosts file</summary>
<br>

Create a `hosts` file with a list of hosts you want to interact with. 
```sh
[<group_name>]
<username>@<hostname>
```

example:
```sh
[update_server]
jondoe@192.168.1.10
```
</details>

## Commands

<details>
<summary>Run a playbook</summary>
<br>

```sh
ansible-playbook -i <hosts_file> playbooks/<playbook>.yml
```
</details>

<details>
<summary>Run a playbook and ask for sudo password</summary>
<br>

```sh
append --ask-become-pass

ansible-playbook -i hosts playbooks/<playbook>.yml --ask-become-pass
```
</details>

## Install Ansible

<details>
<summary>Debian</summary>

Update your system’s package database and install the necessary dependencies:
```sh
sudo apt update && sudo apt install -y python3-pip git
```
Install Ansible with pip:
```sh
python3 -m pip install --user ansible
```
Verify that Ansible is installed correctly by running the following command:
```sh
ansible --version
```
</details>

<details>
<summary>MacOS</summary>

Install Homebrew:
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Install Ansible with brew:
```sh
brew install ansible
```
Verify that Ansible is installed correctly by running the following command:
```sh
ansible --version
```
</details>
