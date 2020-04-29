### REF: https://fedoramagazine.org/using-the-networkmanagers-dnsmasq-plugin/


~~~
### los ya conocidos

$ cat /etc/hosts            #  asigna nombres a ip
$ cat /etc/resolv.conf      #  lista de servidores dns
~~~


~~~
### habilitar dnsmasq plugin

$ sudo vim /etc/NetworkManager/conf.d/00-dnsmasq.conf

[main]
dns=dnsmasq
~~~


~~~
### resolver nombre de dominio directamente

$ sudo vim /etc/NetworkManager/dnsmasq.d/00-vinicio.com.conf

address=/.vinicio.com/192.168.0.10
~~~


~~~
### reiniciamos el servicio

$ sudo systemctl restart NetworkManager
~~~


~~~
### y lo mas importante estudiar el trafico

$ sudo tcpdump -ni wlp2s0 udp port 53

### buscamos a google
$ dig google.com

### ahora a mi :3
$ dig vinicio.com
~~~
