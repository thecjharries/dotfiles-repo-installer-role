# `dotfiles-role-repo-installer`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-role-repo-installer.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-role-repo-installer)
[![GitHub tag](https://img.shields.io/github/tag/thecjharries/dotfiles-role-repo-installer.svg)](https://github.com/thecjharries/dotfiles-role-repo-installer)


## Requirements

Fedora 27 is recommended.

## Role Variables

Defaults are below.

```yml
---
repo_owner: root
repo_group: root
repo_become: yes
recursive_pull: no
desired_version: HEAD
```

Additionally, these variables must be set:

```yml
remote_url
src_path
```

## Dependencies

```yml
---
- src: git+https://github.com/thecjharries/dotfiles-role-git.git
- src: git+https://github.com/thecjharries/dotfiles-role-common-software.git
- src: git+https://github.com/thecjharries/dotfiles-role-package-installer.git
- src: git+https://github.com/thecjharries/dotfiles-role-generic-template.git
```

## Example Playbook

```yml
---
- hosts: all

  roles:
    - role: dotfiles-role-repo-installer
      remote_url: https://github.com/github/gitignore
      src_path: /opt/gitignore
```

## License

ISC
