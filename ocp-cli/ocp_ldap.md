# How to set up OCP to authenticate from LDAP

### master-config.yml

```yaml
  identityProviders:
  - name: "my_ldap_provider"
    challenge: true
    login: true
    provider:
      apiVersion: v1
      kind: LDAPPasswordIdentityProvider
      attributes:
        id:
        - dn
        email:
        - mail
        name:
        - cn
        preferredUsername:
        - uid
      bindDN: "cn=directory manager"
      bindPassword: "password_here"
      insecure: true
      url: "ldap://ldap_host_name_here:389/cn=users,cn=accounts,dc=eu-west-2,dc=compute,dc=internal?uid"
```

# Ansible Inventory:

```bash
openshift_master_identity_providers=[{'name': 'RHIDM', 'challenge': 'true', 'login': 'true', 'kind': 'LDAPPasswordIdentityProvider', 'attributes': {'id': ['dn'], 'email': ['mail'], 'name': ['cn'], 'preferredUsername': ['uid']}, 'bindDN': 'cn=directory manager', 'bindPassword': 'password_here', 'insecure': 'true', 'url': 'ldap://ldap_hostname_here:389/cn=users,cn=accounts,dc=eu-west-2,dc=compute,dc=internal?uid'}]
```