SSH Keys
=========

[![Build Status](https://travis-ci.org/ucsdlib/ansible-role-ssh-keys.svg?branch=master)](https://travis-ci.org/ucsdlib/ansible-role-ssh-keys)

Installs one or more SSH keys for UC San Diego Library staff to a user or role
account on a given host(s).

Currently supports:
* Centos7/RHEL
* Ubuntu 16.04 LTS

Requirements
------------

No external requirements.

Dependencies
------------

No external roles are required.

Role Variables
--------------

* `ssh_keys_ad_account`: Active Directory account to assign SSH keys to
  (`ansible_user_id`)
* `ssh_keys_github_accounts`: GitHub account(s) to add to `authorized_keys`

Example Playbooks
----------------

Simple example of a single user setup for a host:
```
    - hosts: servers
      roles:
         - { role: ucsdlib.ansible-role-ssh-keys,
             ssh_keys_user: 'mcritchlow'
           }
```

Role account setup for a host:
```
    - hosts: servers
      roles:
         - { role: ucsdlib.ansible-role-ssh-keys,
             tags: ssh-keys,
             ssh_keys_user: 'conan',
             ssh_keys_ad_usernames: ['mcritchlow','jhriv','tchu']
           }
```

Library Staff Map
----------------
Since AD usernames do not map 1:1 with GitHub usernames, here is a mapping to
use when setting up SSH keys for a given role/account. Note this is also stored
as a map in `defaults/main.yml` as `ssh_keys_map`

```
- { ad_username: "tchu", github_username: "VivianChu" }
- { ad_username: "lsitu", github_username: "lsitu" }
- { ad_username: "hweng", github_username: "hweng" }
- { ad_username: "drtrujillo", github_username: "dt-ucsd" }
- { ad_username: "mcritchlow", github_username: "mcritchlow" }
- { ad_username: "jhriv", github_username: "jhriv" }
- { ad_username: "aflick", github_username: "allisonflick" }
- { ad_username: "tmarconi", github_username: "tmarconi" }
- { ad_username: "rstanonik", github_username: "rstanonik" }
- { ad_username: "jgorney", github_username: "jgorney" }
```

License
-------

BSD 2

Author Information
------------------

UC San Diego Library Development and Operations teams.

