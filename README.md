# PHP Configuration

PHP runtime configuration for Ahab deployment.

## Variables

See `php-vars.yml` for all configurable options.

### Key Variables

- `php_version`: PHP version (default: 8.1)
- `php_memory_limit`: Memory limit (default: 256M)
- `php_expose_php`: Expose PHP version (default: false)
- `php_opcache_enabled`: Enable OPcache (default: true)
- `php_disable_functions`: Disabled functions for security

## Templates

- `php.ini.template`: Main PHP configuration
- `php-fpm.conf.template`: PHP-FPM configuration

## Security Features

- Dangerous functions disabled
- URL includes/fopen disabled
- Secure session configuration
- Error display disabled in production
- Security headers configuration

## Performance Features

- OPcache enabled and tuned
- PHP-FPM process management
- Memory and execution limits
- File upload optimization

## Usage

```bash
# Switch to PHP configuration
make config-php

# Deploy PHP
make install-php
```

## Extensions

The following PHP extensions are installed by default:
- CLI and FPM
- Database drivers (MySQL, PostgreSQL)
- Common libraries (cURL, GD, mbstring, XML, ZIP)
- Performance (OPcache)
- Utility (BCMath, Intl)
