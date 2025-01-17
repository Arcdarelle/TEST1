Q7 : Autofs
===========


**Question 7.** Configure autofs to automount the home directories of netuserX user. Note the following:

*   netuserX home directory is exported via NFS, which is available on classroom.example.com**(172.25.254.254)** and your NFS-exports directory is /netdir for ldapuser5,
    
*   netuser’s home directory is classroom.example.com:/home/netdir/ldapuser5, where X is your station number
    
*   ldapuser5’s home directory should be automounted autofs service.
    
*   home directories must be writable by their users.
    
*   password for netuser is ablerate.
    

**Answer**

Basically, they want the user’s home directory to be mounted automatically when they log in. Here you need to keep 3 things in mind:

*   Who is the user? **A: netuserX**
    
*   What is the NFS export directory? **A: /netdir**
    
*   What is the user’s home directory? **A: classroom.example.com:/home/netdir/netuserX**
    

```
# Check if autofs is installed, if not install it
rpm -qa autofs
yum install autofs

# Check the status of the daemon, make sure it is running and enabled
systemctl status autofs
systemctl start autofs
systemctl enable autofs

# set auto mount for the user
vi /etc/auto.master

# under the line starting with /misc, press o to create a new line, type:
/netdir /etc/auto.misc

# save and exit the file
vi /etc/auto.misc

# add a new line to this file
netuserX  -fstype=nfs,rw classroom.example.com:/home/netdir/netuserX

# save and exit

# restart the service systemctl restart autofs

# In the exam, you will need to login to the user's account to make sure it works!
su - netuserX
```
