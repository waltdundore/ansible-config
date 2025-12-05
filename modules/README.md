# Ahab Configuration Modules

This directory contains modular configuration packages that can be included in your Ahab setup.

## What are Modules?

Modules are git repositories containing reusable configuration snippets, playbooks, roles, or complete application stacks. They allow you to:

- Package and distribute common configurations
- Version control your infrastructure components
- Share configurations across teams
- Easily add/remove functionality

## Module Structure

Each module should contain:

```
module-name/
├── README.md           # Module documentation
├── config.yml          # Configuration snippet to merge
├── roles/              # Optional: Ansible roles
├── playbooks/          # Optional: Ansible playbooks
└── files/              # Optional: Static files
```

## Managing Modules

### List Installed Modules
```bash
make module-list
```

### Add a Module
```bash
make module-add
# Enter git URL: git@github.com:user/module-name.git
# Enter module name: module-name
```

### Remove a Module
```bash
make module-remove
# Enter module name: module-name
```

### Update All Modules
```bash
make module-update
```

## Using Modules

After adding a module, include its configuration in your main `config.yml`:

```yaml
# Include module configuration
includes:
  - modules/docker-stack/config.yml
  - modules/monitoring/config.yml
```

## Creating Your Own Modules

1. Create a new git repository
2. Add your configuration files
3. Document usage in README.md
4. Add the module using `make module-add`

### Example Module: docker-stack

```yaml
# modules/docker-stack/config.yml
docker:
  compose_version: "2.23.0"
  containers:
    - name: traefik
      image: traefik:latest
      ports:
        - "80:80"
        - "443:443"
```

## Module Best Practices

1. **Version your modules** - Use git tags for releases
2. **Document dependencies** - List required Ansible collections
3. **Provide examples** - Include sample configurations
4. **Keep modules focused** - One purpose per module
5. **Test thoroughly** - Validate on multiple distributions

## Official Modules

Coming soon - official Ahab modules for common stacks:
- Docker Compose stacks
- Monitoring (Prometheus/Grafana)
- Web servers (Nginx/Apache)
- Databases (PostgreSQL/MySQL)
- CI/CD tools

## Community Modules

Share your modules! Submit a PR to add your module to the community list.

---

**Ahab Software, LLC**  
Licensed under CC BY-NC 4.0
