qué es? para qué sirve?
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

---

