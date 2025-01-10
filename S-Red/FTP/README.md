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
 - El cliente solicita una conexión de datos pasiva, (PASV)
 - El servidor abre un puerto aleatorio y se lo indica al cliente.

**El servidor responde a la conexión** con un estado de 3 dígitos de carácteres Ascii ("200", "200 OK"), indicando que se ha conectado con éxito.
(Los números representan el código de respuesta, el texto opcional, es legible por humanos).

Siempre necesita 2 puertos, uno para enviar y otro para recibir.

**Tipos de Datos**:
 - **ASCII**: Usado para texto. (Tipo A)
 - **Imagen/Binario**: envía byte a byte el archivo. (Tipo I)
 - **EBCDIC**: Texto plano EBCDIC (Tipo E)
 - **Local**: Para máquinas que no usan 8-bits, pueden ser "L9, L36". (Tipo L _n_)
 - **Unicode**: Texto en UTF-8. (Tipo U)

**Estructuras de Archivos**
 - **F**: FILE, los archivos son una secuencia de bytes, carácteres o palabras.
 - **R**: RECORD, los archivos se dividen entre registros, que tienen longitud fija o variable.
 - **P**: PAGE, los archivos se dividen en páginas, que contienen datos o metadatos.

**Modos de Transferencia de Datos**
 - **S**: Stream, los archivos se envían con flujo continuo.
 - **B**: Block, organiza los datos en bloques y los envía por TCP.
 - **C**: Compressed, extiende el modo B con compresión.

**Inicio de Sesión**
 Usa usuario y contraseña, el **usuario** se envía al servidor usando el comando **USER**, y la contraseña con el comando **PASS**. 
 Permite también el usuario Anonymous, este usuario no requiere contraseña, lo que es especialmente útil en casos en los que no nos interesa dar de alta a todos los usuarios 
 La conexión no es cifrada, lo que lo hace vulnerable ante ataques de sniffing.

**Métodos Seguros**
Dado que FTP por defecto **no** es seguro, surgieron diferentes versiones en las que se intentaba hacer más seguro, algunas de ellas son:
 - **FTP a través de SSH**: Crea un tunel FTP normal, pero a través de una conexión SSH.
 - **FTPS**: Es una extensión que cifra las conexiones mediante comunicaciones SSL o TLS, usa el comando "AUTH TLS", (Transport Layer Security; Secure Sockets Layer).
 - **SSH FTP**: Está diseñado específicamente para la transferencia de archivos, los envía a através de SSH.
 
 También para entornos en los que importa más la velocidad, se creó,
  - **TFTP**: Envía en UDP, lo que permite una transferencia rápida.

**Comandos**

**Códigos de Respuesta**
 - **2yz**: Respuesta con éxito.
 - **4yz / 5yz**: Respuesta fallida.
 - **1 yz / 3yz**: Error o respuesta incompleta.
 - **x0z**: Error de sintaxis.
 - **x1z**: Error en la solicitud de información.
 - **x2z**: Responde al control de conexiones de datos.
 - **x3z**: Autenticación del proceso de inicio de sesión.
 - **x5z**: Estado del servidor FTP en la transferencia de archivos.
