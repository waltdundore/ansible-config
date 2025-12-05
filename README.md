<div align="center">

# Ahab Config

![Ahab Logo](https://raw.githubusercontent.com/waltdundore/ansible-control/prod/docs/images/ahab-logo.png)

**Automated Host Administration & Build - Config**

*Configuration settings*

</div>

---

## Branch Structure

- `dev` - Development settings
- `prod` - Production settings
- `workstation` - Workstation settings

## Setup

```bash
cd ~/git/ansible-config
git checkout dev
vim dev/config.yml
```

Update SSH key path and other settings.

## Usage

Link from ansible-control:

```bash
cd ~/git/ansible-control
ln -s ../ansible-config/dev/config.yml config.yml
```

## Configuration Variables

- `ansible.playbook` - Playbook to run
- `ansible.roles` - Roles to apply
- `vagrant.vms` - VM definitions
- `ssh.public_key` - SSH key path
- `common.user` - System username
- `docker.users` - Docker group members


---

## About

**Ahab Software, LLC**  
Automated Host Administration & Build

Website: [ahabsoftware.com](https://ahabsoftware.com)  
GitHub: [github.com/waltdundore](https://github.com/waltdundore)

Licensed under CC BY-NC 4.0 - See LICENSE file

