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

