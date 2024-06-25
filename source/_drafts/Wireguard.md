---
title: Wireguard
tags: []
id: '52667'
categories:
  - - uncategorized
---


```

# Enable IP Forwarding
```
-> ls -l /etc/sysctl.d/wireguard.conf 
-rw------- 1 root root 53 Sep 25 22:23 /etc/sysctl.d/wireguard.conf
-> cat /etc/sysctl.d/wireguard.conf 
net.ipv4.ip_forward=1
net.ipv6.conf.all.forwarding=1

-> sysctl -p /etc/sysctl.d/wireguard.conf
net.ipv4.ip_forward = 1
net.ipv6.conf.all.forwarding = 1
```

# Install and configure Bind & Wireguard

sudo ufw disable
sudo apt install bind9
sudo vim /etc/bind/named.conf.options

options {
        directory "/var/cache/bind";
        dnssec-validation auto;
        listen-on-v6 { any; };
        // new added configuration
        recursion yes;
        forwarders {
                1.1.1.1;
                1.0.0.1;
                2606:4700:4700::1111;
                2606:4700:4700::1001;
        };
        forward only;
};

named-checkconf  /etc/bind/named.conf
named-checkconf  /etc/bind/named.conf.options
sudo service bind9 restart

sudo ln -s /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf

sudo apt install wireguard
sudo systemctl stop wg-quick@wg0
sudo vim /etc/wireguard/wg0.conf
sudo systemctl start wg-quick@wg0

sudo wg show
```

Pay attention to the network inface name. It may change in deffient system, like eth0 or ens5.


Reference: 
1. https://emanuelduss.ch/2018/09/29/wireguard-vpn-road-warrior-setup/
2. https://www.wireguard.com/install/
