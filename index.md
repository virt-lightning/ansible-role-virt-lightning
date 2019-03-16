# How to use the Ansible role ansible-role-virt-lightning

## What does it do

This is an Ansible role to install, configure and test Virt-Lightning.

Virt-Lightning can quickly deploy new virtual machines using `libvirt`. It also prepares the Ansible inventory file.

Following tasks will be executed by the role:

1. Install the virt-lightning dependencies including `git`, `libvirt`, `python` modules, `rsync` (some are distribution specific).
2. Configure libvirt on the system.
3. Create the virt-lightning environment in `~/virt-lightning`.
4. Configure virt-lightning (`~/.config/virt-lightning/config.ini`).
5. Prepare an image
6. Test that virt-lightning is able to create, run, and destroy a virtual
  machine.

## Requirements

None. You need to have root access.

## Role variables

* Skip the tests (default to false):

````
virt_lightning_run_tests: true
````

* Configure the URI of the Qemu system:

````
virt_lightning_qemu_uri: qemu:///system
````

## Dependencies

None.

## Example Playbook

````
- hosts: servers
  vars_files:
    - vars/main.yml
  roles:
    - { role: virt-lightning/ansible-role-virt-lightning }
````

## License

To be defined.

## Author Information

This role was created in 2019 by Goneri Le Bouder.

