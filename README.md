# 10-01hw
# «Keepalived/vrrp» - Дрибноход Давид

## Задание 1.
#### Node 1
```

vrrp_instance failover_test {
state MASTER
interface enp0s8
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
192.168.0.1
}
virtual_ipaddress {
192.168.0.50 dev enp0s8 label enp0s8:vip
}
}

```
#### Node 2
```
vrrp_instance failover_test {
state BACKUP
interface enp0s8
virtual_router_id 10
priority 110
advert_int 4
authentication {
auth_type AH
auth_pass 1111
}
unicast_peer {
192.168.0.2
}
virtual_ipaddress {
192.168.0.50 dev enp0s8 label enp0s8:vip
}
}

```
![Скриншот 1](https://github.com/DrDavidN/10-01hw/blob/main/img/10-01z1_1.JPG)
![Скриншот 1](https://github.com/DrDavidN/10-01hw/blob/main/img/10-01z1_2.JPG)

## Задание 2.
![Скриншот 1](https://github.com/DrDavidN/10-01hw/blob/main/img/10-01z2_1.JPG)
![Скриншот 1](https://github.com/DrDavidN/10-01hw/blob/main/img/10-01z2_2.JPG)


