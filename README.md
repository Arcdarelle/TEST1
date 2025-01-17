Q15 : Yum Repo
==============


**Question 15.** Configure your VM repository. The packages distribution are available via YUM:

```
baseos url = http://content.example.com/rhel7.0/x86_64/dvd/BaseOs
appstream url= http://content.example.com/rhel7.0/x86_64/dvd/Appstrea   `
```

**Answer: same as question 2.**

```
# check the repolist available (There will be none on this server)
yum repolist all

# Navigate to the /etc/yum/repos.d folder, create and edit a new .repo file
cd /etc/yum.repos.d
vi server.repo
```

*   **AppStream:**
    

For practice on this server, instead use the following baseurl: **file:///opt/exam/AppStream**

```
[AppStream]
name= AppStream
baseurl=http://content.example.com/rhel7.0/x86_64/dvd/Appstream
gpgcheck=0
enabled=1
```
*   **BaseOS**
    

For practice on this server, instead use the following baseurl: **file:///opt/exam/BaseOS**

```
[BaseOS]
name=BaseOS
baseurl=http://content.example.com/rhel7.0/x86_64/dvd/BaseOs
gpgcheck=0
enabled=1   
```
Save and quit the file, clean the yum cash and check the repolist

```
yum clean allyum repolist all
```
