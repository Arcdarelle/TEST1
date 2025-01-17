Q4 : User and Group
===================


**Question 4** : Create the following users, groups, and group membership:

*   A group named sysadm.
    
*   A user “harry” who belongs to sysadm as a secondary group.
    
*   A user “natasha” who belongs to sysadm as a secondary group.
    
*   A user “sarah” who does not have access to an interactive shell & who is not a member of sysadm group.
    
*   “harry”, “natasha”, and “sarah” should all have the password of ringogee.
    

**Answer**

```
# create the sysadm
groupgroupadd sysadm

# Create users with specific characteristics
useradd -G sysadm harry
useradd -G sysadm natasha
useradd -s /sbin/nologin sarah

# set password ringogee for all the users
passwd harry
passwd natasha
passwd sarah
```
