# pamd_ldap ansible

This role setups and configures the pam ldap module


## Requirements

This role requires and apt based system


## Role Variables

### General

| Name                    | Required/Default                    | Description                                                                                                                                                                                               |
|-------------------------|:-----------------------------------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `pamd_ldap_nslcd_conf`  | `{'uid': 'nslcd', 'gid': 'nslcd' }` | Dict containing the option key/value pairs. According to [the nslcd.conf man page](https://linux.die.net/man/5/nslcd.conf). If a value can be defined multiple times just use a list containg all values. |
| `pamd_ldap_access_conf` | `[]`                                | List containing Dicts with access settings. According to [the access.conf man page](https://linux.die.net/man/5/access.conf).                                                                             |

### `pamd_ldap_access_conf`
Each list entry has to have following attributes
| Name         | Required/Default   | Description                                                                                                                                                                                                                                                                                                                                              |
|--------------|:------------------:|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `permission` | :heavy_check_mark: | Can be either a "+" character (plus) for access granted or a "-" character (minus) for access denied.                                                                                                                                                                                                                                                    |
| `object`     | :heavy_check_mark: | The users/group field, should be a list of one or more login names, group names, or ALL (which always matches). To differentiate user entries from group entries, group entries should be written with brackets, e.g. (group).                                                                                                                           |
| `origins`    | :heavy_check_mark: | The origins field, should be a list of one or more tty names (for non-networked logins), host names, domain names (begin with "."), host addresses, internet network numbers (end with "."), internet network addresses with network mask (where network mask can be a decimal number or an internet address also), ALL (which always matches) or LOCAL. |

For more information please see [the access.conf man page](https://linux.die.net/man/5/access.conf).


## Example Playbook

```yml
- hosts: pamd_ldap
  roles:
    - role: pamd_ldap
      pamd_ldap_mysql_password: password
      pamd_ldap_default_password: password
      pamd_ldap_default_email: admin@example.com
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).


## Author Information

 * [Fritz Otlinghaus(Scriptkiddi)](https://github.com/Scriptkiddi) _fritz.otlinghaus@stuvus.uni-stuttgart.de_
