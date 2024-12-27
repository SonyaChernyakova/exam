# exam

rtr
```
echo net.ipv4.ip_forward=1 > /etc/sysctl.conf 
dnf install iptables-services –y
systemctl enable ––now iptables
iptables –t nat –A POSTROUTING –s 192.168.0.0/24 –o ens3 –j MASQUERADE
iptables –t nat –A POSTROUTING –s 192.168.1.0/24 –o ens3 –j MASQUERADE
iptables-save > /etc/sysconfig/iptables
systemctl restart iptables
```
