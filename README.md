# ansible-laptop_config

[![Lint](https://github.com/edgester/ansible-laptop_config/actions/workflows/lint.yaml/badge.svg)](https://github.com/edgester/ansible-laptop_config/actions/workflows/lint.yaml)

ansible playbook to configure my personal environment

This is an ansible playbook that configures my personal Linux environment.

## Prerequisites

You must install git and ansible before running this playbook.

## Using this playbook

Download the git repo:

    git clone https://github.com/edgester/ansible-laptop_config.git
    cd ansible-laptop_config

Install the ansible collections and roles:

   ./pre-flight

Edit group_vars/all.yml to suit your needs. Be sure to change the following
variables:

  * dotfiles_repo  - the path/URL to your dotfiles git repo
  * dotfiles_repo_version - the git reference to check out (i.e. main)
  * dotfiles_files - A list of files to symlink form the dotfiles repo into
    dotfiles_home

Run it:

  ./run
