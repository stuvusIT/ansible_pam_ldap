# pamd_ldap ansible

This role setups and configures the pam ldap module


## Requirements

This role requires and apt based system


## Role Variables

### General

| Name                       | Required/Default                     | Description                                                        |
|----------------------------|:------------------------------------:|--------------------------------------------------------------------|
| `pamd_ldap_user`           | `nslcd`                              | User for running nslcd.                                            |
| `pamd_ldap_group`          | `nslcd`                              | Group for running nslcd.                                           |
| `pamd_ldap_uri`            | :heavy_check_mark:                   | The location at which the LDAP server(s) should be reachable,      |
| `pamd_ldap_base`           | :heavy_check_mark:                   | The search base that will be used for all queries.                 |
| `pamd_ldap_version`        | `3`                                  | The LDAP protocol version to use.                                  |
| `pamd_ldap_binddn`         | :heavy_multiplication_x:             | The DN to bind with for normal lookups.                            |
| `pamd_ldap_bindpw`         | :heavy_multiplication_x:             | The passwod for the DN to bind to.                                 |
| `pamd_ldap_rootpwmoddn`    | :heavy_multiplication_x:             | The DN used for password modifications by root.                    |
| `pamd_ldap_ssl`            | `true`                               | Enable or disable ssl usage.                                       |
| `pamd_ldap_tls_reqcert`    | `never`                              | Specifies what checks to perform on a server-supplied certificate. |
| `pamd_ldap_tls_cacertfile` | `/etc/ssl/certs/ca-certificates.crt` | Path to ca certificate to validate tls certificate.                |
| `pamd_ldap_scope`          | `sub`                                | The search scope.                                                  |

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
