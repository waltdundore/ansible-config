# MySQL Configuration

MySQL database server configuration for Ahab deployment.

## Variables

See `mysql-vars.yml` for all configurable options.

### Key Variables

- `mysql_port`: MySQL port (default: 3306)
- `mysql_root_password`: Root password (use ansible-vault)
- `mysql_bind_address`: Bind address (default: 127.0.0.1)
- `mysql_ssl_enabled`: Enable SSL/TLS (default: true)
- `mysql_validate_password`: Enable password validation (default: true)

## Templates

- `my.cnf.template`: Main MySQL configuration

## Security Features

- Password validation policy
- SSL/TLS encryption
- Root login restrictions
- Anonymous user removal
- Test database removal

## Performance Tuning

- InnoDB buffer pool sizing
- Query cache configuration
- Connection limits
- Thread cache optimization

## Usage

```bash
# Switch to MySQL configuration
make config-mysql

# Deploy MySQL
make install-mysql
```

## Secrets Management

Store sensitive data in ansible-vault:

```bash
# Create vault file
ansible-vault create group_vars/all/vault.yml

# Add MySQL root password
vault_mysql_root_password: "your-secure-password"
```
