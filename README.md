# Nomad

[![Build Status](https://travis-ci.org/brianshumate/ansible-nomad.svg?branch=master)](https://travis-ci.org/brianshumate/ansible-nomad)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-brianshumate.nomad-blue.svg)](https://galaxy.ansible.com/brianshumate/nomad/)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/brianshumate/ansible-nomad.svg)](http://isitmaintained.com/project/brianshumate/ansible-nomad "Average time to resolve an issue")
[![Percentage of issues still open](http://isitmaintained.com/badge/open/brianshumate/ansible-nomad.svg)](http://isitmaintained.com/project/brianshumate/ansible-nomad "Percentage of issues still open")

This Ansible role performs basic [Nomad](https://nomadproject.io/)
installation, including filesystem structure, and example configuration.

It will also bootstrap a minimal cluster of 3 server nodes, and can do this
in a development environment based on Vagrant and VirtualBox. See
[README_VAGRANT.md](https://github.com/brianshumate/ansible-nomad/blob/master/examples/README_VAGRANT.md) for more details about the Vagrant setup.

## Requirements

This role requires an Arch Linux, Debian, RHEL, or Ubuntu distribution; the role is tested
with the following specific software versions:

* Ansible: 2.7.10
* nomad: 0.10.3
* Arch Linux
* CentOS: 7
* Debian: 8
* RHEL: 7
* Ubuntu: 16.04

## Role Variables

The role defines its defaults in [defaults/main.yml](defaults/main.yml).
To configure the role you will need to override the defaults in a separate file and then combine the defaults, see [defaults/example_override.yml](defaults/example_override.yml) for an example.

## Dependencies

Ansible requires GNU tar and this role performs some local use of the
unarchive module, so ensure that your system has `gtar`/`unzip` installed.
Jinja2 templates use ipaddr filter that need `netaddr` python library.

## Example Playbook

Basic nomad installation is possible using the included `site.yml` playbook:

```
ansible-playbook -i <hosts> site.yml
```

You can also simply pass variables in using the `--extra-vars` option to the
`ansible-playbook` command:

```
ansible-playbook -i hosts site.yml --extra-vars "nomad_datacenter=maui"
```

### Vagrant and VirtualBox

See `examples/README_VAGRANT.md` for details on quick Vagrant deployments
under VirtualBox for testing, etc.

## License

BSD

## Author Information

[Brian Shumate](http://brianshumate.com)

## Contributors

Special thanks to the folks listed in [CONTRIBUTORS.md](https://github.com/brianshumate/ansible-nomad/blob/master/CONTRIBUTORS.md) for their
contributions to this project.

Contributions are welcome, provided that you can agree to the terms outlined
in [CONTRIBUTING.md](https://github.com/brianshumate/ansible-nomad/blob/master/CONTRIBUTING.md)
