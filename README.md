Q18 : Resize LVM
================

**Question 18.** Resize your vo logical volume, it should be approx 300MB( note -> only size accepted from 270mb to 290mb).

**Answer**

```
# check the size of the logical volume (175M)
df -h
lvs //( will display on which volume group it is sitting.)

# resize the volume
lvresize /dev/myvgo/v0 -L 300M -r

# check
lvsdf -h
```
