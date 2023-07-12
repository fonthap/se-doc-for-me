# Use repo with ISO img

## Oracle linux

mount ISO to folder
```
mount -o loop,ro OracleLinux-R9-U2-x86_64-dvd.iso /local/
```
create repo file config 

```
vi /etc/yum.repos.d/local.repo
```

local.repo

```[Local]
name=Oracle Linux 8.5 x86_64
baseurl=file:///local/AppStream
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY
gpgcheck=0
enabled=1

[Local]
name=Os
baseurl=file:///local/BaseOS
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY
gpgcheck=0
enabled=0
```
clear yum repo
```
yum clean all
```
check yum repo
```
yum repolist
```