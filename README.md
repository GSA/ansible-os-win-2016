Windows Server 2016 GSA Benchmark
=================================

This Ansible content will configure a Windows Server 2016 machine to be GSA compliant.

This role **will make changes to the system** that could impact its performance and/or availability.

For configuration compliance auditing, use a tool such as [Nessus](https://www.tenable.com/products/nessus-vulnerability-scanner) or [CIS-CAT](https://learn.cisecurity.org/cis-cat-landing-page)

This hardening content is based on the GSA Microsoft Windows Server 2016 Security Benchmark v1.0 and the [CIS Microsoft Windows Server 2016 Benchmark v1.0.0 ](https://www.cisecurity.org/cis-benchmarks/).

Important Information
---------------------

Before executing, you should carefully review the playbook tasks to make sure your systems will not be negatively impacted.

Please thoroughly review to ensure your organizational requirements are met.

##### The current default configuration will:
* Configure all Windows Firewall controls except for "Ensure 'Windows Firewall - Public - Inbound connections' is set to 'Block (default)'"
* Configure Windows Update controls

##### The configuration will not:
* Set the 'Minimum password length' to 16 or more characters
* Configure 'Deny access to this computer from the network' to include local accounts
* Configure 'Deny log on through Remote Desktop Services' to include local accounts


Dependencies
------------
Ansible > 2.4


Example Playbook
-------------------------
```
---
- name: Harden Server
  hosts: all
  roles:
       - ansible-os-win-2016
  tasks:
```
How to test locally
--------------------------
```
ansible-playbook main.yml --connection=local
```

License
-------
MIT
