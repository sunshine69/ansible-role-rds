rds
===

Manage RDS instances, parameter groups, option groups etc.

Requirements
------------


Role Variables
--------------

* `rds_subnet_group` (dict) - subnet group used by DB.
  Contains:
    - `name` (string) - subnet group name
    - `description` (string) - subnet group description 

* `rds_option_group` (dict) - option group used by DB.
  Contains:
    - `name` (string) - option group name
    - `engine_name` (string) - DB engine used
    - `major_engine_version` (string) - version of engine
    - `description` - description of option group
    - `apply_immediately` (boolean) - whether to apply changes to the option group immediately

* `rds_parameter_group` (dict) - parameter group used by DB.
  Contains:
    - `name` (string) - parameter group name
    - `description` - description of parameter group
    - `params` (list) - list of parameters for the group
    - `apply_immediately` (boolean) - whether to apply changes to the parameter group immediately

* `rds_db_instances` (list) - list of database instances to manage
  Each DB instance contains:
    - `db_instance_identifier` (string) - name of the DB instance
    - `engine` (string) - engine used by the DB
    - `engine_version` (string) - version of DB engine
    - `db_instance_class` (string) - instance type of the DB
    - `master_user_name` (string) - DB username
    - `master_user_password` (string) - DB password
    - `allocated_storage` (int) - number of GBs to allocate for storage
    - `storage_type` (string) - type of storage to use
    - `multi_az` (boolean) - whether to make the DB highly available across AZs
    - `wait` (boolean) - whether to wait until the DB is available before continuining
    - `wait_timeout` (int) - number of seconds to wait
    - `tags` (dict) - dict of tag keys and values

* `rds_force_password_update` (boolean) - whether to force the update of the DB password. This
  defaults to `False`, and is typically passed on the command line when you know you need to change
  a password.


Dependencies
------------


Example Playbook
----------------


License
-------

XVT internal use

Author Information
------------------
