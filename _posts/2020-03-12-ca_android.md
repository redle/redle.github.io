---
layout: post
author: redle
title: Hacking install CA Android
---
# Generate
```
openssl req -x509 -days 730 -nodes -newkey rsa:2048 -outform der -keyout server.key -out ca.der -extensions v3_ca
```

# Convert the private key
```
openssl rsa -in server.key -inform pem -out server.key.der -outform der
openssl pkcs8 -topk8 -in server.key.der -inform der -out server.key.pkcs8.der -outform der -nocrypt
```

# Convert the public key
```
openssl x509 -inform der -in ca.der -out ca.pem
openssl x509 -inform PEM -subject_hash_old -in ca.pem | head -1
cp ca.pem a58355c2.0
openssl x509 -inform PEM -text -in ca.pem -out /dev/null>> a58355c2.0
```

# Copy to system certs
```
/system/etc/security/cacerts/
```

# BurpSuite
```
Go to the proxy settings page and choose “Import / Export CA Certificate” -> “Import” -> “Certificate and priate key in DER format”
CA Certificate choose ca.der
Private Key choose server.key.pkcs8.der
```

# Links:
> https://blog.ropnop.com/configuring-burp-suite-with-android-nougat/
> https://awakened1712.github.io/hacking/hacking-install-ca-android/