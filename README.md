[![GoKEV](http://GoKEV.com/GoKEV200.png)](http://GoKEV.com/)

<div style="position: absolute; top: 40px; left: 200px;">

# GoKEV-cisco-config-templated
This project is an Ansible role to configure Cisco switches


## Example Playbooks
Here's an example of how you could launch this role


<pre>---
----
- name: Config with cisco
  hosts: all
  gather_facts: no
  connection: local

  roles:
  - GoKEV.cisco-config-templated

</pre>

## With a requirements.yml that looks as such:

<pre>
---
- name: GoKEV.cisco-config
  version: master
  src: https://github.com/GoKEV/GoKEV-cisco-config-templated.git
</pre>


## And variables as such:

<pre>

---
# defaults file for cisco
## Do not declare VLAN1 here because it already exists as default.
## That will mess with the idempotent nature and report change
vlans:
  - vlan_id: 10
    vlan_name: VLAN1
  - vlan_id: 20
    vlan_name: VLAN2


access_ports:
  - interface: GigabitEthernet0/1
    vlan: 10
    description: Demo Access Port
trunk_ports:
  - interface: GigabitEthernet0/2
    vlans_allowed: 10,20
    native_vlan: 1
    description: Demo Trunk Port

</pre>


## Troubleshooting & Improvements

- Not enough testing yet

## Notes

  - Not enough testing yet

## Author

This project was created in 2018 by [Kevin Holmes](http://GoKEV.com/).


