### Таблица адресациии
|Устройство|Интерфейс     |    IPv4          |Маска      | Шлюз                |
| ----     | ------------ | ---------------- | --------- | ------------------- |  
|HQ-R      |    ens192    |    192.168.0.2   |    /24    |    192.168.0.1      |
 |BR-R      |    ens192    |    172.16.0.2   |    /24    |    172.16.0.1      |
 |HQ-SRV|    ens192    |    192.168.0.3   |    /24    |    192.168.0.1      |
|BR-SRV|    ens192    |    172.16.0.3   |    /24    |    172.16.0.1      |
 |ISP   |    ens192    |    10.12.37.2    |    /24    |    10.12.37.254     |
 | | ens224 | 192.168.0.1 | /24 | - |
 | | ens256 | 172.16.0.1 | /24 | - |


### Имена хостов
#### ISP

```debian
hostnamectl set-hostname ISP
```
#### HQ-R

```debian
hostnamectl set-hostname HQ-R
```
#### BR-R

```debian
hostnamectl set-hostname BR-R
```
#### HQ-SRV

```debian
hostnamectl set-hostname HQ-SRV
```
#### BR-SRv

```debian
hostnamectl set-hostname BR-SRV
```
### Адресация на устройствах
#### ISP

```debian
nano /etc/network/interfaces
```

```debian
auto ens192
iface ens192 inet static
address 10.12.37.3/24
gateway 10.12.37.254


auto ens224
iface ens224 inet static
address 192.168.0.1/24


auto ens256
iface ens256 inet static
address 172.16.0.1/24
```
#### HQ-R

```debian
nano /etc/network/interfaces
```

```debian
auto ens192
iface ens192 inet static
address 192.168.0.2/24
gateway 192.168.0.1
```
#### BR-R

```debian
nano /etc/network/interfaces
```

```debian
auto ens192
iface ens192 inet static
address 172.16.0.2/24
gateway 172.16.0.1
```
#### HQ-SRV

```debian
nano /etc/network/interfaces
```

```debian
auto ens192
iface ens192 inet static
address 192.168.0.3/24
gateway 192.168.0.1
```
#### BR-SRV

```debian
nano /etc/network/interfaces
```

```debian
auto ens192
iface ens192 inet static
address 172.16.0.3/24
gateway 172.16.0.1
```
