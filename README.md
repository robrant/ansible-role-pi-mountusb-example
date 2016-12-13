

# About

Example playbook to show how to make calls to the ansible role that mounts an external USB storage device on a Raspberry Pi.

# Dependencies

* I've only tested this on a Mac and Raspberry Pi B+ running Jessie (Dec 2016).
* You'll need Ansible on your local development machine/laptop.
* This repo uses a `git submodule` to pull in the role from ansible-role-pi-mountusb.

# Usage

* Stick an external USB storage device into one of your Pi's USB ports.

* Clone this repo

      $> git clone https://github.com/robrant/ansible-role-pi-mountusb-example.git

* Get the submodule

      $> git submodule init

* Modify `playbook.yml` as you need:

      - hosts: pis        # Don't change this unless you've changed the group in your inventory (hosts) file.
        roles:
          - mount-usb     # Don't change this unless you've made changes.
        tags: mount-usb

* Modify `hosts` file as you need; replace `pibox0` with either the hostname or IP address of your pi.

* Run it

      $> ansible-playbook -i hosts playbook.yml
