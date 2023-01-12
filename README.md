# Cisco Model Driven Devops Ansible Collection

This Ansible Collection is an implementation of Model-Driven DevOps and includes the following roles:
* [oc](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/oc/README.md)
* [check](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/check/README.md)
* [validate](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/validate/README.md)
* [common](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/common/README.md)
* [netbox](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/netbox/README.md)
* [nso](https://github.com/model-driven-devops/ansible-mdd/blob/main/roles/nso/README.md)

## Dependancies
### Environmnet Variables
If using NetBox:
- `NETBOX_API`
- `NETBOX_TOKEN`

To use an external NSO (ie. not deployed in CML):
- `NSO_URL` Protocol, FQDN or IP address and port (ex. `http://192.168.1.100:8080`)
- `NSO_USERNAME`
- `NSO_PASSWORD`

## Playbooks



### Status Check Operations

#### `ciscops.mdd.run_check_list`

    - Run the list of checks defined in `check_list`

##### Required Data Structures

- `check_list`: List of checks to run
- `check_table`: Dictionary defining the checks

> Note: See default values in roles/check/defaults/main.yml


### `ciscops.mdd.update_netbox_from_nso`

    - Update Netbox from NSO

Example:
```
ansible-playbook ciscops.mdd.update_netbox_from_nso
```

### `ciscops.mdd.netbox_init`

    - Initialize Netbox

Example:
```
ansible-playbook ciscops.mdd.netbox_init
```

> Note: Netbox modules to not work with Ansible <4, so the entire path will need to be specified when running with Ansible <3



### `ciscops.mdd.netbox_init`

- Initialize Netbox

ansible-playbook ciscops.mdd.netbox_init

### `ciscops.mdd.cml_update_netbox`

- Add hosts from CML into netbox

Inventory Source: CML

Example:
```
ansible-playbook cml_update_netbox
```

### `ciscops.mdd.nso_update_netbox`

- Update Netbox devices from NSO

Example:
```
ansible-playbook nso_update_netbox
```

### `ciscops.mdd.nso_init`

- Initialize NSO

Example:
```
ansible-playbook nso_init
```

### `ciscops.mdd.nso_update_devices`

- Update NSO devices from inventory source

Example:
```
ansible-playbook nso_update_devices
```
