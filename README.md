Role Name
=========

Burp-ui-agent only role

Started since bui-agent 0.6.0
https://burp-ui.readthedocs.io/en/0.6.0/buiagent.html


Requirements
------------

You only need burp-server installed and configured.
During automatic tests I use https://github.com/CoffeeITWorks/ansible_burp2_server but you can setup burp-server in any other way.

Role Variables
--------------

Check the [defaults/main.yml](defaults/main.yml)

You can change the burpui version with vars:

```yaml
burp_agent_pip_burpui: "burp-ui-agent"
burpui_pip_packages:
  - { name: "{{ burp_agent_pip_burpui }}", version: 0.6.1 }
```

You must change the global password:

```yaml
burp_agent_global_password: "password"
```

There are other vars that you can modify.

Don't modify the role itself!!

You must have an structure where you only change your own vars on your group_vars or host_vars files.

See: https://github.com/CoffeeITWorks/ansible-generic-help/

Dependencies
------------

No dependencies, but recommended to use coffeeitworks.ansible_burp2_server to setup burp-server

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: burp_servers
      hosts: burp_servers
      roles:
        - role: ansible_burp2_server
        - role: ansible_burpui_agent

You can also use it without ansible_burp2_server role.

License
-------

BSD

Author Information
------------------

Pablo Estigarribia - pablodav at github and gmail.

Thanks

Burpui
------

Main page: https://git.ziirish.me/ziirish/burp-ui

Burp backup and restore
-----------------------

Main page: http://burp.grke.org/
