Q20 : VDO Volume
================


**Question 20**. Configure VDO as per following

*   Create a Volume using VDO as vgough
    
*   Volume Logical Size should be 50G
    
*   format it using **xfs** file system type
    
*   make it persistant mountt at **/mnt/vgough**
    

**Answer**

Before answering this question, you need to remove the Stratis volume we created in the previous question in order to use the sdc drive.

[**Click here to do that.**](https://drive.google.com/file/d/1eSGpNnxbqvYqkDKjmubyjH9MMu9EEATj/view?usp=sharing)

 * Check if VDO is installed
```
# check if VDO is installed, if not install it
vdo
yum install -y vdo kmod-kvdo
systemctl start vdo
systemctl enable --now vdo
```
 * Create the VDO volume
```
# Create the VDO volume
vdo create --name=vgough --device=/dev/sdc --vdoLogicalSize=50G

# the path to the volume is given at the end /dev/mapper/vgouh
```
 * Create a file system
```
# create a file system using the format xfs
mkfs.xfs -K /dev/mapper/vgough
udevadm settle
```
 * Create a mount point
```
# create a mount point
mkdir /mnt/vgough
```
 * Mount the volume
```
# mount the volume
vi /etc/fstab

# at the end of the file, press o to add the following line
/dev/mapper/vgough /mnt/vgough xfs x-systemd.requires=vdo.service, 0 0

# save and quit
mount -a

# check
reboot
```

If the system does not reboot, follow the process to break the root password.

Instead of running the **root passwd** command, run the **\# vi /etc/fstab** command and put a **#** sign in front of the line you are suspecting (to disable it)and then reboot the system
