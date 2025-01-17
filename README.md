Q6 : Cronjob
============


**Question 6** : Set The Cron Job for the user “Natasha” that should runs daily every 3 minutes local time and executes “Ex200 Test in progress” with logger.

**Answer**

```
# check if the crontab package is installed
rpm -qa crontabs

# Check if the daemon is running and enabled
systemctl status crond

# create the cronjob
crontab  -e -u natasha  */3****  echo "EX200 Testing"

# restart and enable the service
systemctl restart crond.service
systemctl enable crond.service

# verify the cronjob is set for the user
crontab -l -u natasha
```
