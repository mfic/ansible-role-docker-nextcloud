Role Name
=========

An Ansible role to manave Nextcloud instances

Requirements
------------

- docker
- ansible

Role Variables
--------------

## Required variables
```yaml
site_working_directory: "/path"
db_image: "mariadb"
db_version: 11
db_volume_data: "./data/db"
db_mysql_database: "nextcloud"
db_mysql_root_password: "supersecurepassword"
db_mysql_user: "db_user"
db_mysql_password: "securepassword"
nc_image: "nextcloud"
nc_version: "latest"
nc_admin_user: "admin"
nc_admin_password: "asecurepassword"
nc_router_traefik: "nc_domain"
nc_domains: "Host(`fqdn`)"
nc_trusted_domains: "fwdn" #Optional space-separated list of domains
```

## Optional variables
```yaml
php_timezone: "UTC"
traefik_tls_provider: "letsencrypt" #letsencrypt (HTTP-Challange) or cloudflare (DNS-Challange)
traefik_docker_network: "webproxy"
db_logging:
  driver: "json-file"
  max_size: "1m"
  max_file: "10"
db_resources_limits:
  cpus: "0.5"
  memory: "300M"
nc_volume_data: "./data/site/data"
nc_volume_config: "./data/site/config"
nc_volume_apps: "./data/site/apps"
nc_volume_confd: "./conf.d/php.ini"
nc_data_dir: "/var/www/html/data"
nc_table_prefix: ""
nc_overwriteprotocol: "https"
nc_logging:
  driver: "json-file"
  max_size: "1m"
  max_file: "10"
nc_resources_limits:
  cpus: "0.5"
  memory: "300M"
```

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
