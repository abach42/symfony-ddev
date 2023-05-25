# DDEV simple set up for symfony projects

Dummy DDEV configuration to start a Symfony project.  

## DDEV Configuration for symfony

Following custom settings should be updated in your `.ddev/config.yaml` file

```
type: php
docroot: app/public
php_version: "8.0"
hooks:
post-start:
    - exec: wget https://get.symfony.com/cli/installer -O - | bash
    - exec: mv ~/.symfony/bin/symfony /usr/local/bin/symfony
```

## Installation

- Clone this repository in a directory of your choice  `git clone git@gitlab.321.works:Training/symfony/symfony-ddev.git [choice-directory]`
- Remove the current .git directory `rm -r -f [choice-directory]/.git `
- Initialize a new git repository `git init`
- Optional run `ddev config` to change your ddev project name
- DDEV `docroot` should be set to `app/public`
- **Do not create** the `app/public` Directory 
- DDEV `type` should be set to `php`
- Run ddev start

Symfony Binary is already installed in the web container. You can access symfony console directly from your 
host with `ddev symfony [flags] [args]`

At this point you can create your application however you want.

### Create aSymfony application using Symfony Binary
- If exists remove the directory `app/public` run `rm -rf app` from your project root dir
- Run `ddev symfony new app --full` to create your symfony application