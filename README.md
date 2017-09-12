# ansible-macos-softwareupdate
Ansible role that runs the macOS softwareupdate.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-softwareupdate.svg)](https://travis-ci.org/feffi/ansible-macos-softwareupdate) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-softwareupdate/total.svg)](https://github.com/feffi/ansible-macos-softwareupdate) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-softwareupdate.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-softwareupdate) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-softwareupdate.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-softwareupdate) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-softwareupdate.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-softwareupdate) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-softwareupdate/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-softwareupdate.git
  name: feffi.macos-softwareupdate
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_softwareupdate:
  # Download or install only recommended updates (true) or all available updates (false)
  recommended: true

  # Install software updates (true) or download only (false)
  install: false
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_softwareupdate:
          recommended: true
          install: false

      roles:
        - { role: feffi.macos-softwareupdate }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-softwareupdate,
            macos_softwareupdate: {
              recommended: true,
              install: false
            }
          }
```
