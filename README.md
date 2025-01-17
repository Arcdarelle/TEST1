Q11 : Find Files
================


**Question 11.** Find all files and directories which is created by a user “julia” in to this system and copy it into a _**“/root/findfiles”**_ directory.

**Answer**

```
# create the /root/findfiles directory
mkdir /root/findfiles

# find the files and copy
find / -user julia  -exec cp -rvp {} /root/findfiles/ \; 2> /dev/null

# note: to find and copy all the files only, use this instead:
find / -user julia -type f -exec cp -rvp {} /root/findfile/ \; 2> /dev/null

# note: to find and copy all the files only, use this instead:
find / -user julia -type d -exec cp -rvp {} /root/findfile/ \; 2> /dev/null

# check
cd /root/findfiles
ls -la
```
