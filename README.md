# [Ansible role mount](#ansible-role-mount)

Configure mounts

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-mount/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-mount/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-mount/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-mount)|[![downloads](https://img.shields.io/ansible/role/d/buluma/mount)](https://galaxy.ansible.com/buluma/mount)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-mount.svg)](https://github.com/buluma/ansible-role-mount/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-mount/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.mount
      mount_requests:
        - path: /mnt/tmp
          src: /tmp
          opts: bind
          fstype: none
          mode: "1777"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-mount/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-mount/blob/master/defaults/main.yml):

```yaml
---
# defaults file for mount

# The `mode`, `owner` and `group` can be set in the `mount_requests` list, but
# when not specified, these defaults are used.
mount_default_mode: "0750"
mount_default_owner: root
mount_default_group: root

# You can define mounts as variables. All parameters for the `mount` module are
# supported.

# mount_requests:
#   - path: /mnt/tmp
#     src: /tmp
#     opts: bind
#     fstype: none
#   - path: swap
#     src: /dev/data/swap
#     fstype: swap
#     opts: sw
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-mount/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-mount/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Alpine](https://hub.docker.com/r/buluma/alpine)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|
|[Kali](https://hub.docker.com/r/buluma/kalilinux)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-mount/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-mount/blob/master/LICENSE).

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)

