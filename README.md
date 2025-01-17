Q14 : Root Password
===================

**Question 14.** Root Password reset

**Answer**

```
# steps to break the root password1- Boot up the server  2- Enter e at the grub# at the end of the line starting with linux  3- rd.break  4- Ctrl + x  5- # mount -o remount,rw /sysroot6- # chroot /sysroot7- # passwd root8- Enter ringogee as password and confirm9- # touch /.autorelabel10- #exit11- #exit   
```
