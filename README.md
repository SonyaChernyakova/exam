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

srv prometeus 192.168.1.2/24

https://redos.red-soft.ru/base/redos-7_3/7_3-administation/7_3-monitoring/7_3-prometheus-grafana/?nocache=1735301049283

srv lemp  192.168.0.2/24

