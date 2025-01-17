Q3 : Selinux-http
=================


**Question 3** : SELINUX PORT

*   Your system httpd service having some issues service is not running on port 83.
    
*   In your system httpd service have some files in _**/var/www/html**_ (do not change or alter files)
    
*   solve the port issue.
    

**Answer (Troubleshooting scenario)**

Here, we can first check the status of the httpd daemon and try to start it.

```
systemctl status httpd
systemctl start httpd
# The daemon will fail to start

```

Let’s double check if the server is configured to listen on port **83**. Also check the system mode:

```
grep -i listen /etc/httpd/conf/httpd.conf
# The system is listening on port 83

getenforce
# The system is in Enforcing mode ie, the Selinux is blocking the port
```

Make sure the port is added. If it is not, then go ahead and do it.

```
firewall-cmd --list-all
firewall-cmd --permanent --add-port=83/tcp
firewall-cmd --reload
firewall-cmd --list-all
```

Add the **httpd** service in the Selinux as well:

```
firewall-cmd --permanent --add-service=http
firewall-cmd --reload
firewall-cmd --list-all
```

Use the **semanage** command to list all the ports configured in Selinux. Add the port **83** if it is not found in the list:

```
# use this command to install semanage on the service if it is not found
yum install policycoreutils-python-utils

# list the ports with semanage
semanage port -l |grep http

# add the port 83
semanage port -a -t http_port_t 83 -p tcp

# check if the port was successfully added
semanage port -l |grep http
```

Start, enable and check the status of the **httpd** daemon

```
systemctl start httpdsystemctl enable httpdsystemctl status httpd 
```

Finally, check in your browser with **yourIP:83** to make sure the issue is solved.

**Note:** **Throughout the exam, always enable all the daemon you will use. Your server will be rebooted at the end.**

**Summary of useful the steps to the solution**

```
firewall-cmd --permanent --add-port=83/tcp
firewall-cmd --reload
semanage port -l | grep http
semanage port -a -t http_port_t 83 -p tcp
semanage port -l | grep http  firewall-cmd --list-all   
```
