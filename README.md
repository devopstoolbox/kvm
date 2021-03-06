Role Name
=========

kvm

[![Build Status](https://travis-ci.org/cmihai-ansible/kvm.svg?branch=master)](https://travis-ci.org/cmihai-ansible/kvm)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.kvm](https://galaxy.ansible.com/devopstoolbox.kvm)

```bash
ansible-galaxy install devopstoolbox.kvm
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```
kvm_enable_service: true
kvm_enable_selinux: true
kvm_users:
 - user: devops
   group: libvirt
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install kvm on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: kvm is configured
      import_role:
        name: devopstoolbox.kvm
      vars:
        kvm_enable_service: true
        kvm_enable_selinux: true
        kvm_users:
         - user: devops
           group: libvirt
      tags: kvm
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/crivetimihai)
