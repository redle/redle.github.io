---
layout: post
author: redle
---
Instalation Java on Debian 

```
$ wget --no-cookies --no-check-certificate --header "Cookie: oraclelicense=accept-securebackup-cookie" \
  http://download.oracle.com/otn-pub/java/jdk/11.0.2+9/f51449fcd52f4d52b93a989c5c56ed3c/jdk-11.0.2_linux-x64_bin.deb

$ dpkg -i jdk-11.0.2_linux-x64_bin.deb

$ update-alternatives --install /usr/bin/java java  /usr/lib/jvm/jdk-11.0.2/bin/java 2
$ update-alternatives --config java
```
References:

[https://tecadmin.net/install-oracle-java-on-debian-10-buster/](https://tecadmin.net/install-oracle-java-on-debian-10-buster/)
