Q10 : NTP Chrony
================


**Question 10.** Configure your system to syncronize the time from _“classroom.example.com”._

**Answer**

```
# Check if cron is installed
rpm -qa chrony

# Check status of the daemon  and make sure it is enabled
systemctl status chronydsystemctl enable chronyd

# edit the configuration file
vi /etc/chrony.conf

# under the line starting with pool, press o to create a new line. Type:
pool classroom.example.com iburst#save and quit

# restart the service
systemctl restart chronyd.service

# check
chronyc sources -v
```
