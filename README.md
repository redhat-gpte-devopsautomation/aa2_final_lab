1. Create OpenStack credtial
1. Create SSH credential
1. Create Project pointed at git repo
1. Create Inventory pointing to git repo's hosts file
1. Create Template for provision.yml using git repo's hosts file
1. Create Dynamic Inventory pulling from OpenStack
1. (**Optional**) Create Groups for app_server, database_server, load_balancers, internal pointing to meta-*group_name*_AnsibleGroup groups (Run provision.yml to create the meta-* groups)
1. Create Templates for database.yml, app.yml, load_balancers.yml, smoke_tests.yml, and destroy.yml using dynamic inventory with privilege escalation


1. Create a workflow that will execute the following sequence. If any job fails, call destroy.yml
```
provision.yml -> database.yml -> app.yml -> smoke_tests.yml
                -> load_balancers.yml ->
```