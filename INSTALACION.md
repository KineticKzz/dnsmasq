# INSTALACION Y CONFIGURACION DE DNSMASQ

## CONFIGURACION SERVIDOR

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

``echo "local=/sergio.es/" >> /etc/dnsmasq.conf``

Con la primera linea hacemos una copia de seguridad del fichero antes de modificarlo, con la segunda le decimos al servicio dns donde quiero que vaya, y, con la tercera linea le decimos que utilice  el archivo /etc/hosts para identificar los dominios.

Y así deberia quedar nuestro fichero /etc/hosts

![img](https://i.imgur.com/E2LuLY2.png)

Ejecutamos:

``systemctl restart dnsmasq``

Y nos deberia quedar de la siguiente manera:

![img](https://i.imgur.com/y690hsH.png)


## CONFIGURACION CLIENTE
En el cliente solo tenemos que configurar la ip, dandole la que pusimos anteriormente en /etc/hosts en el servidor.

Y los dns, dandole la ip del servidor (red interna)

Por lo tanto:

![img](https://i.imgur.com/8MYHQPl.png)

![img](https://i.imgur.com/l1UMRR3.png)
