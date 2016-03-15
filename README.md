# Ansible demonstration

This repo contains creates a Centos testbed for Ansible playbooks

## Requirements

Vagrantfile, in which case [Vagrant 1.8.1+](https://www.vagrantup.com/downloads.html) and [VirtualBox 5.0x](https://www.virtualbox.org/wiki/Downloads) are required.

## Instructions

Assuming Vagrant is ready clone this repo locally

  vagrant up

This will create two [Centos 7](https://atlas.hashicorp.com/geerlingguy/boxes/centos7) hosts using Ansible to prepare the hosts for management by Ansible.
- ansible management host
- ansible managed host

See the 'provisioning' directory for detail.

Details on adding Ansible project to follow, this readme is incomplete.




