Cron
====

This role will configure cron jobs

Requirements
------------

None

Supported distributions
-----------------------

- Debian:
    - 8 (Jessie)
    - 9 (Stretch)
- CentOS:
    - 6
    - 7

Usage
-----

```yml
cronjobs:
  - { 
    name: 'echo', 
    hour: 0, 
    minute: 0,
    weekday=*
    day=*
    month=* 
    user: 'root', 
    job: 'echo "cron job" > /dev/null' 
  }
  - { 
    name: 'job to remove', 
    hour: 0, 
    minute: 0,
    weekday=*
    day=*
    month=* 
    user: 'root', 
    job: 'echo "cron job to remove" > /dev/null' 
    state=absent
  }
```

Dependencies
------------

None

Tests
-----

```
$ cd tests
$ vagrant up --provision
```