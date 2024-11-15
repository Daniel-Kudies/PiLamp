<p align="center" width="100%">
    <img width="20%" src="images/logo.jpg"> 
</p>

# PiLAMP
PiLAMP is an Ansible project designed to automate the deployment of a LAMP stack (**Linux**, **Apache**, **MySQL**, and **PHP**) on a target infrastructure. It includes configuration files and playbooks to enable easy and efficient setup.

## Features

- **Apache Web Server**: A robust and widely used web server.
- **MySQL Database**: Reliable and fast relational database management.
- **PHP Support**: Comprehensive support for PHP-based web applications.
- **Simple Installation**: PiLAMP provides a user-friendly setup process via Ansible.

## Prerequisites

- A working Ansible setup (version 2.9 or higher recommended)
- SSH access to target servers
- Python installed on the controller node and target servers

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd PiLAMP

2. Adjust the inventory files and variables in pilamp/inventory to match your infrastructure.

3. Run the playbooks:
   ```bash
   ansible-playbook -i pilamp/inventory/staging.yaml pilamp/playbooks/main.yaml
   ```

## Project Structure
```
PiLAMP/
├── .gitignore                  # Git ignore file
├── README.md                   # Project documentation
├── .vscode/settings.json       # VS Code-specific settings
├── images/
│   └── logo.jpg                # Logo or images
├── pilamp/
│   ├── ansible.cfg             # Ansible configuration file
│   ├── inventory/              # Inventory files and group variables
│   │   ├── staging.yaml
│   │   ├── group_vars/
│   │   │   ├── adminer.yaml
│   │   │   ├── database.yaml
│   │   │   ├── default_vars.yaml
│   │   │   ├── php.yaml
│   │   │   └── webserver.yaml
│   ├── playbooks/              # Ansible playbooks and roles
│   │   ├── database.yaml
│   │   ├── main.yaml
│   │   ├── webserver.yaml
│   │   └── roles/
│   │       ├── database/
│   │       │   ├── handlers/main.yaml
│   │       │   └── tasks/main.yaml
│   │       ├── php/
│   │       │   ├── handlers/main.yaml
│   │       │   └── tasks/main.yaml
│   │       └── webserver/
│   │           ├── files/index.html
│   │           ├── handlers/main.yaml
│   │           ├── tasks/
│   │           │   ├── adminer.yaml
│   │           │   ├── main.yaml
│   │           │   └── webserver.yaml
│   │           ├── templates/
│   │           │   ├── hosts.j2
│   │           │   ├── logrotate-apache.j2
│   │           │   ├── vhost.j2
│   │           │   └── vhost_adminer.j2
```
