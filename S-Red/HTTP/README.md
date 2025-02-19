apache2
host virtual en www.apellido.lan
host virtual en otraweb.apellido.lan
host virtual en miweb.apellido.lan


Protocolo de transferencia de hipertexto
Puerto **80** TCP
Se puede hacer con usuario y clave, en la actualidad no se suele utilizar.

http         ://  14.12.7.8 / index.html
protocolo    máquina    recurso

---
### Historia
Originalmente se creó como protocolo con el que transmitir información (hipertexto)

---
### Host virtual
Servidor pasa el recurso, el navegador declarará de qué máquina lo quiere, de forma que se puede crear varios host virtuales en una misma máquina.
(Varios recursos en un mismo servidor, virtualización de la que le gusta a Ricard)

Cabecera: contiene la máquina que nos va a dar el recurso. (puede ser virtual)


---
Un **User Agent** es el Navegador con el que lo abrimos.

---


Keep-alive: mantener la búsqueda activa; yes/no


---
### Verbos
Posibles peticiones al servidor web.

**Get**: pegado a la URL (?, parámetro = a otro).

**Post**: lo manda a través de cabeceras.

**Put**: enviar recurso al servidor (generalmente **no** se puede hacer)

**Delete**: borrar (generalmente **no** se puede hacer)

**Head**: como Get, pero **sólo** quiere las cabeceras.

---
### Respuesta
versión del protocolo: http 1.1    
código: 200OK

**1xx**

**2xx** (correcta) más común 200

**3xx** (redirección; el usuario tiene que hacer más cosas) más común 301

**4xx** (cabeceras); más común 404 (not found), 403 (forbidden)

**5xx** (internal server error); más común 500


(mirar códigos de respuesta)


Date: Fri, 20 Jan 2025 14:13:12 GMT

Content-Type: text/html

Content-Length: 8490 (tamaño del mensaje)

[espacio en blanco]
[Contenido]
< html> ... < /html>


---
### Seguridad
Mejor colocar datos en cabeceras, **NO** en la URL, la URL no va cifrada, se puede conseguir con un sniffer.

Si un recurso no existe, podemos hacer que devuelva en vez de un 404, un 200, a una página en la que indica que no existe.
Un programa malicioso podría buscar páginas típicas, si le devolvemos una página, le costará más.

Se puede configurar URL para dar los menos datos posibles. 

#### Certificado
El cliente puede tenerlo opcionalmente, servidor obligatorio

---

### Host Virtuales
ports.conf
Listen 80
       443 (requiere cargado SSL)

---

<VirtualHost *asterisco*: 80>
ServerAdmin   alex@hurtado.lan
DocumentRoot /var/www/miWeb
ServerName www.profe.com
ServerAlias profe.com

ErrorLog
CustomLog
</VirtualHost>



Usuario que ejecuta apache: www-data:www-data
En caso de no funcionar, cambiamos owner (chwon -R www-data:www-data /var/www/miweb)

---
Además: 
a2enmod ssl

en ambos casos: -> Sites-enabled

a2ensite www.hurtado.lan (como se llame el fichero)

(Práctica optativa: hacer alguna cosa chula con los logs)




sites-available

**apachectl**: herramienta de gestión de apache, recomendable utilizarla.

Una autoridad certificadora puede delegar en otra (si una dice que es cierto, la tora también)





4



puerto mayor a 1024 más recomendable, términos de seguridad.

---
Mediante HTTPS el **servidor se identificará SIEMPRE**, mientras que el cliente opcionalmente (normalmente **no**)
