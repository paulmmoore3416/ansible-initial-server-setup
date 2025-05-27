# 🚀 Ansible Initial Server Setup

Ansible playbook to automate initial server setup on **Ubuntu 20.04**.

---

## 📚 Table of Contents

- [About The Project](#about-the-project)
- [Features](#features)
- [Built With](#built-with)
- [Skills](#skills)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Usage](#usage)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)

---

## 📝 About The Project

This repository contains an **Ansible playbook** designed to automate the initial setup of a fresh Ubuntu 20.04 server. It streamlines the process of securing and preparing new instances for deployment, ensuring a consistent and reliable setup.

Whether you're provisioning a single VPS or multiple cloud instances, this playbook provides a robust and repeatable way to get your servers ready for your applications.

---

## ✨ Features

- **System Update & Upgrade**: Ensures all packages are up-to-date.
- **User Creation**: Creates a new non-root user with sudo privileges.
- **SSH Hardening**:
  - Disables root login via SSH.
  - Disables password authentication (requires SSH key authentication).
  - Changes default SSH port (optional).
- **Firewall Configuration (UFW)**:
  - Enables UFW.
  - Allows SSH access (on the configured port).
  - Allows HTTP/HTTPS (optional, for web servers).
  - Denies all other incoming traffic by default.
- **Time Synchronization**: Installs and configures NTP or systemd-timesyncd.
- **Basic Security Tools**: Installs fail2ban for brute-force attack prevention.
- **Common Utilities**: Installs essential packages like curl, wget, git, unzip, etc.

---

## 🛠️ Built With

- [Ansible](https://www.ansible.com/)
- [Ubuntu 20.04 LTS](https://ubuntu.com/)

---

## 🧑‍💻 Skills

<details>
  <summary><strong>Ansible</strong></summary>

**Skill Level:**  
`[██████░░░░░]` Medium

</details>

<details>
  <summary><strong>Linux</strong></summary>

**Skill Level:**  
`[██████░░░░░]` Medium

</details>

<details>
  <summary><strong>Ubuntu</strong></summary>

**Skill Level:**  
`[██████░░░░░]` Medium

</details>

<details>
  <summary><strong>Red Hat</strong></summary>

**Skill Level:**  
`[██████░░░░░]` Medium

</details>

---

## 🚦 Getting Started

Follow these steps to get this playbook running on your servers.

### ✅ Prerequisites

- **Ansible Installed** (version 2.9+ recommended) on your control node.
    ```bash
    # Debian/Ubuntu:
    sudo apt update
    sudo apt install software-properties-common
    sudo add-apt-repository --yes --update ppa:ansible/ansible
    sudo apt install ansible

    # macOS (with Homebrew):
    brew install ansible
    ```
- **SSH Access**: The target Ubuntu 20.04 server(s) must be accessible via SSH from your control node.
- **SSH Key Authentication**: Highly recommended for root user or an initial sudo user on the target server.
- **Python 3 on Target**: Ubuntu 20.04 comes with Python 3 preinstalled (required by Ansible).

### 📦 Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/paulmmoore3416/ansible-initial-server-setup.git
    cd ansible-initial-server-setup
    ```

### ⚙️ Configuration

#### 1. **Inventory File**

Create or edit `inventory.ini` at the root of the playbook:

```ini
[ubuntu_servers]
your_server_ip_or_hostname ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa

# Multiple servers example:
# server1.example.com ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
# server2.example.com ansible_user=root ansible_ssh_private_key_file=~/.ssh/id_rsa
```

- `ansible_user`: The initial user to connect as (should have sudo privileges, root is common for initial setup).
- `ansible_ssh_private_key_file`: Path to your SSH private key.

#### 2. **Group Variables**

Edit `group_vars/all.yml` to customize the setup:

```yaml
# --- New User Configuration ---
new_user: "your_new_username"         # REQUIRED: The username for the new non-root user
new_user_ssh_key: |                  # REQUIRED: Your public SSH key for the new user
  ssh-rsa AAAAB3... your_public_key_goes_here your_email@example.com

# --- SSH Hardening ---
ssh_port: 22                         # Optional: Change to a non-standard SSH port (e.g., 2222)
disable_password_auth: true          # Disable password authentication for SSH
disable_root_login: true             # Disable root login via SSH

# --- Firewall (UFW) Configuration ---
enable_ufw: true                     # Enable UFW firewall
allow_http: true                     # Allow incoming HTTP (port 80)
allow_https: true                    # Allow incoming HTTPS (port 443)
# allowed_ports:
#   - 8080/tcp
#   - 3306/tcp   # MySQL

# --- Other Settings ---
install_ntp: true                    # Install NTP for time synchronization
install_fail2ban: true               # Install Fail2Ban
```

> **Important**: Replace `your_new_username` and `new_user_ssh_key` with your actual desired username and public SSH key. This key will be used to log in as the new user after the playbook runs.

---

## ▶️ Usage

After configuring your `inventory.ini` and `group_vars/all.yml`, you can run the playbook:

**Dry Run (Recommended First):**
```bash
ansible-playbook -i inventory.ini main.yml --check --diff
```

**Run the Playbook:**
```bash
ansible-playbook -i inventory.ini main.yml --ask-become-pass
```
- `-i inventory.ini`: Specifies your inventory file.
- `main.yml`: The main playbook file.
- `--ask-become-pass`: Prompts for sudo password if required.

After completion, you should be able to SSH into your server as the new user you specified, using your SSH key. Root login and password authentication should be disabled if configured.

---

## 🗺️ Roadmap

- [ ] Add support for other Linux distributions (e.g., CentOS, Debian)
- [ ] Include roles for common applications (e.g., Docker, Nginx, PostgreSQL)
- [ ] Implement idempotency checks for all tasks
- [ ] Improve error handling and reporting
- [ ] Add more comprehensive security hardening options

> See the [open issues](../../issues) for a full list of proposed features and known issues.

---

## 🤝 Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create! Any contributions you make are **greatly appreciated**.

1. **Fork the Project**
2. **Create your Feature Branch**  
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your Changes**  
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the Branch**  
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

Or simply open an issue with the tag `enhancement`.

> \⭐ Don’t forget to give the project a star!

---

## 📄 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.

---

## 📫 Contact

**Project Link:** [https://github.com/paulmmoore3416/ansible-initial-server-setup](https://github.com/paulmmoore3416/ansible-initial-server-setup)

---

## 🙏 Acknowledgments

> Thanks to the open source community for inspiration and guidance!

---
