Semaphore
=========
This role deploys [Semaphore](https://github.com/CastawayLabs/semaphore), an open source alternative to Ansible Tower

Requirements
------------
This role has been written with [SmartOS](https://smartos.org) in mind, and is designed to be deployed to a [zone](https://wiki.smartos.org/display/DOC/Zones), for use as a server.
However, if popular demand shows, I'll happily add in support for other operating systems.

Role Variables
--------------
All variables have sensible defaults, which can be found in `defaults/main.yml`.
The current version includes the following variables:

| Name               | Default Value | Description                  |
|--------------------|---------------|------------------------------|
| semaphore_user_name  | semaphore | username to run the Semaphore service |
| semaphore_group_name | semaphore | groupname to run the Semaphore service |
| semaphore_user_uid | 1000 | UID of the Semaphore service user |
| semaphore_group_gid | 1000 | GID of the Semaphore service group |
| semaphore_user_home | /opt/{{ semaphore_user_name }} | home directory for the Semaphore service user |
| semaphore_follow_git | false | ensure Semaphore source follows HEAD from Git |
| semaphore_redis_port | 6379 | the port redis is listening on |
| semaphore_redis_host | 127.0.0.1 | the address redis is listening on |
| semaphore_redis_key | ~ | the redis key |
| semaphore_use_analytics | "false" | |
| semaphore_is_ssl | "false" | |
| semaphore_newrelic_key | ~ | New Relic key |
| semaphore_bugsnag_key | ~ | Bugsnag key |
| semaphore_smtp_user | ~ | SMTP username
| semaphore_smtp_pass | ~ | STMP password |
| semaphore_mongo_db | "mongodb://127.0.0.1/semaphore" | MongoDB database |
| semaphore_mongo_auto_reconn | "true" | |
| semaphore_mongo_native_parser | "true" | |
| semaphore_mongo_srv_auto_reconn | "true" | |
| semaphore_port | 3000 | |


Example Playbook
----------------

    - hosts: semaphore_servers
      roles:
        - role: cmacrae.semaphore

Or, passing parameter values:

	- hosts: semaphore_servers
	  roles:
	    - { role: cmacrae.semaphore, semaphore_user_name: test, semaphore_group_name: test }
License
-------
MIT

Author Information
------------------
Created by [Calum MacRae](http://cmacr.ae)

Feel free to:  
Contact me - [@calumacrae](https://twitter.com/calumacrae), [mailto:calum0macrae@gmail.com](calum0macrae@gmail.com)  
[Raise an issue](https://github.com/cmacrae/ansible-semaphore/issues)  
[Contribute](https://github.com/cmacrae/ansible-semaphore/pulls)  
