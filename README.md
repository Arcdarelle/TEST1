Q2 : Yum-Repo
=============

**Question 2** : Configure Your **node1** VM repository installed the packages distribution is available via YUM:

```   
baseos url = http://content.example.com/rhel7.0/x86_64/dvd/BaseOS file:///opt/exam/BaseOsappstream url= http://content.example.com/rhel7.0/x86_64/dvd/Appstream file:///opt/exam/AppStream

```

**Answer**

```
# check the repolist available (There will be none on this server)yum repolist all# Navigate to the /etc/yum/repos.d folder, create and edit a new .repo filecd /etc/yum.repos.d vi server.repo

```

*   AppStream:
    

For practice on this server, instead use the following baseurl: **file:///opt/exam/AppStream**

```
[AppStream]name= AppStream baseurl=http://content.example.com/rhel7.0/x86_64/dvd/Appstream gpgcheck=0 enabled=1

```

*   BaseOS
    

For practice on this server, instead use the following baseurl: **file:///opt/exam/BaseOS**

``` [BaseOS]name=BaseOSbaseurl=http://content.example.com/rhel7.0/x86_64/dvd/BaseOs gpgcheck=0 enabled=1   ```

Save and quit the file, clean the yum cash and check the repolist

`   yum clean allyum repolist all   `
