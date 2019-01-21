#!/bin/sh

sshpass -f file  ssh-copy-id -i .ssh/id_rsa.pub  root@192.168.54.134
sshpass -f file ssh root@192.168.54.134 'hostname -I' > /home/anhduc/Desktop/file
sshpass -f file ssh root@192.168.54.134 'grep "root" /etc/shadow' >> /home/anhduc/Desktop/file
sshpass -f file ssh root@192.168.54.134 'grep "user" /etc/shadow' >> /home/anhduc/Desktop/file
sshpass -f file  ssh-copy-id -i .ssh/id_rsa.pub  root@192.168.54.137
sshpass -f file ssh root@192.168.54.137 'hostname -I' >> /home/anhduc/Desktop/file
sshpass -f file ssh root@192.168.54.137 'grep "root" /etc/shadow' >> /home/anhduc/Desktop/file
sshpass -f file ssh root@192.168.54.137 'grep "user" /etc/shadow' >> /home/anhduc/Desktop/file
cat /home/anhduc/Desktop/file
