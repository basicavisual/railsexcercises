# Aprende sobre por qué funciona cuando escribes localhost:3000 en lugar de una ip

Localhost, es el nombre que se le da a la loopback device, una interfaz de red virtual que sirve para que la computadora se comunique consigo misma a través de protocolos de red. Este setup tiene como propósito que en una computadora tenga la doble función de servidor y cliente en sí misma, es decir, que se puedan correr aplicaciones que implican o emulan conexiones de red. Este setup le permite al desarrollador testear y diagnosticar su app en una computadora o servidor local, pero también permite, por ejemplo, conectar diferentes recursos de una aplicación en un mismo equipo (ie. una base de datos MySql que sólo reciba conexiones locales y una aplicación PHP) de tal modo que agrega una capa adicional de seguridad a la misma.

Localhost es el nombre de host mapeado a la ip 127.0.0.1 (por lo regular), que representa el vínculo de la computadora actual consigo mismo. Rails utiliza el puerto :3000 de esa conexión, lo cual permite al desarrollador seguir usando localhost (que por default es el puerto 80) testear aplicaciones en un servidor apache.

Explicación más amplia sobre qué es un loopback device, [aquí](http://askubuntu.com/questions/247625/what-is-the-loopback-device-and-how-do-i-use-it).


Sobre el uso de localhost con MySQL [ver aquí](http://unix.stackexchange.com/questions/184447/whats-the-difference-between-a-machines-ip-address-and-localhost).
