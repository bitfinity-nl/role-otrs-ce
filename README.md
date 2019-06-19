# role-otrs-ce
((OTRS)) Community Edition Open Source Help Desk Software and free features


http://<your ip>/otrs/installer.pl

Example Playbook
----------------

This is an example how to use the role:

  - hosts: lab-ubt01
    become: yes
 
    vars:
      # -- custom settings: ansible-role-mysql-5.7 --
      MySQL_ROOT_ACCOUNT  : '{{ def_mysql_user }}' 
      MySQL_ROOT_PASSWORD : '{{ def_mysql_pass }}'   

      # -- custom settings: role-otrs-ce --
      otrs_sys_user       : '{{ MySQL_ROOT_ACCOUNT }}'
      otrs_sys_pass       : '{{ MySQL_ROOT_PASSWORD }}'
      otrs_db_name        : 'otrs' 
      otrs_db_user        : 'otrs'
      otrs_db_pass        : 'password'

    roles:
      - ansible-role-mysql-server-5.7
      - role-otrs-ce

    tasks:
