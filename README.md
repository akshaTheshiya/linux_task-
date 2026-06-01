Quection 1 :---
User & Permission Management
Create users: user1, user2, user3
Create group: developers
Add users to the group
Create a shared directory /project
Configure permissions so only group members can access it

ANswer :---
[linux@aksha ~]$ sudo su
[sudo] password for linux: 
[root@aksha linux]# cd /

------------* create 3 user and give passwd *----------------
[root@aksha /]# useradd task1
[root@aksha /]# useradd task2
[root@aksha /]# useradd task3
[root@aksha /]# passwd task1
Changing password for user task1.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@aksha /]# passwd task2
Changing password for user task2.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@aksha /]# passwd task3
Changing password for user task3.
New password: 
BAD PASSWORD: The password is shorter than 8 characters
Retype new password: 
passwd: all authentication tokens updated successfully.

------------* create group and useradd to the group*-------------   
[root@aksha /]# groupadd lecture
[root@aksha /]# passwd lecture
passwd: Unknown user name 'lecture'.
[root@aksha /]# usermod -aG lecture task1
[root@aksha /]# usermod -aG lecture task2
[root@aksha /]# usermod -aG lecture task2
[root@aksha /]# usermod -aG lecture task3
[root@aksha /]# tail etc/group
op:x:1069:
top:x:1072:
hello1:x:1073:
a1:x:1074:
dude:x:1075:
xyz:x:1076:
task1:x:1077:
task2:x:1078:
task3:x:1079:
lecture:x:1080:task1,task2,task3


----------------* create directory *----------------------
[root@aksha /]# mkdir /classtask
[root@aksha /]# ls
acl       akshu1  akshu4  axu2  axu5  class      etc      lib    mnt     opt   run   selinux  sys  var
afs       akshu2  akshu5  axu3  bin   classtask  home     lib64  mydir   proc  sbin  srv      tmp
aksha.sh  akshu3  axu1    axu4  boot  dev        kamlesh  media  mydir1  root  se    sukla    usr

--------------* permission to directory *------------------
[root@aksha /]# chmod 770 /classtask

-------------* directory add to the group *----------------
[root@aksha /]# chgrp lecture /classtask

[root@aksha /]# ls -ld
dr-xr-xr-x. 31 root root 4096 Jun  1 12:51 .

[root@aksha /]# cd /classtask

[root@aksha classtask]# ls

[root@aksha /]# 

