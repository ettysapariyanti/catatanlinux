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


