NFS Ansible role
================

Installs NFS utilities and configure clients

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    nfs__install: False

Install mandatory packages

    nfs__configure: False

Configure server-side NFS

    nfs__client_configure: False

Configure client-side NFS

    nfs__exports: []
      - path: 
      - host: 
      - owner: 
      - group: 
      - options: 

    nfs__owner: []
    nfs__group: []

    nfs__pipefs: "/run/rpc_pipefs"

Depends on distribution and version used, these pipefs located in `/etc/idmapd.conf` file may change.

    nfs__mapping:
      nobody_user: nobody
      nobody_group: nogroup
      domain: []

The mapping of users and domain, placed in `/etc/idmapd.conf` file. Defaults are `nobody` for user, and `nogroup` for group. If no domain specified, it defaults to value returned by `dnsdomainname` command.

## Dependencies

None.

## Example Playbook

    - hosts: db-servers
      roles:
        - { role: nfs }

## License

## Author Information
