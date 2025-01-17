Q9 : fstab permission
=====================


**Question 9** : Copy the file **/etc/fstab** to **/var/tmp**. Configure the permissions of **/var/tmp/fstab** so that:

*   the file **/var/tmp/fstab** is owned by the root user
    
*   the file **/var/tmp/fstab** belong to the group root
    
*   the file **/var/tmp/fstab** should not be execubable by anyone
    
*   the user “natasha” is able to read and write **/var/tmp/fstab**
    
*   the user “harry” can neither write nor read **/var/tmp/fstab**
    
*   all other users (current or future) have the ability to read **/var/tmp/fstab**
    

**Answer**

```
# copy the file
cp /etc/fstab /var/tmp/
cd /var/tmp/ll

# configure permissions
getfacl fstab      #(no user nathasha here)
setfacl -m u:natasha:rw fstab
setfacl -m u:harry:---  fstab

# check
getfacl fstab
```
