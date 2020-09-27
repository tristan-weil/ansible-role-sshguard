# Ansible Role: sshguard

An Ansible Role to install and configure `sshguard`.

**NOTE**: by default this role supports *firewalld* as backend for Linux distributions.

[![Actions Status](https://github.com/tristan-weil/ansible-role-sshguard/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-sshguard/actions)

## Role Variables

Available variables are listed below, (see also `defaults/main.yml`).

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| sshguard_config | {}    | a dictionary of allowed parameters (see https://bitbucket.org/sshguard/sshguard) that will be merged with the var *sshguard_default_config* |
| sshguard_whitelist | [] | a list of whitelisted IP/MASK or hostnames    

*NOTE*: it is possible to disable a default parameter by using "DISABLED" as its value.

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-sshguard'
          sshguard_whitelist:
            - mycompany.com
            - xx.xx.xx.xx
            
          sshguard_config:
            BLACKLIST: "{{ 90:_sshguard_blacklist_path }}"

## Todo

None.

## Dependencies

See [requirements_galaxy.yml](https://github.com/tristan-weil/ansible-role-sshguard/blob/master/requirements_galaxy.yml)

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-sshguard/blob/master/meta/main.yml)

## License

See [LICENSE.md](https://github.com/tristan-weil/ansible-role-sshguard/blob/master/LICENSE.md)
