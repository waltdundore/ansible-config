# Apache Configuration

Apache web server configuration for Ahab deployment.

## Variables

See `apache-vars.yml` for all configurable options.

### Key Variables

- `apache_port`: HTTP port (default: 80)
- `apache_ssl_port`: HTTPS port (default: 443)
- `apache_document_root`: Web root directory
- `ssl_enabled`: Enable SSL/TLS (default: true)
- `apache_security_headers`: Enable security headers (default: true)

## Templates

- `apache.conf.template`: Main Apache configuration
- Additional templates can be added for virtual hosts, etc.

## Security Features

- Security headers (X-Frame-Options, X-XSS-Protection, etc.)
- SSL/TLS with modern cipher suites
- Server information hiding
- TRACE method disabled
- Directory traversal protection

## Usage

```bash
# Switch to Apache configuration
make config-apache

# Deploy Apache
make install-apache
```
