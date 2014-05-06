Stouts.base
===========

[![Build Status](https://travis-ci.org/Stouts/Stouts.base.png)](https://travis-ci.org/Stouts/Stouts.base)

Ansible role which creates base directories and sets base variables, also ensures for deploy user exists

#### Variables

```yaml
base_environment: develop                   # set environment variable
base_deploy_user:                           # create and set deploy user
    name: vagrant
    password: vagrant
base_project_name: stout                    # set varibale with project name
base_deploy_directory: /usr/lib/{{ base_project_name }}  # create and set project deployment directory
base_configuration_directory: "{{base_deploy_directory}}/configuration"  # create and set project configuration directory
base_logs_directory: "{{base_deploy_directory}}/logs"  # create and set project logs directory
base_run_directory: "{{base_deploy_directory}}/run"  # create and set project run directory
base_source_directory: "{{base_deploy_directory}}/source"   # set variable with source directory
```

#### Usage

Add `Stouts.base` to your roles and set variables in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.base

  vars:
    base_project_name: facebook  # ;)

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.base/issues)!
