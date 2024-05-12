VSCodium Installer
=========

[![Molecule Test](https://github.com/Guillermo-N/ansible-role-vscodium/actions/workflows/CI.yml/badge.svg)](https://github.com/Guillermo-N/ansible-role-vscodium/actions/workflows/CI.yml)

Automates the setup of [VSCodium](https://vscodium.com/), adding repositories, installing the software, and applying custom configurations.

Requirements
------------

At the moment only OS families base on `Debian` and `RedHat` are supported.The following list shows the distributions used for testing, in which the role will work. Other versions and distributions may also work.

Linux distributions:
- Ubuntu
  - 24.04 LTS (Noble Numbat)
  - 22.04 LTS (Jammy Jellyfish)
- Debian
  - 12(Bookworm)
  - 11(Bullseye)
- Rocky
  - 9
  - 8
- Fedora
  - 40
  - 39

Role Variables
--------------

### vscode_marketplace:
- **Description**: Controls whether to add Microsoft's VSCode extension marketplace.
- **Required**: No
- **Default**: `true`

### vscodium_extensions:
- **Description**: List of extensions to be installed.
- **Required**: No
- **Default**: `[]` (empty list)
- **Notes**: List of VSCode/VSCodium extensions to be installed.

### vscodium_settings:
- **Description**: JSON file with custom settings.
- **Required**: No
- **Default**: `""` (empty string)

### vscodium_keybindings:
- **Description**: JSON file with custom keybindings.
- **Required**: No
- **Default**: `""` (empty string)

### vscodium_tasks:
- **Description**: JSON file with custom tasks.
- **Required**: No
- **Default**: `""` (empty string)


Example Playbook
----------------
Minimal example:

    - hosts: localhost
      roles:
        - ansible-vscodium-installer

All variables example:

    - hosts: localhost
      roles:
        - ansible-vscodium-installer
          vscode_marketplace: false
          vscodium_extensions:
            - extension.one
            - extension.two
            - extension.three
          vscodium_settings: /path/to/code/settings
          vscodium_keybindings: /path/to/code/bindings
          vscodium_tasks: /path/to/code/tasks

License
-------

MIT

Author Information
------------------

[Guillermo N.](https://github.com/Guillermo-N)
