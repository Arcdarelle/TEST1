Q17 : SWAP
==========

**Question 17.** Create a swap partition of 400M MB and make it available permanent.

**Answer**

The swap is a volume on the Hard disk that the system borrows when it runs out of memory. Here we are going to use the smaller volume to create this partition

*   Create a partition of 400M
    

```
fdisk /dev/sdb
Command (type m for help): n
Choose the primary partition type : p
Press Enter to choose as default, partition number 3
First sector: press Enter
For the size, write +400M
Command: p
```
you see the new partition created
```
# give a tab to the new partition
Command : t
# You can enter l to check the list of hex codes (the one we are searching here is the 82)
Hex code: 82 (for linux SWAP)Command: p (to print)
command : w (to write the modifications)

# Check
lsblk
# if it does not display, use the command:
partprobe
```
if it throws any error, reboot the system


*   Make it a swap partition
    

```
# Check the actual swap size (it is 2047 here)
free -m

# make the swap partition
mkswap /dev/sdb3vi /etc/fstab

# at the end of the file, press o to insert a line
/dev/sdb3   swap   swap   defaults   0 0

# save and quit

# mount
mount -a
swapon -a
swapon -s

# check
free -m

```
the size is now **2447**
