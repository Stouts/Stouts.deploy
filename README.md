Stouts.base
===========

[![Build Status](https://travis-ci.org/Stouts/Stouts.base.png)](https://travis-ci.org/Stouts/Stouts.base)

Ansible role which creates base directories and sets base variables, also ensures for deploy user exists

#### Variables

```yaml
base_enabled: yes                     # Enable the role
base_environment: develop             # Pick environment variable
base_deploy_user: vagrant             # Set deploy user
base_project_name: stout              # Pick a project name
base_deploy_directory: /usr/lib/{{ base_project_name }}                 # Main project's directory
base_configuration_directory: "{{base_deploy_directory}}/configuration" # Directory for placed configuration files
base_logs_directory: "{{base_deploy_directory}}/logs"                   # Directory for placed logs
base_run_directory: "{{base_deploy_directory}}/run"                     # Directory for run files
base_source_directory: "{{base_deploy_directory}}/source"               # Source's directory
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
