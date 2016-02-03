# Ansible Role: Memcached

[![Build Status](https://img.shields.io/travis/thestarkenya/ansible-role-memcached.svg)](https://travis-ci.org/thestarkenya/ansible-role-memcached) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/thestarkenya/ansible-role-memcached/master/LICENSE)

Installs and configures Memcached on RHEL/CentOS ~~or Debian/Ubuntu~~.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
memcached_config_use_template: true
# Listen on TCP port <num>
memcached_config_port: 11211
# Use <num> MB memory max to use for object storage
memcached_config_cachesize: 64
# Use <num> max simultaneous connections
memcached_config_maxconn: 1024
# Extra options
memcached_config_options: []
```

## Dependencies

None

## Example Playbook

```yaml
- hosts: servers

  vars_files:
    - vars/main.yml

  roles:
    - role: ansible-role-memcached
```

Inside `vars/main.yml`:

```yaml
memcached_config_options:
  - -l 127.0.0.1
  - -v >> /var/log/memcached.log

# ... etc ...
```

## License

MIT
