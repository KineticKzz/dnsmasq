# INSTALACION Y CONFIGURACION DE DNSMASQ

## SERVIDOR

Primero vamos a descargar el paquete
``apt install dnsmasq``

``systemctl enable dnsmasq``

``systemctl start dnsmasq``

Vamos a hacer la práctica con dos tarjetas de red, una como adaptador puente o NAT y la otra interna que será la que comunique con el cliente.

Tal que así:
![img](https://i.imgur.com/GyizbEH.png)

``systemctl restart networking``

A continuación ejecutamos los tres siguientes comandos:
``cp /etc/dnsmasq.conf /etc/dnsmasq.conf.ORIGINAL``
``echo "server=/sergio.es/192.168.1.1" >> /etc/dnsmasq.conf``
``echo "server=/sergio.es" >> /etc/dnsmasq.conf``




