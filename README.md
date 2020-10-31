philranzato.nginx
=========

Install and configure Nginx

Requirements
------------

Sudo permissions to install and configure Nginx.

Role Variables
--------------

```yaml
# configuration can be "HTTPS-reverse-proxy | "
configuration: "HTTPS-reverse-proxy"

# Upstream server parameters
upstream:
  ## The name used in the configuration file
  name: "my-server"
  ## The server fqdn to which to redirect traffic
  server: "localhost"
  ## The server port to which to redirect traffic
  port: "5678"

# SSL
ssl:
  ## Whether to enable ssl for nginx
  enabled: false
  ## The certificate path to expose on the Nginx
  certificate: /opt/private/ssl/cert.crt
  ## The certificate key to expose on the Nginx
  key: /opt/private/ssl/cert.key
  ## The certificate key password (LEAVE IT BLANK IF THERE IS NO PASSWORD PROTECTION)
  ## Password will be store in /var/lib/nginx/<cert>.key.txt, where <cert> is the key name you provide above
  key_password: ""

# Nginx configurations
access_log: /var/log/nginx/nginx.access.log
error_log: /var/log/nginx/nginx.error.log
user: nginx
pid: /run/nginx.pid
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
---
- name: "Install and configure Nginx"
  hosts: target
  roles:
  - { role: philranzato.nginx }
  vars_files:
  - vars/nginx.yml
```

License
-------

BSD

Author Information
------------------

Check me on [LinkedIn](www.linkedin.com/in/phil-ranzato-47b8bb194)
