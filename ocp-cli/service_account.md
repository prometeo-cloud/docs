# How to create a Service Account for Automating OCP

```bash
# logs as a sysadmin
$ oc login -u system:admin

# switches to the default project
oc project default

# creates a service account to be used 
oc create serviceaccount automator

# add the role cluster-admin to the user
oc policy add-role-to-user cluster-admin automator

# get the token
oc describe sa automator | grep Tokens
```

