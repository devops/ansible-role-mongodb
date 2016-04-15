# Ansible Role: mongodb

Installs and configures the MongoDB.

## Requirements

None.

## Role Variables

### `defaults/main.yml`

* `mongodb_baseurl: "http://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.0/x86_64/"`
* `mongodb_disable_thp: true`
* `mongodb_packages: mongodb-org`
* `mongodb_user: mongod`
* `mongodb_daemon_name: "{{ 'mongod' if ('mongodb-org' in mongodb_packages) else 'mongodb' }}"`
* `mongodb_conf_logpath: "/var/log/mongodb"`
* `mongodb_conf_port: 27017`
* `mongodb_conf_dbpath: "/var/lib/mongo"`
* `mongodb_conf_pidfilepath: "/var/run/mongodb/mongod.pid"`
* `mongodb_conf_bind_ip: "127.0.0.1"`
* `mongodb_conf_auth: false`
* `mongodb_conf_replSet: ""`
* `mongodb_conf_oplogSize: 1024`
* `mongodb_conf_keyFile: "/path/to/keyfile"`

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
         - role: mongodb
           mongodb_conf_bind_ip: '{{ ansible_default_ipv4.address }}'
           mongodb_conf_auth: true

## Author Information

z
