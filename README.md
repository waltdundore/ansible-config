# ansible-config

Central configuration file for ansible-control project.

## Usage

This repository contains `config.yml` which configures:
- Ansible playbook selection
- SSH key paths
- Vagrant VM resources
- Libvirt network settings
- Role-specific variables (common, docker, nfs, workstation)

## Setup

1. Clone this repository alongside ansible-control:
```bash
git clone git@github.com:waltdundore/ansible-config.git
```

2. Edit `config.yml` with your settings

3. Symlink into ansible-control:
```bash
cd ansible-control
ln -s ../ansible-config/config.yml config.yml
```

## Configuration

See `config.yml` for all available settings and documentation.
