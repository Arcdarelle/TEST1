Q8 : Backup
===========


**Question 8.** Create a backup 


 *  Create a tar archive of “**/usr/local/**” Directory with **.bzip2** ( can also be **.tgz** )extension.
 *  Tar archive named **“myetcbackup.tar”** should be place in “**/root/**” Directory.

**Answer**

```
# verify that tar and bzip2 or gzip2 are installed
yum install tar
yum install bzip2 #(or yum install gzip2)

# create the backup file:

# *for bz2 use this
tar -cvjf /root/mybackup.tar.bz2 /usr/local

# *for tgz use this
tar -cvzf /root/mybackup.tar.tgz /usr/local# checkcd /rootls
```
