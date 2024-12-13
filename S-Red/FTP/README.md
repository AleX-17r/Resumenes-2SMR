#### ¿Qué es?
File Transfer Protocol, es un protocolo de transferencia de ficheros, este funciona con una comunicación Cliente-Servidor, usando **por separado** el **control** y los **datos**.

Los Usuarios se conectan con usuario y contraseña, se puede configurar el usuario "anonimous".

#### Seguridad
Por defecto no incluye un cifrado, para una conexión segura usaríamos **FTPS**, que cuenta con SSL, o reemplazarlo por **SFTP**, que funciona con SSH.

#### Historia
Originalmente se creó para **NCP** (Arpanet) en 1971, más tarde, en 1980, se sustituyó por **TCP/IP**.

Desde que existe, se han emplementado mejoras como el modo pasivo (1994) o extensiones de seguridad (1997).

#### Funcionamiento
Puede funcionar en modo activo o modo pasivo, esto determinará como establecer la conexión de datos.
**Siempre**
 - El cliente inicia la **conexión** al servidor 
 - Si la conexión se ha establecido, el servidor lo indicará.

**Dependiendo de si es Activo o Pasivo**

**En el modo activo**
 - El cliente indica que desea una conexión de **datos**, le indica un puerto y dirección IP. (comando PORT)
 - El servidor se conecta al cliente y establece la conexión de datos.
**En el modo pasivo**
 - El cliente inicia la conexión al servidor 
 - El servidor indica si se ha establecido la conexión
 - El cliente solicita una conexión de datos pasiva, (PASV)
 - El servidor abre un puerto aleatorio y se lo indica al cliente.
