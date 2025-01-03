[![CI](https://github.com/de-it-krachten/ansible-role-redis/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-redis/actions?query=workflow%3ACI)


# ansible-role-redis

Installs & manages redis



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# List of redis packages to install
redis_packages:
  - redis

# List of services
redis_services:
  - redis

# Dict of settings to configure
redis_settings:
  maxmemory: 100mb
  maxmemory-policy: volatile-ttl
  # bind: '127.0.0.1 ::1'
  bind: "127.0.0.1"
  supervised: systemd
</pre></code>

### defaults/family-Debian.yml
<pre><code>
# redis configuration
redis_conf: /etc/redis/redis.conf
</pre></code>

### defaults/family-RedHat-9.yml
<pre><code>
# redis configuration
redis_conf: /etc/redis/redis.conf
</pre></code>

### defaults/family-RedHat.yml
<pre><code>
# redis configuration
redis_conf: /etc/redis.conf
</pre></code>

### defaults/family-Suse.yml
<pre><code>
# List of redis packages to install
redis_packages:
  - redis7

# redis configuration
redis_conf: /etc/redis/default.conf

# List of services
redis_services:
  - redis@default
</pre></code>

### defaults/Ubuntu-18.yml
<pre><code>
# redis configuration
redis_conf: /etc/redis/redis.conf

# Dict of settings to configure
redis_settings_overwrite:
  bind: '127.0.0.1'
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'redis'
  hosts: all
  become: 'yes'
  tasks:
    - name: Include role 'redis'
      ansible.builtin.include_role:
        name: redis
</pre></code>
