[![Build Status](https://travis-ci.com/IRMooBear/driver_rtl8812au.svg?branch=master)](https://travis-ci.com/IRMooBear/driver_rtl8812au)

Pi Driver RTL8812AU
=========

This ansible role will go through the complete process of downloading and compiling the RTL8812AU driver, loading it into kernel, ensure that it load on boot and install network interface.

Role Variables
--------------

    compile_threads: "{{ ansible_processor_cores }}"
    
Number of threads to use during compile time.    
    
    rtl8812au_version: 2807a0a2b71cc47c7483f2a9638c66438c83c5da
    
Git checkout version.    
    
    rtl8812au_mac: 000000000000
    
The Mac address of your RTL8812AU based device for configuration 
   
    rtl8812au_wpa_supplicant: yes
    
Generate WPA Supplicant file containing authentications.   
    
    rtl8812au_load_module_on_startup: no
    
Load kernel module on system boot.    
    
    rtl8812au_config_i386: yes
    rtl8812au_config_rpi: yes
    
Compile configuration, default set to compile for RPI.  Turn off RPI if you compile on i386...    
    
    rtl8812au_authentications:
      -
        ssid: ssid_name
        password: password
        key_management: WPA-PSK
        priority: 1
        id_str: ssid_name
        
A list of access point auth to generate a wpa_supplicant.conf file specific for the RTL8812AU device.  See defaults for example.        

Example Playbook
----------------

1. Make sure to set mac address if you know it
2. Set authentications variable so the wpa_supplicant configuration file can be generated from template.

    - hosts: servers
      roles:
         - { role: irmoobear.pi_driver_rtl8812au }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
