# *Модуль 1*

### **[Задание](https://github.com/sa22-demo/demo2025/blob/main/%D0%97%D0%90%D0%94%D0%90%D0%9D%D0%98%D0%95%20%D0%9A%D0%9E%D0%94%2009.02.06-1-2025.pdf)**

#

### Содержание

1. **[Произведите базовую настройку устройств](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-1)**

2. **[Настройка ISP](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-2)**
  
3. **[Создание локальных учетных записей](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-3)**
  
4. **[Настройте на интерфейсе HQ-RTR в сторону офиса HQ виртуальный коммутатор](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-4)**
   
5. **[Настройка безопасного удаленного доступа на серверах HQ-SRV и BR-SRV](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-5)**
  
6. **[Между офисами HQ и BR необходимо сконфигурировать IP-туннель](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-6)**

7. **[Обеспечьте динамическую маршрутизацию](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-7)**

8. **[Настройка динамической трансляции адресов](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-8)**

9. **[Настройка протокола динамической конфигурации хостов](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-9)**

10. **[Настройка DNS для офисов HQ и BR](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-10)**

11. **[Настройте часовой пояс на всех устройствах, согласно месту проведения экзамена](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-11)**

<br/>

<br/>

<p align="center">
  <img width="444" src="https://github.com/user-attachments/assets/b8ee7b98-fdf1-41c3-9f67-1b130eeb8b99"
<p\>

<br/>

## Задание 1

### Произведите базовую настройку устройств

- Настройте имена устройств согласно топологии. Используйте полное доменное имя

- На всех устройствах необходимо сконфигурировать IPv4

- IP-адрес должен быть из приватного диапазона, в случае, если сеть локальная, согласно RFC1918

- Локальная сеть в сторону HQ-SRV(VLAN100) должна вмещать не более 64 адресов

- Локальная сеть в сторону HQ-CLI(VLAN200) должна вмещать не более 16 адресов

- Локальная сеть в сторону BR-SRV должна вмещать не более 32 адресов

- Локальная сеть для управления(VLAN999) должна вмещать не более 8 адресов

- Сведения об адресах занесите в отчёт, в качестве примера используйте Таблицу 3

<br/>

<details>
<summary>Решение</summary>
<br/>

**Полное доменное имя можно посмотреть в таблице для [Задания 10](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-10)**

<br/>

#### Настройка имен устройств на ALT Linux
```bash
hostnamectl set-hostname <FQDN>; exec bash
```
> FQDN (Fully Qualified Domain Name) - полное доменное имя
>
> `exec bash` - обновление оболочки

<p align="center"><strong>Таблица подсетей</strong></p>
<table align="center">
  <tr>
    <td align="center">Сеть</td>
    <td align="center">Адрес подсети</td>
    <td align="center">Пул</td>
  </tr>
  <tr>
    <td align="center">SRV-Net (VLAN 100)</td>
    <td align="center">192.168.100.0/26</td>
    <td align="center">192.168.100.1 - 192.168.100.62</td>
  </tr>
  <tr>
    <td align="center">CLI-Net (VLAN 200)</td>
    <td align="center">192.168.200.0/28</td>
    <td align="center">192.168.200.1 - 192.168.200.14</td>
  </tr>
  <tr>
    <td align="center">BR-Net</td>
    <td align="center">192.168.0.0/27</td>
    <td align="center">192.168.0.1 - 192.168.0.30</td>
  </tr>
  <tr>
    <td align="center">MGMT (VLAN 999)</td>
    <td align="center">192.168.99.0/29</td>
    <td align="center">192.168.99.1 - 192.168.99.6</td>
  </tr>
  <tr>
    <td align="center">ISP-HQ</td>
    <td align="center">172.16.4.0/28</td>
    <td align="center">172.16.4.1 - 172.16.4.14</td>
  </tr>
  <tr>
    <td align="center">ISP-BR</td>
    <td align="center">172.16.5.0/28</td>
    <td align="center">172.16.5.1 - 172.16.5.14</td>
  </tr>
</table>


