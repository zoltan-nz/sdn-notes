### Running Mininet VM

* Never change mac address
* Setup NAT with port forward

`ssh -Y -l mininet -p 2222 localhost`

#### Upgrade old Ubuntu image

https://help.ubuntu.com/community/EOLUpgrades

Update sources.list:

```
## EOL upgrade sources.list
# Required
deb http://old-releases.ubuntu.com/ubuntu/ CODENAME main restricted universe multiverse
deb http://old-releases.ubuntu.com/ubuntu/ CODENAME-updates main restricted universe multiverse
deb http://old-releases.ubuntu.com/ubuntu/ CODENAME-security main restricted universe multiverse

# Optional
#deb http://old-releases.ubuntu.com/ubuntu/ CODENAME-backports main restricted universe multiverse
```

