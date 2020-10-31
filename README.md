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

# Nginx configurations
access_log: /var/log/nginx/nginx.access.log
error_log: /var/log/nginx/nginx.error.log
user: nginx
pid: /run/nginx.pid
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