<br/>
<p align="center"><strong>Таблица адресации</strong></p>
<table align="center">
  <tr>
    <td align="center">Имя устройства</td>
    <td align="center">Интерфейс</td>
    <td align="center">IPv4</td>
    <td align="center" >Маска</td>
    <td align="center">Шлюз</td>
  </tr>
  <tr>
    <td align="center" rowspan="3">ISP</td>
    <td align="center">ens18</td>
    <td align="center">(DHCP)</td>
    <td align="center">/24</td>
    <td align="center">(DHCP)</td>
  </tr>
  <tr>
    <td align="center">ens19</td>
    <td align="center">172.16.4.1</td>
    <td align="center">/28</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td align="center">ens20</td>
    <td align="center">172.16.5.1</td>
    <td align="center">/28</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td align="center" rowspan="3">HQ-RTR</td>
    <td align="center">ens18</td>
    <td align="center">172.16.4.2</td>
    <td align="center">/28</td>
    <td align="center">172.16.4.1</td>
  </tr>
  <tr>
    <td align="center">ens19.100</td>
    <td align="center">192.168.100.1</td>
    <td align="center">/26</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td align="center">ens19.200</td>
    <td align="center">192.168.200.1</td>
    <td align="center">/28</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td align="center" rowspan="2">BR-RTR</td>
    <td align="center">ens18</td>
    <td align="center">172.16.5.2</td>
    <td align="center">/28</td>
    <td align="center">172.16.5.1</td>
  </tr>
  <tr>
    <td align="center">ens19</td>
    <td align="center">192.168.0.1</td>
    <td align="center">/27</td>
    <td align="center"></td>
  </tr>
  <tr>
    <td align="center">HQ-SRV</td>
    <td align="center">ens18</td>
    <td align="center">192.168.100.62</td>
    <td align="center">/26</td>
    <td align="center">192.168.100.1</td>
  </tr>
  <tr>
    <td align="center">BR-SRV</td>
    <td align="center">ens18</td>
    <td align="center">192.168.0.30</td>
    <td align="center">/27</td>
    <td align="center">192.168.0.1</td>
  </tr>
  <tr>
    <td align="center">HQ-CLI</td>
    <td align="center">ens18</td>
    <td align="center">192.168.200.14</td>
    <td align="center">/28</td>
    <td align="center">192.168.200.1</td>
  </tr>
</table>


> Адресация для **ISP** взята из следующего задания

<br/>

#### Настройка IP-адресации на **HQ-SRV**, **BR-SRV**, **HQ-CLI**, **HQ-RTR**, **BR-RTR** (настройка IP-адресации на **ISP** проводится в [следующем задании](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-2))

Приводим дефолтные файлы **`options`**, **`ipv4address`**, **`ipv4route`** в директории **`/etc/net/ifaces/*имя интерфейса*/`** к следующему виду (в примере **HQ-SRV**):
> **`options`**
```ini
BOOTPROTO=static
TYPE=eth
CONFIG_WIRELESS=no
SYSTEMD_BOOTPROTO=static
CONFIG_IPV4=yes
DISABLED=no
NM_CONTROLLED=no
SYSTEMD_CONTROLLED=no
```

<br/>

> **`ipv4address`**
```ini
192.168.100.62/26
```

<br/>

> **`ipv4route`**
```ini
default via 192.168.100.1
```


<br/>

#### Настраиваем интерфейсы на **HQ-RTR**, которые смотрят в сторону **HQ-SRV** и **HQ-CLI** (с разделением на VLAN):
В каталоге **`ens19/`** лежит стандартный **`options`**:
```ini
BOOTPROTO=static
TYPE=eth
CONFIG_WIRELESS=no
SYSTEMD_BOOTPROTO=static
CONFIG_IPV4=yes
DISABLED=no
NM_CONTROLLED=no
SYSTEMD_CONTROLLED=no
```

<br/>

Настройка VLAN производится по пути **`ens19.xxx/`** , где xxx - номер VLAN

> **`ens19.100/options`**
```ini
TYPE=vlan
HOST=ens19
VID=100
DISABLED=no
```
> **`ens19.100/ipv4address`**
```ini
192.168.100.1/26
```

