# Kluster

This is my deployment automation for the OS and

## Prerequisites

* An SD card with Ubuntu 20.04. `ubuntu-20.04.2-preinstalled-server-arm64+raspi.img`
* DHCP static lease reservations (listed in `inventory.yaml`)
* SSH into the system once to set password (this can probably be automated with `sshpass` and `expect`)
* The password encrypted with ansible-vault, stored in inventory.yaml and the key at `~/ansible-vault-pw` (see `ansible.cfg`)

## Hardware

The cluster currently consists of 3 Raspberry Pi 4Bs. `rpi1` has 8GB of RAM, `rpi2` and `rpi3` have 4GB. All have PoE hats and a Samsung Evo 870 2.5" SSDs connected via a Sabrent USB 3.0 SATA adapter.

## Ansible

### Usage

* Install Ansible
* Install dependencies:
    ansible-galaxy install -r requirements.yaml
* Run the playbook
    ansible-playbook kluster.yaml
* Optional - symlink ~/.kube/k3s.yml to config so `kubectl` works:
    ln -s ~/.kube/k3s.yml ~/.kube/config
