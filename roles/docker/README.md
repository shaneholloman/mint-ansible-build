# Ansible Docker role

Installs Docker CE.

## Requires

The Ansible Docker role has the following requirements:

* Operating system: Ubuntu

## Usage

Configure all depending roles.

```yml
docker_package: "docker-ce=5:19.03.8~3-0~ubuntu-bionic"
docker_log_driver: "json-file"
docker_log_max_size: "10m"
docker_log_max_file: "3"
```

Include it in your playbook.

```yml
- hosts: docker
  roles:
  - role: docker
    tags: docker
```