# Ansible Role: V2ray Server

An Ansible Role that installing V2ray Server on Linux

## Requirements

Debian 9/Ubuntu 18.04

## Role Variables

Available variables are listed below, along with default values (see defaults/main.yml):

```yaml
ServerName: 'example.com'
Clientid: '53eb9e88-fcdb-4499-8263-9b2ccb9b1802'
HttpsPort: 443
WsPath: '/ws'
PlainPort: 1887
TlsPort: 8887
Http2Port: 8443
Http2Path: '/h2'
```

## Dependencies

None.

## Example Playbook

Clone the project to a directory named `v2ray`:

```shell
git clone git@github.com:devops-templates/ansible-roles-v2ray.git v2ray
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
        ServerName: 'example.com'
        Clientid: '53eb9e88-fcdb-4499-8263-9b2ccb9b1802'
        HttpsPort: 443
        WsPath: '/ws'
        PlainPort: 1887
        TlsPort: 8887
        Http2Port: 8443
        Http2Path: '/h2'
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
