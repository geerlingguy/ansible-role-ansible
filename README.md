# Ansible Role: Ansible

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-ansible.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-ansible)

An Ansible Role that installs Ansible on RHEL/CentOS and Debian/Ubuntu.

## Requirements

If using on a RedHat/CentOS-based host, make sure you've added the EPEL repository (it can easily be installed by including the `geerlingguy.repo-epel` role on Ansible Galaxy).

## Role Variables

None.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
        - { role: geerlingguy.ansible }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
