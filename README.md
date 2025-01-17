Q19 : Stratis Volume
====================


**Question 19.** Configure Stratis as following

*   create stratis pool
    
*   create filesystem
    
*   take snapshot
    

**Answer**

Stratis a a tool that can be used to manipulate volumes in Linux. For the practice, we are going to use the sdc partition of the hard drive

```
# create a pool with stratis
stratis pool create pool1 /dev/sdc

# if stratis is not found just install it, start and enable the service
yum search stratis
yum install stratis-cli
stratisd -y
systemctl start stratisd
systemctl enable stratisd
systemctl status stratisd

# create the stratis pool list
stratis pool create pool1 /dev/sdc
stratis pool list

# create a file system  stratis file
system create pool1 fs1
stratis filesystem list

# create a mount point
mkdir /mnt/fs1
blkid
```
This shows the stratis volume with its UUID  as well as the type xfs  
```
# mount the file system
vi /etc/fstab

# at the end of the file press o to enter a new line
/stratis/pool1/fs1  /mnt/fs1  xfs  defaults   0 0

# save and quit
mount -a
df -h

# take a snapshot (backup)
stratis filesystem snapshot pool1 fs1 fs1-snap1
stratis filesystem list

# check
df -h
```
