# Ahab Common Configuration

This directory contains configuration files shared across all Ahab roles.

## Files

- `ansible.cfg.base` - Base Ansible configuration
- `common-vars.yml` - Variables used by all roles
- `daemon.json.template` - Docker daemon configuration
- `sudoers.d.ahab.template` - Sudo permissions for ahab user

## Usage

These files are inherited by all role-specific branches. Role branches can:
- Override variables in `common-vars.yml` by defining them in role-specific vars
- Extend templates by including them in role-specific templates
- Add additional configuration files as needed

## Modifying Common Configs

1. Make changes on the `main` branch
2. Merge changes into role branches as needed
3. Test changes across all roles before deploying

## Security

- No secrets should be stored in these files
- Use ansible-vault for sensitive data
- All templates should follow security best practices
