# ansible-initial-server-setup
Ansible playbook to automate initial server setup on Ubuntu 20.04

Ubuntu 20.04 Initial Server Setup Ansible Playbook

Table of Contents

    -About The Project
    -Features
    -Built With
    -Getting Started
    -Prerequisites
    -Installation
    -Configuration
    -Usage
    -Roadmap
    -Contributing
    -License
    -Contact
    -Acknowledgments

About The Project

This repository contains an Ansible playbook designed to automate the initial setup of a fresh Ubuntu 20.04 server. It streamlines the process of securing and preparing new instances for deployment, ensuring consistency across your infrastructure and significantly reducing manual configuration time.

Whether you're provisioning a single VPS or multiple cloud instances, this playbook provides a robust and repeatable way to get your servers ready for your applications.
Features

    System Update & Upgrade: Ensures all packages are up-to-date.

    User Creation: Creates a new non-root user with sudo privileges.

    SSH Hardening:

    Disables root login via SSH.

    Disables password authentication (requires SSH key authentication).

    Changes default SSH port (optional).

    Firewall Configuration (UFW):

    Enables UFW.

    Allows SSH access (on the configured port).

    Allows HTTP/HTTPS (optional, for web servers).

    Denies all other incoming traffic by default.

    Time Synchronization: Installs and configures ntp or systemd-timesyncd.

    Basic Security Tools: Installs fail2ban for brute-force attack prevention.

    Common Utilities: Installs essential packages like curl, wget, git, unzip, etc.

Built With

    Ansible

    Ubuntu 20.04 LTS

Getting Started

To get this playbook running on your servers, follow these steps.
Prerequisites

Before you begin, ensure you have:

    Ansible Installed: You need Ansible (version 2.9 or higher is recommended) on your local machine (the control node).

    # On Debian/Ubuntu:
    sudo apt update
    sudo apt install software-properties-common
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install ansible

    # On macOS (with Homebrew):
    brew install ansible

    SSH Access: The target Ubuntu 20.04 server(s) must be accessible via SSH from your control node.

    SSH Key Authentication: It's highly recommended to use SSH key-based authentication for the root user (or an initial user with sudo privileges) on the target server.

    Python on Target: Ubuntu 20.04 comes with Python 3 installed by default, which Ansible requires.

Installation

    Clone the repository:

    git clone https://github.com/your-username/ansible-ubuntu-setup.git
    cd ansible-ubuntu-setup

Configuration

You'll need to configure your inventory.ini file and group_vars/all.yml to match your environment.

    Define your hosts in inventory.ini:
    Create or edit the inventory.ini file at the root of the playbook. Replace your_server_ip_or_hostname with your actual server details.

    # inventory.ini
    [ubuntu_servers]
    your_server_ip_or_hostname ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
    # If you have multiple servers, list them like this:
    # server1.example.com ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
    # server2.example.com ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa

        ansible_user: The initial user to connect as (should have sudo privileges, root is common for initial setup).

        ansible_ssh_private_key_file: Path to your SSH private key.

    Configure variables in group_vars/all.yml:
    Edit the group_vars/all.yml file to customize the setup.

    # group_vars/all.yml

    # --- New User Configuration ---
    new_user: "your_new_username" # REQUIRED: The username for the new non-root user
    new_user_ssh_key: |          # REQUIRED: Your public SSH key for the new user
      ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC... your_public_key_goes_here your_email@example.com

    # --- SSH Hardening ---
    ssh_port: 22                 # Optional: Change this to a non-standard SSH port (e.g., 2222)
    disable_password_auth: true  # Set to true to disable password authentication for SSH
    disable_root_login: true     # Set to true to disable root login via SSH

    # --- Firewall (UFW) Configuration ---
    enable_ufw: true             # Set to true to enable UFW firewall
    allow_http: true             # Set to true to allow incoming HTTP (port 80)
    allow_https: true            # Set to true to allow incoming HTTPS (port 443)
    # Add more ports if needed, e.g.:
    # allowed_ports:
    #   - 8080/tcp
    #   - 3306/tcp # MySQL

    # --- Other Settings ---
    install_ntp: true            # Set to true to install NTP for time synchronization
    install_fail2ban: true       # Set to true to install Fail2Ban

    Important: Replace "your_new_username" and the new_user_ssh_key with your actual desired username and your public SSH key. This key will be used to log in as the new user after the playbook runs.

Usage

Once you've configured your inventory.ini and group_vars/all.yml, you can run the playbook.

    Perform a dry run (recommended first):
    This will show you what changes Ansible would make without actually applying them.

    ansible-playbook -i inventory.ini main.yml --check --diff

    Run the playbook:
    This will execute the playbook and apply the configurations to your server(s).

    ansible-playbook -i inventory.ini main.yml --ask-become-pass

        -i inventory.ini: Specifies your inventory file.

        main.yml: The main playbook file.

        --ask-become-pass: Prompts for the sudo password on the target machine if ansible_user is not root or if passwordless sudo is not configured for the initial user. If you're connecting as root with an SSH key, you might not need this.

    After the playbook completes, you should be able to SSH into your server as the new_user you specified, using your SSH key. Root login and password authentication should be disabled (if configured).

Roadmap

    [ ] Add support for other Linux distributions (e.g., CentOS, Debian).

    [ ] Include roles for common applications (e.g., Docker, Nginx, PostgreSQL).

    [ ] Implement idempotency checks for all tasks.

    [ ] Improve error handling and reporting.

    [ ] Add more comprehensive security hardening options.

See the open issues for a full list of proposed features (and known issues).
Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

    Fork the Project

    Create your Feature Branch (git checkout -b feature/AmazingFeature)

    Commit your Changes (git commit -m 'Add some AmazingFeature')

    Push to the Branch (git push origin feature/AmazingFeature)

    Open a Pull Request

License

Distributed under the MIT License. See LICENSE for more information.
Contact

Project Link: [https://github.com/paulmmoore3416/ansible-initial-server-setup]
