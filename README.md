# Ansible Role: Ansible

[![CI](https://github.com/geerlingguy/ansible-role-ansible/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-ansible/actions?query=workflow%3ACI)

An Ansible Role that installs Ansible on Linux servers.

## Requirements

If using on a RedHat/CentOS/Rocky Linux-based host, make sure you've added the EPEL repository (it can easily be installed by including the `geerlingguy.repo-epel` role on Ansible Galaxy).

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    ansible_install_method: package

Whether to install Ansible via the system `package` manager (`apt`, `yum`, `dnf`, etc.), or via `pip`. If set to `pip`, you need to make sure Pip is installed prior to running this role. You can use the `geerlingguy.pip` module to install Pip easily.

    ansible_install_version_pip: ''

If `ansible_install_method` is set to `pip`, the specific Ansible version to be installed via Pip. If not set, the latest version of Ansible will be installed.

    ansible_install_pip_extra_args: ''

If `ansible_install_method` is set to `pip`, the extra arguments to be given to `pip` are listed here. If not set, no extra arguments are given.

    ansible_pip_executable: ''

if `ansible_install_method` is set to `pip`, this is the path to the pip executable, in case your platform doesn't find the right name.

    ansible_epel_repo_name: 'epel'

if `ansible_install_method` is set to `package` and you are on a RHEL machine, and your local satellite server admins decided to name the epel repository something other than epel, this variable gives you the opportunity to provide the right name.


## Dependencies

None.

## Example Playbook

Install from the system package manager:

    - hosts: servers
      roles:
        - role: geerlingguy.ansible

Install from pip:

    - hosts: servers
      vars:
        ansible_install_method: pip
        ansible_install_version_pip: "2.7.0"
        ansible_install_pip_extra_args: "--user"
      roles:
        - role: geerlingguy.pip
        - role: geerlingguy.ansible

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
