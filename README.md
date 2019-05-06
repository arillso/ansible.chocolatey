# Ansible Role: chocolatey

[![Build Status](https://travis-ci.org/arillso/ansible.chocolatey.svg?branch=master)](https://travis-ci.org/arillso/ansible.chocolatey) [![license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://sbaerlo.ch/licence) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-chocolatey-blue.svg)](https://galaxy.ansible.com/arillso/chocolatey)

## Description

Manage the Chocolatey Source list and config.

## Installation

```bash
ansible-galaxy install arillso.chocolatey
```

## Requirements

None

## Role Variables

```yml
chocolatey_source:
  - name: chocolatey
    source: https://chocolatey.org/api/v2/
    user:
    password:
    priority: 0
    state: present
```

```yml
chocolatey_config:
  - commandExecutionTimeoutSeconds: 2700
```

```yml
chocolatey_feature:
  - useRememberedArgumentsForUpgrades: true
```

```yml
chocolatey_version: 0.10.11
```

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
    - arillso.chocolatey
```

## Changelog

### 1.2.0

- add support chocolatey feature

### 1.1.0

- add support for choco config
- add change remove source when absent

### 1.0.0

- initial commit

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2018, Simon Bärlocher
