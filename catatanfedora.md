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


