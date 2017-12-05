# How to consume a subscription using subscription-manager

```bash
# get an activation key for your subscription from your administrator

# register using organisation id and activation key
$ subscription-manager register —org= —activation key=

# write pools ids into a file for later inspection
$ subscription-manager list —all —available >> subs.txt

# find the required pool id
$ cat subs.txt

# attach to a pool id
$ subscription-manager attach —pool=<id>

# list consumed subs
$ subscription-manager list —consumed

```