<br/>

> **`ens19.200/options`**
```ini
TYPE=vlan
HOST=ens19
VID=200
DISABLED=no
```
> **`ens19.200/ipv4address`**
```ini
192.168.200.1/28
```

<br/>

> **`ens19.999/options`**
```ini
TYPE=vlan
HOST=ens19
VID=999
DISABLED=no
```
> **`ens19.999/ipv4address`**
```ini
192.168.99.1/29
```
</details>

<br/>





## Задание 2

### Настройка ISP

- Настройте адресацию на интерфейсах:

  - Интерфейс, подключенный к магистральному провайдеру, получает адрес по DHCP

  - Настройте маршруты по умолчанию там, где это необходимо

  - Интерфейс, к которому подключен HQ-RTR, подключен к сети 172.16.4.0/28

  - Интерфейс, к которому подключен BR-RTR, подключен к сети 172.16.5.0/28

  - На ISP настройте динамическую сетевую трансляцию в сторону HQ-RTR и BR-RTR для доступа к сети Интернет

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Настройка интерфейса, который получает сетевую конфигурацию по DHCP

Файл **`options`** (в директории интерфейса) приводим к следующему виду:
```ini
BOOTPROTO=dhcp
TYPE=eth
DISABLED=no
CONFIG_IPV4=yes
```
> **`BOOTPROTO=dhcp`** - заменили статику на динамику

<br/>

#### Настройка интерфейсов, смотрящих в сторону HQ-RTR и BR-RTR происходит аналогично настройке в [Задании 1](https://github.com/sa22-demo/demo2025/tree/main/%D0%9C%D0%BE%D0%B4%D1%83%D0%BB%D1%8C%201#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-1)

<br/>

#### Включение маршрутизации

В файле **`/etc/net/sysctl.conf`** изменяем строку:
```bash
net.ipv4.ip_forward = 1
```

<br/>

Изменения в файле **`sysctl.conf`** применяем следующей командой:
```bash
sysctl -p
```

<br/>

Добавляем правила **`iptables`** на ISP:
```bash
iptables -t nat -A POSTROUTING -o ens18 -s 172.16.4.0/28 -j MASQUERADE
iptables -t nat -A POSTROUTING -o ens18 -s 172.16.5.0/28 -j MASQUERADE
```

Сохраняем:
```bash
iptables-save > /etc/sysconfig/iptables
```

Включаем:
```bash
systemctl enable --now iptables
```
</details>

<br/>






## Задание 3

### Создание локальных учетных записей

- Создайте пользователя sshuser на серверах HQ-SRV и BR-SRV

  - Пароль пользователя sshuser с паролем P@ssw0rd

  - Идентификатор пользователя 1010

  - Пользователь sshuser должен иметь возможность запускать sudo без дополнительной аутентификации.

- Создайте пользователя net_admin на маршрутизаторах HQ-RTR и BR-RTR

  - Пароль пользователя net_admin с паролем P@$$word

  - При настройке на EcoRouter пользователь net_admin должен обладать максимальными привилегиями

  - При настройке ОС на базе Linux, запускать sudo без дополнительной аутентификации

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Создание пользователя `sshuser` на HQ-SRV, BR-SRV, HQ-CLI

Создаем пользователя:
```bash
useradd sshuser -u 1010
```
> опция **`-u`** позволяет указать идентификатор пользователя сразу при создании

<br/>

Задаем пароль:
```bash
passwd sshuser
```

<br/>

Добавляем в группу **wheel**:
```bash
usermod -aG wheel sshuser
```

<br/>

Раскомментируем строку в **`/etc/sudoers`**:
```yml
WHEEL_USERS ALL=(ALL:ALL) NOPASSWD: ALL
```
> Запуск **sudo** для группы **wheel** без аутентификации 

<br/>

#### Создание пользователя `net_admin` на HQ-RTR, BR-RTR:

Делаем аналогично с sshuser (без -u 1010)


</details>

<br/>





## Задание 4

