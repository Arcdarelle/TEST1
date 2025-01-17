Q14 : Root Password
===================

**Question 14.** Root Password reset

**Answer**

```
# steps to break the root password


1- Boot up the server
2- Enter e at the grub

# at the end of the line starting with linux

3- rd.break
4- Ctrl + x
5- # mount -o remount,rw /sysroot
6- # chroot /sysroot
7-# passwd root
8- Enter ringogee as password and confirm
9- # touch /.autorelabel
10- #exit11- #exit   
```
