# Ansible Role: Deploy Zabbix Agent

[![Build Status](https://travis-ci.org/dsgnr/ansible-role-deploy-zabbix-agent.svg?branch=master)](https://travis-ci.org/dsgnr/ansible-role-deploy-zabbix-agent)

This deploys the zabbix-agent to Linux and Windows device and adds the guest to the Zabbix Web UI. Some service discovery is available for Linux devices to add templates to the guest in the UI, so ensure that these are available in your installation, or remove them from the `tasks/linux.yml` file.

## Requirements

- A working Zabbix installation with write access
- Various templates listed in `tasks/linux.yml` - These can be commented out.

## Role Variables

    zabbix_linux_host_groups: Linux Servers
    zabbix_windows_host_groups: Windows Servers
    zabbix_windows_linked_templates: Template OS Windows
    zabbix_server_url: zabbix.example.com
    zabbix_server_api_user: apiuser
    zabbix_listen_server: zabbix.example.com
    zabbix_listen_server_active: zabbix.example.com

## Example Playbook

    ---

    - hosts: all
      vars_files:
        - vault/zabbix_vars.yml
      vars:
        zabbix_linux_host_groups: Linux Servers
        zabbix_windows_host_groups: Windows Servers
        zabbix_windows_linked_templates: Template OS Windows
        zabbix_server_url: zabbix.example.com
        zabbix_server_api_user: apiuser
        zabbix_listen_server: zabbix.example.com
        zabbix_listen_server_active: zabbix.example.com

      roles:
        - deploy-zabbix-agent

## License

GNUv3

## Author Information

This role was created by [Dan Hand](https://danielhand.io).
