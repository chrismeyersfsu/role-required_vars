# role-required_vars
Ansible role to enforce required variables

# Example playbook

```
- hosts: local
  vars:
    - one: 1
    - two: 2
    - three: ''
    - required_vars:
      - 'one'
      - 'two'
      - 'three'
  roles:
    - { role: required_vars }
```

```
- name: "Only check for variabled defined, not blank"
  hosts: local
  gather_facts: false
  vars:
    - one: 1
    - two: 2
    - three: ''
    - required_vars_defined:
      - 'one'
      - 'two'
      - 'three'
  roles:
    - { role: required_vars }
```
