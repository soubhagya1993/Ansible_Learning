Referrence Video -- https://www.youtube.com/watch?v=y2TSR7p3N0M&t=77s&ab_channel=MPrashant

Syntax --

    $ ansible [pattern] -m [module] -a "[module options]"

to run as sudo user if become: true then we should use --ask-become-pass

     ansible-playbook  --ask-become-pass  playbook.yml

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

To Run adhoc commmand by root

    $ ansible localhost -m copy -a "src=/etc/hosts dest=/tmp/hosts" -b --ask-become-pass

To ensure a package is installed without updating it:

    $ ansible webservers -m yum -a "name=acme state=present"

To ensure a package is at the latest version:

    $ ansible webservers -m ansible.builtin.yum -a "name=acme state=latest"

To ensure a package is not installed:

    $ ansible webservers -m ansible.builtin.yum -a "name=acme state=absent"

Do you want a command to run on one machine at a time ?

    ansible all -f 1 -a "free"

To create a group

    ansible app -s -m group -a "name=admin state=present"

To create a user

    ansible app -m user -a "name=devops group=admin createhome=yes" --ask-pass -K --become

To copy file from control node to app servers.

    ansible app -m copy -a "src=/vagrant/test.txt dest=/tmp/test.txt"

Validating Syntax
Option 1 : Using --syntax-check option with ansible-playbook

    ansible-playbook playbook.yml --syntax-check

To Dry run

    ansible-playbook playbook.yml --check

To check free space 

    ansible localhost  -m command -a "df -h" 

To restart service

    ansible localhost -m service -a "name=nginx state=reloaded"

to run a script

    ansible localhost -m shell -a "/tmp/script/test.sh"

check free memory

    ansible localhost -m command -a "free -m"

    
