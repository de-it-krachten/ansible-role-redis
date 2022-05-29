[![CI](https://github.com/de-it-krachten/ansible-role-redis/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-redis/actions?query=workflow%3ACI)


# ansible-role-redis

Installs & manages redis


Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
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
  bind: '127.0.0.1 ::1'
  supervised: systemd
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'redis'
  hosts: all
  vars:
  tasks:
    - name: Include role 'redis'
      include_role:
        name: redis
</pre></code>
