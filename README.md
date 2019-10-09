
## Example Usage

```
- hosts: localhost

  pre_tasks:

    - name: ntp is absent
      when: ansible_distribution_version is version('7.0', '>=')
      package:
        name:
          - ntp
          - ntpdate
        state: absent

  roles:

    - role: mafalb.chrony
      when: ansible_distribution_version is version('7.0', '>=')
```

## Variables

```
ntp_servers:
  - hostname: bla.example.com
    iburst: true		# default false
```
