# `dotfiles-repo-installer-role`

[![Build Status](https://travis-ci.org/thecjharries/dotfiles-repo-installer-role.svg?branch=master)](https://travis-ci.org/thecjharries/dotfiles-repo-installer-role)


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
- src: git+https://github.com/thecjharries/dotfiles-git-role.git
- src: git+https://github.com/thecjharries/dotfiles-common-software-role.git
- src: git+https://github.com/thecjharries/dotfiles-package-installer-role.git
- src: git+https://github.com/thecjharries/dotfiles-generic-template-role.git
```

## Example Playbook

```yml
---
- hosts: all

  roles:
    - role: dotfiles-repo-installer-role
      remote_url: https://github.com/github/gitignore
      src_path: /opt/gitignore
```

## License

ISC
