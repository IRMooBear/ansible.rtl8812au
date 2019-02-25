[![Build Status](https://travis-ci.com/IRMooBear/pi_driver_rtl8812au.svg?branch=master)](https://travis-ci.com/IRMooBear/pi_driver_rtl8812au)

Pi Driver RTL8812AU
=========

This ansible role will go through the complete process of downloading and compiling the RTL8812AU driver, loading it into kernel, ensure that it load on boot and install network interface.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- rtl8812_mac: The Mac address of your RTL8812AU based device for configuration
- rtl8812_authentications: A list of access point auth to generate a wpa_supplicant.conf file specific for the RTL8812AU device.  See defaults for example.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: irmoobear.pi_driver_rtl8812au }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
