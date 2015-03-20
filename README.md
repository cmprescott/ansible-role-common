Role Name
=========

Installs and configures the following common applications on Debian/Ubuntu & OS X.

- **File**
  - unzip
  - unrar
- **Networking**  
  - curl
  - git
  - netcat
  - wget
- **Terminal**
  - bash
  - byobu
  - locate
  - sudo
  - tree
  - vim

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

```yaml
# -------------
# bash
# -------------
common_bash_aliases:
  - "alias ll='ls -alF'"
  - "alias la='ls -A'"
  - "alias l='ls -CF'"
  - "alias vi='vim'"
# -------------
# byobu
# -------------
common_byobu_widgets_left:
  - logo
  - release
  - session
common_byobu_widgets_right:
  - reboot_required
  - updates_available
  - uptime
  - cpu_temp
  - load_average
  - cpu_count
  - cpu_freq
  - memory
  - disk
  - date
  - time
common_byobu_windows: []
# -------------
# platform dependent
# -------------
__common_packages: [ unzip, unrar, curl, git, netcat, wget, bash, byobu, locate, sudo, tree, vim ]
__common_byobu_bin: /usr/bin/byobu-launch

```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - role: common

License
-------

BSD

Author Information
------------------

Prescott Chris
