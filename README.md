# role-required_vars
Error out if `required_vars` are not defined or blank ('').
Error out if `required_vars_defined` are not defined.
Error out if `required_vars_blank` are blank.

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
