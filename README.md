# ansible-barricade

A simple Ansible role for integrating Barricade.

## Installation

To install the `ansible-barricade` role via the `ansible-galaxy` command:

```
$ ansible-galaxy install https://github.com/barricadeio/ansible-barricade
```

## Usage

You'll need your *Barricade Automation Key*. This can be retrieved by visiting
[your team page](https://app.barricade.io/dashboard/settings/team/profile).

Create a task like:

`barricade.yml`

```yml
---
- name: Install Barricade
  hosts: all
  sudo: yes
  roles:
    - role: ansible-barricade
      barricade_automation_key: <Barricade Automation Key>
```

Run with `ansible-playbook barricade.yml` and it should be set up.

To remove Barricade, you can set the `barricade_state` attribute:

```yml
---
- name: Install Barricade
  hosts: all
  sudo: yes
  roles:
    - role: ansible-barricade
      barricade_state: absent

```

## Configuration

You can completely instrument configuration via the variables in `defaults/main.yml`.
