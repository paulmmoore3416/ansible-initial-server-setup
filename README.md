# Ansible Initial Server Setup Lab

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Ansible Lint](https://github.com/paulmmoore3416/ansible-initial-server-setup/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/paulmmoore3416/ansible-initial-server-setup/actions/workflows/ansible-lint.yml)
[![GitHub issues](https://img.shields.io/github/issues/paulmmoore3416/ansible-initial-server-setup)](https://github.com/paulmmoore3416/ansible-initial-server-setup/issues)
[![GitHub stars](https://img.shields.io/github/stars/paulmmoore3416/ansible-initial-server-setup)](https://github.com/paulmmoore3416/ansible-initial-server-setup/stargazers)

This repository contains a beginner-friendly Ansible automation lab for setting up initial server configurations. It demonstrates basic Ansible concepts like playbooks, roles, inventory, and variables.

## Features

- **Modular Roles**: Organized Ansible roles for common, users, security, nginx, and postgresql.
- **Secure Setup**: Includes SSH hardening, firewall configuration, and user management.
- **Easy Configuration**: Simple inventory and variable management.
- **Beginner-Friendly**: Step-by-step guide for learning Ansible.

## Prerequisites

- Ansible installed on your control machine.
- SSH access to target servers.
- Basic knowledge of Linux command line.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/paulmmoore3416/ansible-initial-server-setup.git
   cd ansible-initial-server-setup
   ```

2. Install Ansible (if not already installed):
   ```bash
   # On Ubuntu/Debian
   sudo apt update
   sudo apt install ansible

   # On macOS
   brew install ansible

   # On other systems, follow https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
   ```

## Usage

1. Edit `inventory.ini` to add your target servers.

2. Update variables in `group_vars/all.yml` as needed.

3. Run the playbook:
   ```bash
   ansible-playbook -i inventory.ini playbook.yml
   ```

## Lab Structure

- `inventory.ini`: Defines the target servers.
- `playbook.yml`: Main playbook for initial setup.
- `roles/`: Directory containing Ansible roles.
  - `common/`: Common server setup tasks.
  - `users/`: User management.
  - `security/`: Security hardening.
  - `nginx/`: Web server setup.
  - `postgresql/`: Database setup.
- `group_vars/`: Variables for different groups.
- `ansible.cfg`: Ansible configuration.

## What This Lab Covers

- Installing essential packages.
- Creating users and setting up SSH keys.
- Configuring firewall rules.
- Setting up basic monitoring.
- Applying security best practices.

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Next Steps

- Experiment with adding new roles.
- Integrate with CI/CD pipelines.
- Explore advanced Ansible features.
- Deploy to cloud environments.

## Resources

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/) for roles.