# Ansible Role: chocolatey

[![Build Status](https://img.shields.io/travis/arillso/ansible.chocolatey.svg?branch=master&style=popout-square)](https://travis-ci.org/arillso/ansible.chocolatey) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](https://sbaerlo.ch/licence) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-chocolatey-blue.svg?style=popout-square)](https://galaxy.ansible.com/arillso/chocolatey) [![Ansible Role](https://img.shields.io/ansible/role/d/25136.svg?style=popout-square)](https://galaxy.ansible.com/arillso/chocolatey)

## Description

Manage the Chocolatey Source list and config.

## Installation

```bash
ansible-galaxy install arillso.chocolatey
```

## Requirements

None

## Role Variables

### Source

A list of possible Chocolatey repositories that can be added or removed.

| Parameter                                                      | Spalte 2                                                                                                                                                                                                |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name                                                           | The name of the source. Required with actions other than list.                                                                                                                                          |
| admin_only                                                     | Makes the source visible to Administrators only.                                                                                                                                                        |
| allow_self_service                                             | Allow the source to be used with self-service                                                                                                                                                           |
| bypass_proxy                                                   | Bypass the proxy when using this source.                                                                                                                                                                |
| certificate                                                    | The path to a .pfx file to use for X509 authenticated feeds.                                                                                                                                            |
| certificate_password The password for certificate if required. |
| source                                                         | The file/folder/url of the source.                                                                                                                                                                      |
| user                                                           | The username used to access source.                                                                                                                                                                     |
| password                                                       | The password for source_username.                                                                                                                                                                       |
| priority                                                       | The priority order of this source compared to other sources, lower is better. All priorities above 0 will be evaluated first then zero-based values will be evaluated in config file order.             |
| state                                                          | absent, will remove the source. disabled, will ensure the source exists but is disabled. present, will ensure the source exists and is enabled.                                                         |
| update_password                                                | always, the module will always set the password and report a change if certificate_password or source_password is set. on_create, the module will only set the password if the source is being created. |

```yml
chocolatey_source:
  - name: chocolatey
    source: https://chocolatey.org/api/v2/
    priority: 0
    state: present
```

### Config

There are settings that can adjust the way Chocolatey works for you
See: [https://chocolatey.org/docs/chocolatey-configuration#config-settings](https://chocolatey.org/docs/chocolatey-configuration#config-settings)

```yml
chocolatey_config:
  # Default timeout for command execution
  - commandExecutionTimeoutSeconds: 2700
```

### feature

There are functions that can adjust the way Chocolatey works for you
See: [https://chocolatey.org/docs/chocolatey-configuration#features](https://chocolatey.org/docs/chocolatey-configuration#features)

```yml
chocolatey_feature:
  - useRememberedArgumentsForUpgrades: false
  - usePackage0RepositoryOptimizations: false
  - useEnhancedExitCodes: false
```

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
    - arillso.chocolatey
```

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2019, Simon Bärlocher
