Ansible Role: Common
=========
[![Build Status](https://travis-ci.org/cmprescott/ansible-role-common.svg?branch=master)](https://travis-ci.org/cmprescott/ansible-role-common)

Installs and configures the following common applications on Debian, Elementary OS, Ubuntu, & OS X. This is a living project. I tend to add things as I need them on my computers.

- **File**: `unzip`, `unrar`
- **Networking**: `curl`, `netcat`, `wget`  
- **Programming**: `git`, `vim`
- **Terminal**: `bash`, `byobu`, `locate`, `sudo`, `tree`

Requirements
------------

```shell
# Ansible version 1.4.4+
ansible --version

# Linux needs apt, OS X needs homebrew cask
case $OSTYPE in
  "linux"*)
      apt --version;;
  "darwin"*)
      brew cask --version;;
esac
```

Role Variables
--------------

```yaml
# ----- bash -----
common_bash_aliases:
  - "ll='ls -alF'"
  - "la='ls -A'"
  - "l='ls -CF'"
  - "vi='vim'"
  - "grep='grep --color=auto'"
  - "fgrep='fgrep --color=auto'"
  - "egrep='egrep --color=auto'"

# ----- byobu -----
common_byobu_widgets_left: [ logo, release, session  ]
common_byobu_widgets_right: [ reboot_required, updates_available, uptime, cpu_temp, load_average, cpu_count, cpu_freq, memory, disk, date, time ]
common_byobu_windows: []

# ----- platform dependent -----
__common_packages: [ unzip, unrar, curl, git, netcat, wget, bash, byobu, locate, sudo, tree, vim ]
__common_package_path: (/usr/ | /usr/local/ depending on platform)

```

Dependencies
------------

None

Example Playbook
----------------

    - hosts: all
      roles:
         - role: cmprescott.common

License
-------

BSD

Author Information
------------------

Prescott Chris
