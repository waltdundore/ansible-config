<div align="center">

# Ahab Config

![Ahab Logo](https://raw.githubusercontent.com/waltdundore/ansible-control/prod/docs/images/ahab-logo.png)

**Automated Host Administration & Build - Config**

*Configuration settings and modular packages*

</div>

---

## Overview

This repository contains:
- **config.yml** - Main configuration file
- **modules/** - Modular configuration packages (git clones)

## Branch Structure

- `dev` - Development settings
- `prod` - Production settings
- `workstation` - Workstation settings

## Setup

```bash
cd ~/git/ansible-config
git checkout dev
vim config.yml
```

Update SSH key path and other settings.

## Configuration Modules

Modules allow you to package and distribute reusable configurations. Each module is a separate git repository cloned into the `modules/` directory.

### Managing Modules

```bash
# List installed modules
make module-list

# Add a new module
make module-add

# Remove a module
make module-remove

# Update all modules
make module-update
```

### Using Modules

After adding a module, include its configuration in your `config.yml`:

```yaml
# Include module configurations
includes:
  - modules/docker-stack/config.yml
  - modules/monitoring/config.yml
```

See [modules/README.md](modules/README.md) for detailed documentation.

## Configuration Variables

- `ansible.playbook` - Playbook to run
- `ansible.roles` - Roles to apply
- `vagrant.vms` - VM definitions
- `ssh.public_key` - SSH key path
- `common.user` - System username
- `docker.users` - Docker group members

## Module Structure

```
ansible-config/
├── config.yml          # Main configuration
├── dev/
│   └── config.yml      # Dev-specific config
├── prod/
│   └── config.yml      # Prod-specific config
├── workstation/
│   └── config.yml      # Workstation config
└── modules/            # Modular packages (gitignored)
    ├── README.md       # Module documentation
    ├── docker-stack/   # Example module
    └── monitoring/     # Example module
```

## Creating Modules

1. Create a git repository with your configuration
2. Add `config.yml` and any supporting files
3. Document usage in README.md
4. Add to your setup: `make module-add`

Example module structure:
```
my-module/
├── README.md
├── config.yml
├── roles/
└── files/
```

---

## About

**Ahab Software, LLC**  
Automated Host Administration & Build

Website: [ahabsoftware.com](https://ahabsoftware.com)  
GitHub: [github.com/waltdundore](https://github.com/waltdundore)

Licensed under CC BY-NC 4.0 - See LICENSE file
