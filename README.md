# LAMP Stack Deployment with Ansible

This repository contains an Ansible playbook to automate the installation and setup of a LAMP (Linux, Apache, MySQL, PHP) stack on Ubuntu 18+ servers. Once the project is complete, you'll be able to deploy LAMP stacks with the following components:

- **Apache**: The latest version of the Apache web server.
- **PHP**: PHP 7.4 or later.
- **MySQL**: MySQL 8 for database management.

## Prerequisites

Before running the Ansible playbook, ensure you have the following:

1. **Ansible Control Node**: An Ubuntu 18.04 machine with Ansible installed and configured to connect to your Ansible hosts using SSH keys. Make sure the control node has a regular user with sudo permissions and a firewall enabled. If you haven't set up Ansible yet, follow our guide on [How to Install and Configure Ansible on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-lamp-on-ubuntu-18-04).

## What Does this Playbook Do?

Running this Ansible playbook will perform the following actions on your Ansible hosts:

1. Install `aptitude`, which is preferred by Ansible as an alternative to the `apt` package manager.
2. Install the required LAMP packages.
3. Create a new Apache VirtualHost and set up a dedicated document root for it.
4. Enable the new VirtualHost.
5. Optionally disable the default Apache website (when the `disable_default` variable is set to true).
6. Set the password for the MySQL root user.
7. Remove anonymous MySQL accounts and the test database.

## Usage

1. Clone this repository to your Ansible control node.
2. Edit the `hosts` file to specify the target hosts.
3. Run the playbook using the following command:

   ```bash
   ansible-playbook -i hosts site.yml
