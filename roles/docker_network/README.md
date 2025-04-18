<img src="/logos/docker_network.png" alt="docker_network logo" width="100" height="100">

# Docker Network role

Configures a Docker network.

## Usage

Configure the role.

```yml
docker_network_name: example.com
docker_network_driver: overlay # defaults: bridge
docker_network_subnet: 172.18.1.0/24 # default: 172.18.0.0/16
docker_network_gateway: 172.18.1.1 # default: 172.18.0.1
docker_network_ipv6_subnet: 2001:db8:2::/64 # default: 2001:db8:1::/64
docker_network_ipv6_gateway: 2001:db8:2::1 # default: 2001:db8:1::1
```

And include it in your playbook.

```yml
- hosts: docker_network
  roles:
  - role: docker_network
```

## Docs

### IP tables

The `docker-proxy` ceates NAT routes in the ip tables. To list them run:

```
sudo iptables -t nat -L DOCKER -n -v
```
