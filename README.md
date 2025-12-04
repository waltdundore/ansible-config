# ansible-config

Configuration settings for ansible-control.

## Setup

Use ansible-control setup script:

```bash
cd ~/git/ansible-control
./setup.sh
```

## Edit Configuration

```bash
cd ~/git/ansible-config
git checkout dev
vim dev/config.yml
```

**Required:**
```yaml
ssh:
  public_key: ~/.ssh/id_ed25519.pub  # Your SSH key path
```

**Optional:**
```yaml
vagrant:
  cpus: 4
  memory: 16384
  vms:
    - name: fedora
      box: bento/fedora-43

common:
  packages:
    - vim
    - git

docker:
  users:
    - your_username

nfs:
  mounts:
    - path: /mnt/storage
      src: server:/export
```

## Branches

- `dev` - Development settings
- `prod` - Production settings
- `workstation` - Workstation settings