### Настройте на интерфейсе HQ-RTR в сторону офиса HQ виртуальный коммутатор

- Сервер HQ-SRV должен находиться в ID VLAN 100
- Клиент HQ-CLI в ID VLAN 200
- Создайте подсеть управления с ID VLAN 999
- Основные сведения о настройке коммутатора и выбора реализации разделения на VLAN занесите в отчёт

<br/>

<details>
<summary>Решение</summary>
<br/>

https://dzen.ru/a/ZyHLLdBle0DoD1oJ
</details>

<br/>





## Задание 5

### Настройка безопасного удаленного доступа на серверах HQ-SRV и BR-SRV

- Для подключения используйте порт 2024
- Разрешите подключения только пользователю sshuser
- Ограничьте количество попыток входа до двух
- Настройте баннер «Authorized access only»

<br/>

<details>
<summary>Решение</summary>
<br/>

Добавляем следующие строки в файл **`/etc/openssh/sshd_config`**:
```yaml
Port 2024
MaxAuthTries 2
PasswordAuthentication yes
Banner /etc/openssh/bannermotd
AllowUsers    sshuser
```
> В параметре **AllowUsers** вместо пробела используется **`Tab`**

<br/>

Создаем файл **`bannermotd`**:
```yml
Authorized access only
```

<br/>

Перезагружаем службу:
```bash
systemctl restart sshd
```

</details>

<br/>





## Задание 6

### Между офисами HQ и BR необходимо сконфигурировать IP-туннель

- Сведения о туннеле занесите в отчёт

- На выбор технологии GRE или IP in IP

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Настройка туннеля между HQ-RTR и BR-RTR:
Для начала нужно создать директорию для туннельного интерфейса:  

```bash
mkdir /etc/net/ifaces/gre1
```

Затем создать файл `options` у туннеля():  

```ini
TYPE=iptun
TUNTYPE=gre
TUNLOCAL=172.16.4.2
TUNREMOTE=172.16.5.2
TUNOPTIONS='ttl 64'
HOST=ens18
```

> в `TUNLOCAL` нужно вписать адрес смотрящий на ISP  
> в `TUNREMOTE` нужно вписать адрес устройства, к которому идет туннель  
> в `HOST` нужно вписать интерфейс смотрящий на ISP  

Дальше добавляем IP-адрес на туннель:

```bash
echo 172.16.0.1/30 > /etc/net/ifaces/gre1/ipv4address
```

В конце перезагружаем службу network:  

```bash
systemctl restart network
```

### Все тоже самое делаем и на другом устройстве туннеля

</details>

<br/>

## Задание 7

### Обеспечьте динамическую маршрутизацию: ресурсы одного офиса должны быть доступны из другого офиса. Для обеспечения динамической маршрутизации используйте link state протокол на ваше усмотрение

- Разрешите выбранный протокол только на интерфейсах в ip туннеле

- Маршрутизаторы должны делиться маршрутами только друг с другом

- Обеспечьте защиту выбранного протокола посредством парольной защиты

- Сведения о настройке и защите протокола занесите в отчёт

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Настройка OSPF на HQ-RTR

Устанавливаем:
```
apt-get update
apt-get -y install frr
```

Включаем автозагрузку FRR:  
```
systemctl enable --now frr
```

<br/>

В файле `/etc/frr/daemons` меняем `ospfd=no` на `ospfd=yes`

Рестарт:
```bash
systemctl restart frr
```

<br/>

Затем заходим в среду роутера(на примере HQ-RTR):  
```
vtysh
```

И прописываем:  
```bash
conf t
router ospf
  network 172.16.0.0/30 area 0
  network 192.168.100.0/26 area 0
  network 192.168.200.0/28 area 0
  exit
ip forwarding
do w
```

<br/>

#### Маршрутизация OSPF на BR-RTR настраивается аналогично примеру выше

</details>

<br/>





## Задание 8

### Настройка динамической трансляции адресов

- Настройте динамическую трансляцию адресов для обоих офисов.

- Все устройства в офисах должны иметь доступ к сети Интернет

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Настройка NAT на HQ-RTR

