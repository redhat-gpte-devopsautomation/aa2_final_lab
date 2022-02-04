1. Create OpenStack credtial
1. Create SSH credential
1. Create Project pointed at git repo
1. Create Inventory pointing to git repo's hosts file
1. Create Template for provision.yml using git repo's hosts file
1. Create Dynamic Inventory pulling from OpenStack
1. Run provision.yml
1. Create Groups for app_server, database_server, load_balancers, internal pointing to meta-*group_name*_AnsibleGroup
1. Create Template for database.yml using dynamic inventory with privilege escalation
1. Create Template for app.yml using dynamic inventory with privilege escalation


1. Create a workflow
provision.yml -> database.yml -> app.yml -> smoke_tests.yml
              -> load_balancers.yml ->