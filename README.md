# ansible-config

Configuration settings for ansible-control.

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
