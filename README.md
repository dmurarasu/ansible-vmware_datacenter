# VMware manage vCenter datacenters
Ansible roles that manages datacenters in vCenter Server

The configuration of the role is done so that it shouldn't be necessary to
modify the role for any configuration.
All settings can be configured by changing role parameters or by declaring new
config as variable.

Please report any issues or send PR.

## Examples
```yaml
---

- name: Example of how to add a couple datacenters
  hosts: vcenter
    vars:
      vcenter_auth:
        hostname: 192.0.2.1
        username: administrator@abc.lan
        password: super_pass
        validate_certs: False

      vmware_datacenter:
        - name: colo1
          state: present
        - name: colo2
          state: present
  roles:
    - ansible-vmware_datacenter  

  ```

## Role variables
```yaml
# ---------------------------------------------------------------------------
# Define the vcenter auth details to be used
# ---------------------------------------------------------------------------
vcenter_auth: { }


# ---------------------------------------------------------------------------
# Define the vmware datacenters details to be added/removed
# ---------------------------------------------------------------------------
vmware_datacenters { }
```

## License
Apache

## Author
Dan Murarasu
