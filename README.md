Stouts.deploy
=============

[![Build Status](https://travis-ci.org/Stouts/Stouts.deploy.png)](https://travis-ci.org/Stouts/Stouts.deploy)

Ansible role which creates deploy directories and sets deploy variables, also ensures for deploy user exists
Deploy boilerplate for using in playbooks and other roles.

#### Variables

```yaml
deploy_enabled: yes                     # Enable the role
deploy_environment: develop             # Pick environment variable
deploy_user: "{{ansible_ssh_user}}"     # Set deploy user
deploy_project_name: web                # Pick a project name
deploy_dir: /usr/lib/{{deploy_project_name}} # Root deploy directory
deploy_configuration_dir: "{{deploy_dir}}/configuration" # Directory for placed configuration files
deploy_logs_dir: "{{deploy_dir}}/logs"                   # Directory for placed logs
deploy_run_dir: "{{deploy_dir}}/run"                     # Directory for run files
deploy_source_dir: "{{deploy_dir}}/source"               # Source's directory
```

#### Usage

Add `Stouts.deploy` to your roles and set variables in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.deploy

  vars:
    deploy_project_name: facebook  # ;)
    deploy_user: deploy

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.deploy/issues)!
