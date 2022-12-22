# Install

[![Lint](https://github.com/ga-lep/install/actions/workflows/ansible-lint.yml/badge.svg?branch=main)](https://github.com/ga-lep/install/actions/workflows/ansible-lint.yml)

Ansible playbooks to setup initial configurations, install various utilities, and security tools to localhost.

## Playbooks
I needed something to install tools quickly after a new fresh OS install.

## Dependencies
Packages to be installed prior to running the playbooks.

```bash
$ apt update
$ apt -y install python-apt ansible
```

### Examples
Perform a dry run:

```bash
$ sudo ansible-playbook playbook.yml --check
```

List tasks or tags:
```bash
$ sudo ansible-playbook playbook.yml --list-tasks
```

Install or skip specific tasks:
```bash
$ sudo ansible-playbook play_apt.yml --tags "deb-utils,rust"
$ sudo ansible-playbook play_apt.yml --skip-tags "kitty"
```

Run playbook and all install tools to localhost:

```bash
$ sudo ansible-playbook play_apt.yml
```
