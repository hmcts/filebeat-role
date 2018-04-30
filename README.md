Role Name
=========

Installs and configures filebeat to send logs to the ELK cluster

Requirements
------------

ELK cluster needs to be up

Role Variables
--------------

Prospectors must be defined, as a list of files to parse, for example:

prospectors:
  - {"name": "/var/log/messages" ,
     "input_type":"log" ,
     "tags":"['test']" ,
     "fields":{ "team" : "devops" ,
                "product" : "elk" ,
                "service" : "logs" ,
                "environment": "dev"
              }
     }


Dependencies
------------

ELK cluster needs to be up

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: filebeat,
             prospectors:
               - name: /var/log/messages
                 input_type: log
                 tags: "['test', 'more tags']"
                 fields:
                    team: divorce
                    product: divorce
                    service: petition store
                    environment: dev
            }

License
-------

MIT

Author Information
------------------

DevOps @ Reform MoJ
