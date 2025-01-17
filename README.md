Q21 : Tuned
===========

**Question 20.** Configure recommended tuned profile

**Answer**

```
# check if tuned is install, if not, install, start and enable it
rpm -qa tuned
systemctl status tuned
```
```
# check the active profile
tuned-adm active
```
```
# list the available profiles
tuned-adm list
```
```
# check the recommended profile
tuned-adm profile recommend
```
The recommended profile here is virtual-guest
```
# To activate the recommended profile
tuned-adm profile virtual-guest
```
