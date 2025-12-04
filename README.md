# ansible-config

Central configuration file for ansible-control project.

## Repository Dependencies

**This repository is part of a three-repository system:**

1. **[ansible-control](https://github.com/waltdundore/ansible-control)** - Main playbooks and roles
2. **[ansible-inventory](https://github.com/waltdundore/ansible-inventory)** - Environment-specific host definitions
3. **THIS REPO** - Central configuration file

### Setup

```bash
# Clone all three repositories
cd ~/git
git clone git@github.com:waltdundore/ansible-control.git
git clone git@github.com:waltdundore/ansible-inventory.git
git clone git@github.com:waltdundore/ansible-config.git

# Create symlinks in ansible-control
cd ansible-control
ln -s ../ansible-inventory inventory
ln -s ../ansible-config/config.yml config.yml
```

## Configuration

The `config.yml` file contains all project settings:

### Ansible Configuration
- Playbook selection (docker, common, proxy, workstation)

### SSH Configuration
- SSH public key path

### Vagrant Configuration
- VM box selection
- CPU and memory allocation
- Multi-VM definitions

### Libvirt Configuration
- Network settings
- Disk size

### Role Configuration
- Common role: packages to install/remove
- Docker role: repository selection, user groups
- NFS role: server, export, mount settings
- Workstation role: packages, user groups, kernel modules

## Branch Strategy

All three repositories have matching branches:
- `dev` - Development environment
- `prod` - Production environment
- `workstation` - Workstation setup

**IMPORTANT:** Keep all three repos on the same branch when working.

## Usage

1. Edit `config.yml` with your settings
2. Changes affect all environments
3. Must be symlinked into ansible-control to function

## Important Notes

- This is the single source of truth for configuration
- All role defaults reference this file
- Changes here affect dev, prod, and workstation
- Must be symlinked as `config.yml` in ansible-control root
