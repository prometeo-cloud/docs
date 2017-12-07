# How to create a Service Account for Automating OCP


### How to create a token

```bash
# log in as sys admin
$ oc login -u system:admin

# creates a service account
$ oc create sa automator

# adds the account to the admin role
$ oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:default:automator

# gets the value of the token using the name
$ oc serviceaccounts get-token automator
```

### How to check access rights

```bash
$ oc get sa automator -o yaml
$ oc policy who-can create ProjectRequest
```

