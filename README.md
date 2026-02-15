# Organization Configuration Repository (org-config)

This repository contains the configuration of a tenant in Ansible
Automation Platform. The tenant is the owner of this repository, and
they should store all configuration for their organization in this
repository. This includes

- Credentials
- Credential Types
- Project
- Inventories
- Inventory sources
- Job Templates
- Workflow Templates
- Schedules

All configuration objects should be added to the inventory. See
[inventory](inventory/group_vars/all/job_templates.yaml) for an
example.

The configuration is applied via the
[org-config](playbooks/org-config.yaml) playbook.

## Required variables

The Org config repository relies on a few variables that need to be
defined during onboarding.  Current these are extra vars for the
playbook _playbooks/org-config.yaml_ and get assigned during
onboarding.

- _aap_api_token_ for access the AAP API
- _tenant_name_ for creating objects with a distinct name

## Dependencies

This repository depends on the following Ansible collections:

- _ansible.platform_
- _ansible.controller_
- _ansible.hub_
- _ansible.eda_
- _infra.app_configuration_
