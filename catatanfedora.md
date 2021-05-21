# Catatan Fedora

Sedang menggunakan **Fedora 34** di Virtualbox. Untuk update repository menggunakan perintah:

* yum clean all
* yum check-update
* yum update

Ingin membuat Fedora menjadi mesin proxy, sebagai clientnya adalah ubuntu 20.04. Proxy yang ingin dibuat adalah SSH Proxy, Web Proxy (menggunakan Squid), Reverse Proxy. Untuk tambahan bahan belajar nantinya bisa membuat Tor Proxy, VPN Proxy.

**SSH Proxy**

Berguna untuk menghubungkan perangkat-perangkat IT yang berada secara remote. jadi perangkat perangkat itu bisa di manage secara remote melalui CLI.

**Web Proxy**

Berguna untuk memblokir iklan-iklan di website-website, mengamati situs-situs apa saja yang dibuka, mengatur bandwidth user maupun situs yang dibuka.

**Reverse Proxy**

Untuk memanfaatkan IP Publik yg cuma 1 buah dan 1 port, namun dari internet bisa mengakses berbagai komputer dan server yg ada di belakang proxy. nantinya nama domain bisa dipanjangkan, untuk mengakses server dan perangkat perangkat yg berbeda dari internet. Contoh:

server1.pisang.com

server2.pisang.com

laptop1.pisang.com

laptop2.pisang.com

pc1.pisang.com

pc2.pisang.com


Karena cuma mau menghubungkan 2 buah komputer, maka hitungan IP Address seperti ini sudah cukup:
```text
IP		    Mask			        Notes ...
1.1.1.0		255.255.255.252		Subnet Address
1.1.1.1		255.255.255.252	
1.1.1.2		255.255.255.252	
1.1.1.3		255.255.255.252		Broadcast Address
```

Perintah **nmcli** untuk menampilkan status interface-interface network di **Fedora 34** :
```text
nmcli dev status
```

maka contoh hasil perintah di atas :
```text
DEVICE  TYPE      STATE      CONNECTION
enp0s3  ethernet  connected  enp0s3
enp0s8  ethernet  connected  Wired connection 1
lo      loopback  unmanaged  --
```

Perintah lainnya di Fedora 34 yang penting untuk mensetting jaringan:
```text
ifconfig -a
```
Perintah ini juga berfungsi untuk melihat status/info interface-interface jaringan di Fedora 34.

maka contoh hasil perintah di atas:
```text
enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.4  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::a00:27ff:fe9f:3466  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:9f:34:66  txqueuelen 1000  (Ethernet)
        RX packets 433  bytes 44679 (43.6 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 385  bytes 44255 (43.2 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 1.1.5.1  netmask 255.255.255.252  broadcast 1.1.5.3
        inet6 fe80::d474:fd2d:1019:b7fc  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:2f:e3:a9  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 24  bytes 1732 (1.6 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 4  bytes 424 (424.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4  bytes 424 (424.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
 ```
 
 Ini perintah yang penting untuk melihat **UUID** dari interface jaringan di Fedora 34. Dikarenakan UUID ini berfungsi untuk mensetting IP statik :
 ```text
 nmcli con show -a
 ```

Maka hasil dari perintah di atas seperti ini:
```text
NAME                UUID                                  TYPE      DEVICE
enp0s3              b9532473-c3e4-3579-95d3-f548a1c918fd  ethernet  enp0s3
Wired connection 1  8d9f4859-91c4-33d2-be3a-62ae7688b357  ethernet  enp0s8
```

## IPTables

Perintah untuk melihat aturan IPTables yg sedang berjalan:

```text
iptables -L
```

Cek status IPTables yang sedang berjalan:
```text
iptables -L -v
```

