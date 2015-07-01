# ansible-role-sfdeploy

Deploy a Symfony2 project with ansible

##Requirements

* Ansible 1.7.2+

##Install

Add to your roles.yml

```yml
- src: https://github.com/maximecolin/ansible-role-sfdeploy
  version: master
  name: maximecolin.sfdeploy
```

Run

```ansible-galaxy install -r ansible/roles.yml -p ansible/roles -f```

## Configuration

Create a deploy playbook

```yml
---

- hosts: prod

  roles:
    - { role: maximecolin.sfdeploy }
```

Configure deploy vars

```yml
sfdeploy:
  root: /srv/my-project
  repository: git@github.com:my-vendor/my-project.git
  branch: master
  shared_files:
    - app/config/parameters.yml
  shared_directories:
    - var/logs
    - vendor
    - web/uploads
  files_to_remove:
    - web/app_dev.php
  writable_directories:
    - var/cache
    - var/logs
    - web/uploads
    - web/media/cache
  run_migration: false
  create_database: true
  acl_user: www-data
```

## Run

```ansible-playbook ansible/deploy.yml -i ansible/hosts -l prod```

## Improvement

This role implement my needs, several improvements and features will come in the future.
