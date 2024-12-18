Base de datos Distribuidas.
Deben acabar en "."; ej. "www.dominio.com."

Capas:
Transporte -> Socket (IP, puerto)
Interred -> IP
Enlace/Física -> MAC


​￼### Hosts
IP - Nombre Host
IP - Nombre Host
... - ...


TTL: Tiempo de vida, cuando acaba, expira

---
Cuando los servidores secundarios quieren copiar el principal, preguntan qué número de serie tiene (versión). Cada vez que se actualiza el primario se debe cambiar su número de serie, para que los secundarios se enteren de que deben actualizarse

---
​￼**Zona**: espacio en el que tiene autoridad servidor, contiene todos los subdominios. (estructura árbol)
 - Puedes delegar un subdominio a un tercero
**Registro Glue**: Conoce otras zonas independientes.

Un mismo recurso **NO** puede estar en 2 zonas diferentes (Son **Disjuntos**, **NO se solapan**).

**Registros Tipo A**: 
  - Traducen entre nombres de recurso de dominio a direcciones (IP).
  - Si un registro está duplicado (mismo dominio 2 IPs), seleccionará una de las IPs, útil para repartir tareas entre más de un servidor.

**Registros Tipo AAAA**:
 - Igual que tipo A, pero en IPv6.

**Registro MX**:
 - Da el nombre del servidor de correo de un dominio (o subdominio)
 - Contiene una prioridad, siendo el menor número el de mayor prioridad.
 - Sólo resuelve nombres, **NO** puede resolver con alias.

**Tipo CNAME**: 
 - Pasa de un alias a una búsqueda de nombre
 - Resuelve igual que el dominio al que está asociado, es decir, si cambia la dirección de un tipo A al que está asociado, también en este.

**Tipo NS**:
 - Servidores DNS.

**Tipo SOA**:
 - Contiene información importante del dominio, la consultan otros servidores.
 - Es principalmente para comunicarse con secundarios.
 - Se puede poner en una línea, o ir a la siguiente indicándolo con "("
 - En el email, el primer . es un @
 - Contiene número de serie

**Tipo TXT**:
 - Puedes escribir cualquier texto
 - Se utiliza para demostrar que tienes el control, es decir, si una empresa te pide que se lo demuestres, le puedes escribir un texto.
 - -all = todo lo que esté antes lo rechaza; +all = lo acepta; ~all = lo pone en duda
 - spf: permite declarar otros dominios que hablen en tu nombre (enviar emails).

**Tipo PTR**
 - Resuleve de una dirección IP a un nombre de recurso.





	Dominio.com.
www.dominio.com.     A      7.12.3.191
ws.dominio.com.         A      8.13.5.14
dominio.com.               A      7.12.3.191
web.dominio.com. CNAME www.dominio.com. (Resolverá el dominio)
dominio.com.           MX  10 mail.dominio.com.
dominio.com.           MX  15 mail3.dominio.com.
dominio.com.           MX  10 mail2.dominio.com.
dominio.com            NS        ns1.dominio.com.
dominio.com            NS        ns2.dominio.com.
ns1.dominio.com         A        IP
ns2.dominio.com        A        IP
dominio.com             SOA     ns.dominio.com.     admin.dominio.com. (
1 ; número de serie
3600 ; intervalo de refresco (en segundos). refresh
600 ; retry. el secudario itentará reintentar configurarse
36000 ; expira. el secudario se desconfigura
600 ; TTL negativo. el tiempo que puede cachear respuestas negativas
)
30.28.8.2.in-addr.arpa. PTR www.dominio.com.


