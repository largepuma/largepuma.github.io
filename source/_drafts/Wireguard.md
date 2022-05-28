---
title: Wireguard
tags: []
id: '52667'
categories:
  - - uncategorized
---

```
sudo apt install bind9
sudo vi /etc/bind/named.conf.options

options {
        directory "/var/cache/bind";
        dnssec-validation auto;
        listen-on-v6 { any; };
        // new added configuration
        recursion yes;
        forwarders {
                1.1.1.1;
                1.0.0.1;
        };
        forward only;
};

named-checkconf  /etc/bind/named.conf
named-checkconf  /etc/bind/named.conf.options
sudo service bind9 restart

sudo ln -s ../run/systemd/resolve/stub-resolv.conf /etc/resolv.conf

sudo systemctl stop wg-quick@wg0
sudo vim /etc/wireguard/wg0.conf
sudo systemctl start wg-quick@wg0

sudo wg status
sudo wg show
```