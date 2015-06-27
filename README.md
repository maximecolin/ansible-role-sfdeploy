# ansible-symfony-deploy
Deploy a Symfony2 project with ansible

```yml
deploy:
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
  acl_user: www-data
```
