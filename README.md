# Ansible Role: V2ray Server

An Ansible Role that installing Shadowsocks Server  on Linux

## Requirements

Debian 9/Ubuntu 18.04

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
uuid: '53eb9e88-fcdb-4499-8263-9b2ccb9b1802'
alterId: 64
httpsPort: 443
tlsPort:8887
h2Port: 8443
```

## Dependencies

None.

## Example Playbook

Clone the project to a directory named `v2ray`:

```shell
git clone git@github.com:devops-templates/ansible-roles-shadowsocks-server.git v2ray
```

Move `hosts.example` and `v2ray.yml` to the same parent directory of `v2ray`:

```yaml
---
- hosts: all
  remote_user: sysops
  become: yes
  # remote_user: user
  # become: yes
  # become_method: sudo
  roles:
    - role: 'v2ray'
      vars:
        uuid: '53eb9e88-fcdb-4499-8263-9b2ccb9b1802'
        alterId: 64
        httpsPort: 443
        tlsPort:8887
        h2Port: 8443
```

Then run the playbook, like this:

```shell
ansible-playbook -i hosts v2ray.yml
```

If use a SSH Key with custom name, run the playbook like this:

```shell
ansible-playbook -i hosts v2ray.yml  --become --key-file ~/.ssh/vps-ssh-key
```

## License

MIT / BSD

## Author Information

This role was created by [小碼哥](https://thisiswangle.com/)
