## Resumen DHCP
Qué es? para qué sirve?
Es un protocolo de red que permite configurar automáticamente clientes para conectarse a una red.

Anteriormente se utilizaron RARP y BOOTP.

### ARP
Originalmente se crearon ARP (Addres Resolution Protocol), que permitía ver la MAC conociendo una IP, y RARP (Rerverse ARP), que asignaba una dirección IP asociada a una MAC concreta.

Para esto, el administrador configuraba en el servidor cada MAC y le asociaba una IP **manualmente**.

Con esta configuración, cada vez que se quisiera conectar un cliente con la MAC registrada, le asignaría su IP.

Aunque fue un avance no tener que configurar la IP manualmente cada vez que se quería conectar un cliente, tenía algunos problemas: 
 - Sólo asigna IP, no Gateway, ...
 - No asignaba máscara de subred, con lo que no podía el mismo servidor RARP trbajar en diferentes subredes (tampoco existía el Agente de Retransmisión)
 - Era costoso tener que registrar cada MAC, sobretodo si se cambiaban equipos, si se quería conectar uno nuevo, se debía configurar manualmente

(Apareció en 1982, quedó obsoleto por BootP, en la actualidad se utiliza en entornos virtuales)

---

### BOOTP
Dados estos problemas, se creó BOOTP, un protocolo que **sí** asignaba automáticamente los datos necesarios para conectarse a una red.

No sólo asignaba IP, podía asignar:
 - IP
 - Gateway
 - Imagen del sistema
 - **Máscara de Subred**
También, para trabajar en diferentes subredes, incorporó el Agente de Retransmisión

Un Agente de Retransmisión, es una máquina en la red que escucha las peticiones de conexión para BOOTP, y las envía por Unicast al servidor, su respuesta se la devuelve al cliente.
Esto se utiliza cuando queremos que se conecte a la red un cliente que está en una subred diferente al servidor.

#### Funcionamiento:
Se le configuran inicialmente unos parámetros, como por ejemplo:
 - Dirección de Red
 - Gateway
 - Imagen de Sistema
Se mantenía a la escucha en el puerto 67.
Cuando un cliente se inicia, envía un paquete UDP en Broadcast, este mensaje es un formulario con campos a rellenar, e incluye su dirección MAC para que el servidor le responda
El servidor, cuando lo recibe, rellena los datos y se lo envía por Unicast a la MAC
	(en el caso de un agente de retransmisión, pasaría por este entre el servidor y el cliente)
El cliente, una vez lo recibe, se configura para poder iniciarse en la red.
	 (en el caso de necesitar un OS, el servidor le enviaría una imagen con la que arrancar)


A pesar de traer tantas ventajas, no tenía un control de las direcciones en desuso, con lo que se podían agotar. 
Cuando la asignaba a un cliente, no la volvía a asignar a otro.

(Apareció en 1985, quedó obsoleto por DHCP, en la actualidad se utiliza para instalar o arrancar sistemas por red en varias estaciones)

----
### DHCP
Apareció como una extensión de BOOTP, lo que lo hace compatible con este.
Su principal diferencia, es que asigna las direcciones de forma **dinámica** y tiene un control de direcciones en desuso, lo que dificulta quedarnos sin direcciones disponibles.

Su funcionamiento, es similar al de BOOTP, pero con más mensajes para conceder una dirección.

 - **DHCPDISCOVER**: el cliente busca servidores disponibles.
 - **DHCPOFFER**: el servidor responde al cliente.
 - **DHCPREQUEST**: el cliente solicita los parámetros que le ofrece el servidor
 - **DHCPACK**: el servidor confirma los parámetros de configuración al cliente
 - **DHCPNACK**: el servidor rechaza la solicitud
 - **DHCPDECLINE**: el cliente rechaza la configuración.
 - **DHCPRELEASE**: el cliente informa al servidor de que no va a continuar utilizando la dirección.



----
Cosas a tener en cuenta:
 - Los mensajes Broadcast no son enrutables
 - BOOTSTRAP Protocol: Hace referencia a que se ejecuta al inicio.