```bash
iptables -t nat -A POSTROUTING -o ens18 -s 192.168.100.0/26 -j MASQUERADE
iptables -t nat -A POSTROUTING -o ens18 -s 192.168.200.0/28 -j MASQUERADE
```

Сохраняем:
```bash
iptables-save > /etc/sysconfig/iptables
```

Включаем:
```bash
systemctl enable --now iptables
```

<br/>

#### Настройка NAT на BR-RTR

```bash
iptables -t nat -A POSTROUTING -o ens18 -s 192.168.0.0/27 -j MASQUERADE
```

Сохраняем:
```bash
iptables-save > /etc/sysconfig/iptables
```

Включаем:
```bash
systemctl enable --now iptables
```

</details>

<br/>

## Задание 9

### Настройка протокола динамической конфигурации хостов

- Настройте нужную подсеть

- Для офиса HQ в качестве сервера DHCP выступает маршрутизатор HQ-RTR.

- Клиентом является машина HQ-CLI.

- Исключите из выдачи адрес маршрутизатора

- Адрес шлюза по умолчанию – адрес маршрутизатора HQ-RTR.

- Адрес DNS-сервера для машины HQ-CLI – адрес сервера HQ-SRV.

- DNS-суффикс для офисов HQ – au-team.irpo

- Сведения о настройке протокола занесите в отчёт

<br/>

<details>
<summary>Решение</summary>
<br/>

Нужно добавить в `resolv.conf` DNS-сервер, иначе мы не сможем обновить репозитории, поэтому идём его редактировать следующей командой:
```bash
mcedit /etc/net/ifaces/ens18/resolv.conf
```

И добавляем следующую строку в него:
```ini
nameserver 77.88.8.8
```

Обновим пакеты и установим её командами:
```bash
apt-get update
apt-get install dnsmasq
```

```bash
systemctl enable dnsmasq
```
Затем зайдем в настройки конфигурационного файла командой:
```bash
mcedit /etc/dnsmasq.conf
```

И внесем в него следующие строки (можно прямо в начало файла):
```ini
no-resolv
server=192.168.100.62
dhcp-range=192.168.200.14,192.168.200.14,24h
dhcp-option=3,192.168.200.1
dhcp-option=6,192.168.100.62
interface=ens19.200
```

Затем перезапускаем службу и посмотрим её статус:
```bash
systemctl restart dnsmasq
systemctl status dnsmasq
```

На HQ-CLI приводим `options` к следующему виду:
```ini
BOOTPROTO=dhcp
TYPE=eth
CONFIG_WIRELESS=no
SYSTEMD_BOOTPROTO=dhcp4
CONFIG_IPV4=yes
DISABLED=no
NM_CONTROLLED=no
SYSTEMD_CONTROLLED=no
```

Если были созданы файлы `ipv4address` и `ipv4route`, то их нужно удалить.

</details>

<br/>

## Задание 10

### Настройка DNS для офисов HQ и BR

- Основной DNS-сервер реализован на HQ-SRV.

- Сервер должен обеспечивать разрешение имён в сетевые адреса устройств и обратно в соответствии с таблицей 2

- В качестве DNS сервера пересылки используйте любой общедоступный DNS сервер

<br/>

<table align="center">
  <tr>
    <td align="center">Устройство</td>
    <td align="center">Запись</td>
    <td align="center">Тип</td>
  </tr>
  <tr>
    <td align="center">HQ-RTR</td>
    <td align="center">hq-rtr.au-team.irpo</td>
    <td align="center">A,PTR</td>
  </tr>
  <tr>
    <td align="center">BR-RTR</td>
    <td align="center">br-rtr.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
  <tr>
    <td align="center">HQ-SRV</td>
    <td align="center">hq-srv.au-team.irpo</td>
    <td align="center">A,PTR</td>
  </tr>
  <tr>
    <td align="center">HQ-CLI</td>
    <td align="center">hq-cli.au-team.irpo</td>
    <td align="center">A,PTR</td>
  </tr>
  <tr>
    <td align="center">BR-SRV</td>
    <td align="center">br-srv.au-team.irpo</td>
    <td align="center">A</td>
  </tr>
  <tr>
    <td align="center">HQ-RTR</td>
    <td align="center">moodle.au-team.irpo</td>
    <td align="center">CNAME</td>
  </tr>
  <tr>
    <td align="center">HQ-RTR</td>
    <td align="center">wiki.au-team.irpo</td>
    <td align="center">CNAME</td>
  </tr>
