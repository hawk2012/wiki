## 🌐 Настройка сети в Linux

Linux предоставляет мощные инструменты для управления сетью как через GUI, так и через терминал.

---

### 📡 Проверка подключения

```bash
ping google.com       # Проверить соединение
ip a                  # Посмотреть IP-адреса
hostname              # Посмотреть имя хоста
nslookup example.com  # Проверить DNS
dig example.com       # Расширенная информация о домене
```

---

### 🛠️ Настройка IP-адреса

#### Временная настройка (через `ip`):
```bash
sudo ip addr add 192.168.1.100/24 dev eth0
sudo ip link set eth0 up
```

#### Постоянная настройка зависит от дистрибутива:

##### Ubuntu (netplan):
Файл: `/etc/netplan/*.yaml`
```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      addresses:
        - 192.168.1.100/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
```
Применить:
```bash
sudo netplan apply
```

##### Debian/Red Hat:
Файл: `/etc/network/interfaces` или `/etc/sysconfig/network-scripts/ifcfg-<интерфейс>`

---

### 🔌 Управление сервисами сети

```bash
systemctl status networking   # Debian/Ubuntu
systemctl status NetworkManager  # Если используется
```

---

### 🔍 Брандмауэр

#### UFW (упрощённый брандмауэр):

```bash
sudo ufw status
sudo ufw allow 80/tcp         # Разрешить HTTP
sudo ufw deny from 192.168.1.100  # Заблокировать IP
```

#### Firewalld (в Fedora/CentOS):

```bash
firewall-cmd --list-all
firewall-cmd --add-port=22/tcp --permanent
firewall-cmd --reload
```

---

### 📎 Полезные ссылки

- [Linux Networking Commands](https://linux.die.net/man/8/ip)
- [UFW Essentials](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-ubuntu-20-04)
- [Netplan.io documentation](https://netplan.io/)
