En primer lugar vamos a crear un script para ejecutarlas, este script, borrará las anteriores.

Esto nos permitirá hacer cambios fácilmente y sin que se nos acumulen reglas antiguas.

(el script en cuestión):
	#!bin/bash
	# eliminar reglas
	iptables -F INPUT
	iptables -F OUTPUT
	iptables -F FORWARD
	# políticas por defecto
	iptables -P INPUT DROP
	iptables -P OUTPUT DROP
	iptables -P FORWARD DROP

Explicación:
recordemos que -F borrará todo el contenido de la cadena; mientras que -P indica el comportamiento por defecto de  la cadena.



---
### Teoría
Tipos de Tabla
- **Filter**: Cadenas de filtrado (Accept/Reject/Mirror).
- **Nat**: Cadenas para cambios em dorección (Preroute/Postroute/Output).
- **Mangle**: Marca paquetes que cumplan con un partrón.

- REJECT: Rechaza los paquetes; avisa
- DROP: No toma los paquetes; NO avisa (como reject, pero sin avisar)
- ACCEPT: Permite que el paquete siga su camino.

- -j: Jump, especifica la acción a tomar cuado un paquete coincide con la regla definida

- sport: Start Port
- dport: Destination Port


Leerá las reglas de arriba a abajo.
Los paquetes pasarán por reglas hasta que se determine una acción (ACCEPT/DROP), en el caso de DROP, tirará el paquete, si es ACCEPT, lo aceptará y seguirá su camino normal.
Si no hay ninguna regla para ese paquete, utilizará la política por defecto.

---
### Presentación
Hola, soy Alejandro Hurtado, y voy a hablaros sobre IPTables
Estos son los principales puntos sobre los que voy a hablar.
Y bueno, para empezar, ¿Qué es?
Pues Iptables es un sistema de filtrado de paquetes, esto nos permite llevar un control de qué paquetes entran o salen de nuestra máquina.

¿Cómo funciona?
El administrador define unas tablas, que contienen cadenas de reglas.
Cada paquete pasará por al menos una cadena de filtrado antes de aceptarse o rechazarse.
Si no tenemos una regla específica para un paquete, tomará la política por defecto.

Sobre las reglas, aquí tenemos una regla con la que aceptamos conexiones web, -A es para añádir una nueva regla, -p, el protocolo del paquete, tcp, --sport 80, el puerto de inicio (S de Start), es decir el puerto del que viene, -j, la acción a tomar, en este caso queremos que acepte.

Y necesitaremos también una regla de Output, ya que con Input, nos puede llegar un mensaje, pero no podremos responder sin el Output.

Y las políticas por defecto, son el comportamiento que seguirá en caso de  no haber ninguna regla específica de ACEPTAR o RECHAZAR.
Es decir, si no hemos puesto ninguna regla para aceptar o rechazar Telnet, lo aceptará o rechazará con la política por defecto, aquí lo he puesto para que rechace todo lo que no se acepte, ya que siempre van a existir más protocolos de los que vamos a utilizar, y aceptar cosas que no vamos a utilizar, es un gran problema de seguridad, ya que deja muchos sitios por los que atacar a nuestra máquina.

Buene, dicho esto:
**Práctica** (1)
- Para activar IpTables, deberemos meter un "1" en este archivo de aquí,
- Si está desactivado, tendrá un 0.
- Pero nos interesa que esté activado, así que vamos a meter un "1"
**Práctica** (2)
- Una vez lo tengamos activado, podremos crear nuestras reglas.
- Para esto, vamos a crear este script, que borrará todas las reglas anteriores y generará las que le pongamos
- Usar este script nos permitirá hacer cambios fácilmente y sin que se nos acumulen reglas antiguas, ya que si empezamos a añadir reglas sin borrar las anteriores, se nos acumularán las antiguas, y nos pueden causar problemas.
- recordemos que -F borrará todo el contenido de la cadena; mientras que -P indica el comportamiento por defecto de  la cadena.
- (En este caso, este script lo rechaza todo, con lo que si lo activamos, perdemos la conexión)
**Cut Here to Activate FW**
- Si queremos evitar todas las conexiones sí nos sirve; es como este cable de red, que nos dice que cortemos aquí para activar el FW. XD
- Pero generalmente **sí** queremos alguna conexión, y más si es un servidor.
**Práctica** (3)
- Vamos a hacer una prueba de cómo funciona, y vamos a permitir sólo SSH (en este caso estoy conectado por SSH, con lo que es importante)
- Esta es una continuación del script anterior, estas son las reglas que va a seguir para aceptar conexiones SSH (imagen).
- Recordemos también que SIEMRPE debe haber una regla de INPUT y otra de OUTPUT.





