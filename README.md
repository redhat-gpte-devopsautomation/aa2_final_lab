1. Create OpenStack credtial
1. Create SSH credential
1. Create Project pointed at git repo
1. Create Inventory pointing to git repo's hosts file
1. Create Template for provision.yml using git repo's hosts file
1. Create Dynamic Inventory pulling from OpenStack
1. (**Optional**) Create Groups for app_server, database_server, load_balancers, internal pointing to meta-*group_name*_AnsibleGroup groups (Run provision.yml to create the meta-* groups)
    a. If the inventory is set to override, which will result in a cleaner inventory, the group may get deleted if all hosts with that tag are removed. To support this situation, all playbooks support both *group_name* and meta-*group_name*_AnsibleGroup
1. Create Templates for database.yml, app.yml, load_balancers.yml, smoke_tests.yml, and destroy.yml using the dynamic OpenStack inventory with privilege escalation


1. Create a workflow that will execute the following sequence. If any job fails, call destroy.yml
```
provision.yml -> database.yml -> app.yml -> smoke_tests.yml
                -> load_balancers.yml ->
```