# Catatan Ubuntu

Saat ini yang dipergunakan adalah Ubuntu 20.04. Untuk perintah perintah melihat perangkat jaringan yang terpasang di komputer, bisa menggunakan perintah:
* lspci
* lspci | less
* lspci | grep -i eth


Perintah untuk menampilkan Mac Address dari perangkat Ethernet card:
```text
lshw -C network
```

Referensi:

https://www.cyberciti.biz/faq/show-ethernet-adapter-ubuntu-linux/


Perintah untuk enable network card menggunakan logical name:
```text
ifconfig enp0s8 up
```

Referensi:

https://askubuntu.com/questions/965343/enabling-and-disabling-network-card-through-commandline


Cara menambah dan mensetting network card di Ubuntu 20.04:

https://linuxhint.com/ubuntu_20-04_network_configuration/


Tutorial bagus untuk setting IPTables:

https://youtu.be/XKfhOQWrUVw



_Salurkan donasi anda sebesar Rp 10.000 melalui : https://saweria.co/simpananfilepenting
Terimakasih_

_Please, send your donation as much as 1 USD through this link: https://paypal.me/ibnuchalid00
Thank you_
