Q16 : LVM-Creation
==================


**Question 16**. Create an LVM name wshare from wgroup volume group. Note the following:

*   PV size should be 8MB
    
*   LVM size should be 50 extents
    
*   Format with “_**ext4**_” file system and mount it under _**/mnt/wshare**_. And it should auto mount after next reboot
    

**Answer**

To check the hard drive, we can run the **lsblk** command. Here we have 3 partitions (sda-20 GB, sdb-4 GB and sdc-10 GB)

You can use the **sdb** for the LVM and the Swap partition, and **sdc** for the stratis or for Vdo (use the drive with the **smaller size for the LVM (sdb)**)

*   **Partition the disk**
    

```
fdisk /dev/sdb1

# in the partition disk: prompt
command (m for help): n (for new)
Partition type: p (for primary)
Partition number: press Enter to choose the default (2)
First sector: press EnterLast sector: +1GCommand: p (to print the partitions)
```
```
# We have now sdb1 and sdb2

# Let’s give a tag to our partition
Command : t
Partition number: press Enter for default (2)

# you can type l to get the list of all hex codes
Hex code: 8e (for linux LVM)
Command: p (to print)
command : w (to write the modifications)
```
```
# Check
lsblk

# if it does not display, use the command:
partprobe

# if it throws any error, reboot the system
```

*   **Create the volume group**
    

```
pvcreate /dev/sdb2
vgcreate wgroup -s 8M /dev/sdb2
```
```
# check
vgs
```

*   **Create the logical volume**
    

```
lvcreate -l 50 -n wshare wgroup
lvs
```
```
# format the volume
mkfs.ext4 /dev/wgroup/wshare

# install it if command not found and try again
yum install mkfs   `
```

*   **Create the mount point**
    

``` 
mkdir /mnt/wshare
blkid

# You can see the logical volume with its UUID and the type ext4
# You can use the UUID to mount it in the file system or you can use the fstab   `
```

*   **Mount the logical volume**
    
```
vi /etc/fstab

# at the end of the file, press o to enter a new line

# use the tab key to put the space
/dev/wgroup/wshare   /mnt/wshare   ext4   defaults   0 0

# save and quit
mount -a

# to make sure the mount point is OK

# check
df -h
```
