Q5 : Collaborative Directory
============================


**Question 5** : create a collaborative directory _**/shared/sysadm**_ with the following characteristics:

*   Group ownership of _**/shared/sysadm**_ is sysadm.
    
*   The directory should be readable, writable, and accessible to member of sysadm, but not to any other user. (It is understood that root has access to all files and directories on the system.)
    
*   Files created in _**/shared/sysadm**_ automatically have group ownership set to the sysadm group.
    

**Answer**

```
# create the directory. The -p option allow us to create nested directories
mkdir -p /shared/sysadmls -ld /shared/sysadm

# Set the group ownership
chgrp sysadm /shared/sysadm

# set permissions (read, write,execute)
chmod 770 /shared/sysadmls -ld /shared/sysadm

# set the SGID on the folder
chmod 2770 /shared/sysadmls -ld /shared/sysadm
```
