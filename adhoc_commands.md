Syntax --

    $ ansible [pattern] -m [module] -a "[module options]"

ping module

    ansible all -m ping

Other noramal linux commands can be passed as -a (arguments)

    ansible all -a hostname

    ansible all -a uptime

    ansible app -a free

    ansible app -a "yum install -y docker-engine"


By using a different user

    /usr/bin/ansible will default to running from your user account. To connect as a different user:

    $ ansible atlanta -a "/sbin/reboot" -f 10 -u username

To Copy files

    $ ansible localhost -m ansible.builtin.copy -a "src=/etc/hosts dest=/tmp/hosts"

To ensure a package is installed without updating it:

    $ ansible webservers -m yum -a "name=acme state=present"

To ensure a package is at the latest version:

    $ ansible webservers -m ansible.builtin.yum -a "name=acme state=latest"

To ensure a package is not installed:

    $ ansible webservers -m ansible.builtin.yum -a "name=acme state=absent"

Do you want a command to run on one machine at a time ?

    ansible all -f 1 -a "free"