</table>

<p align="center"><strong>Таблица 2</strong></p>

<br/>

<details>
<summary>Решение</summary>
<br/>

Нужно добавить в `resolv.conf` DNS-сервер, иначе мы не сможем обновить репозитории, поэтому идём его редактировать следующей командой:
```bash
mcedit /etc/net/ifaces/ens18/resolv.conf
```

И добавляем следующую строку в него:
```ini
nameserver 77.88.8.8
```

Обновим пакеты и установим её командами:
```bash
apt-get update
apt-get install dnsmasq
```

```bash
systemctl enable dnsmasq
```
Затем зайдем в настройки конфигурационного файла командой:
```bash
mcedit /etc/dnsmasq.conf
```

И добавляем в неё строки (для удобства прям с первой строки файла):
```ini
no-resolv               # не будет использовать /etc/resolv.conf
domain=au-team.irpo
server=77.88.8.8        # адрес общедоступного DNS-сервера
interface=*             # на каком интерфейсе будет работать служба

address=/hq-rtr.au-team.irpo/192.168.100.1
ptr-record=1.100.168.192.in-addr.arpa,hq-rtr.au-team.irpo
cname=moodle.au-team.irpo,hq-rtr.au-team.irpo
cname=wiki.au-team.irpo,hq-rtr.au-team.irpo

address=/br-rtr.au-team.irpo/192.168.0.1

address=/hq-srv.au-team.irpo/192.168.100.62
ptr-record=62.100.168.192.in-addr.arpa,hq-srv.au-team.irpo

address=/hq-cli.au-team.irpo/192.168.200.14    # Смотрите адрес на HQ-CLI, т.к он выдаётся по DHCP)
ptr-record=14.200.168.192.in-addr.arpa,hq-cli.au-team.irpo

address=/br-srv.au-team.irpo/192.168.0.30
```

Теперь необходимо добавить в файл `/etc/hosts` следующую строку (после ip адреса используется TAB):

```bash
192.168.100.1   hq-rtr.au-team.irpo
```

Перезапускаем службу:
```bash
systemctl restart dnsmasq
```

Проверим пинг сначала с HQ-SRV на ya.ru и hq-rtr.au-team.irpo:
```bash
ping ya.ru
ping hq-rtr.au-team.irpo
```

Теперь проверим пинг с HQ-CLI:
```bash
ping ya.ru
ping hq-rtr.au-team.irpo
```

И проверим работу CNAME записей с HQ-CLI:
```bash
nslookup moodle.au-team.irpo
nslookup wiki.au-team.irpo
```

<br/>

Теперь необходимо перенастроить все машины на DNS-сервер HQ-SRV, кроме ISP и HQ-CLI:

Редактировать необходимо файл resolv.conf на внешнем интерфейсе, например `/etc/net/ifaces/ens18/resolv.conf`

```bash
nameserver 192.168.100.62
```

</details>

<br/>

## Задание 11

### Настройте часовой пояс на всех устройствах, согласно месту проведения экзамена

<br/>

<details>
<summary>Решение</summary>
<br/>

#### Настройка часового пояса на Alt Linux

На всякий случай ставим пакет:

```bash
apt-get install tzdata
```

Меняем часовой пояс следующей командой:
```bash
timedatectl set-timezone Europe/Moscow
```

<br/>

Проверяем:
```bash
timedatectl status
```
</details>

<br/>
<br/>

###### Не стоит воспринимать данную инструкцию, как истину в последней инстанции, она может оказаться неэффективной или вообще нерабочей. Описан метод, который оказался эффективным в одном из случаев, но не гарантирует аналогичный результат для всех.