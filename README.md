# ansible-role-sfdeploy
Deploy a Symfony2 project with ansible

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
