# Ansible Initial Server Setup Lab

This repository contains a beginner-friendly Ansible automation lab for setting up initial server configurations. It demonstrates basic Ansible concepts like playbooks, roles, inventory, and variables.

## Prerequisites

- Ansible installed on your control machine.
- SSH access to target servers.
- Basic knowledge of Linux command line.

## Lab Structure

- `inventory.ini`: Defines the target servers.
- `playbook.yml`: Main playbook for initial setup.
- `roles/`: Directory containing Ansible roles.
  - `common/`: Common server setup tasks.
  - `users/`: User management.
  - `security/`: Security hardening.
- `group_vars/`: Variables for different groups.
- `ansible.cfg`: Ansible configuration.

## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/ansible-initial-server-setup.git
   cd ansible-initial-server-setup
   ```

2. Edit `inventory.ini` to add your target servers.

3. Update variables in `group_vars/all.yml` as needed.

4. Run the playbook:
   ```bash
   ansible-playbook -i inventory.ini playbook.yml
   ```

## What This Lab Covers

- Installing essential packages.
- Creating users and setting up SSH keys.
- Configuring firewall rules.
- Setting up basic monitoring.
- Applying security best practices.

## Next Steps

- Experiment with adding new roles.
- Integrate with CI/CD pipelines.
- Deploy to cloud environments.

## Resources

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/) for roles.