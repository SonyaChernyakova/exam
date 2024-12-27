![image](https://github.com/user-attachments/assets/b01d130a-8cd3-471c-b875-f59757afedb2)

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
srv lemp  192.168.0.2/24
srv prometeus 192.168.1.2/24
