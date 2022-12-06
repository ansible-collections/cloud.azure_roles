azure_resource_group
==============

A role to manage Azure Resource Group. User can create or delete resource group.

Requirements
------------

* Azure User Account with valid permission

Role Variables
--------------

* **operation** - Operation to perform. Valid values are 'create', 'delete'.
* **azure_resource_group** - Resource group to create or delete.
* **azure_region** - An Azure location for the resource group to create.
* **azure_lock_resource_group** - If set to 'true', will lock the resource group created.
* **azure_tags** - Dictionary of string:string pairs to assign as metadata to the object.
* **azure_force_delete_nonempty** - Remove a resource group and all associated resources.
* **azure_force_delete_locked** - Remove a resource group even if it is locked.


Dependencies
------------

- NA

Example Playbook
----------------

    - hosts: localhost
      roles:
         - role: cloud.azure_ops.azure_manage_resource_group
           operation: "create"
           azure_region: "eastus"
           azure_resource_group: "testing-resource-group"
           azure_resource_group_tags:
             tag0: "tag0"
             tag1: "tag1"
           azure_lock_resource_group: yes

License
-------

GNU General Public License v3.0 or later

See [LICENCE](https://github.com/redhat-cop/cloud.azure_ops/blob/main/LICENSE) to see the full text.

Author Information
------------------

- Ansible Cloud Content Team