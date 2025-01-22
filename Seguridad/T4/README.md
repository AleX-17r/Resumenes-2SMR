### Introducción
La criptografía busca mecanismos para cifrar datos de un emisor a receptor.
Su finanlidad es conseguir la confidencialidad, de forma que si un mensaje se intercepta por un tercero, que no pueda entenderlo.

**Criptología**: estudio de criptosistemas
**Criptografía**: codifica un mensaje
**Criptoanalisis**: rompe las claves para descifrarj
**Criptosistema**: conjunto de claves y equipos utilizados para cifrar.

Tiene 3 fases principales:
- **Cifrado**: Transforma el contenido para que no se entienda.
- **Autenticación**: Método para assegurar la identidad de alguien. 
- **Firma**: Garantiza la identidad en un mensaje, usa clave pública y privada. se cifra la identidad del emisor con privada y descifra con pública.

---
### Criptografía clásica
Se basaba en intercambio de letras, la ocultación de un mensaje dentro de otro, etc...
- **Transposición**: dígitos cambian de posición.
- **Permutación/Sustitución**: cambian los dígitos por otros.
- En la antigua Grecia se utilizaba la **Esteganografía**, que ocultaba el mensaje en sí mismo (como tinta invisible).
### Historia
- **Piedra Rosetta** (196 a.C.): descifra jeroglíficos.
- **Escítala** (400 a. C.): el primer sistema de transposición, espartanos.
- **Cifrado César**: Cifrado por sustitución, época romana.
- **Escritura en espejo**: escribir en dirección opuesta, Leonardo Da Vinci, renacimiento.
- **Discos de Alberti**: Leon Battista Albert, sustitución polialfabética, 1466.
- **(Tabla sustitutción)** (1523): primer método compuesto, función lineal, sustitución, inventado por Blaise de Vigenére.
- **Enigma**: máquina desarrollada en Alemania, 1920.
- **Purple**: máquina de cifrado japonesa.
- **SIGABA**: máquina desarrollada por EUA.
- **TIPEX**: desarrollada en Inglaterra, 1937.

### Criptografía moderna
Comienza con Claude Shannon, cuando público el atículo "Communication Theory of Secrecy Systems" (1949), en el que describía la modernización de las técnicas de cifrado anteriores con procesos matemáticos avanzados.

Sus trabajos se han convertido en las bases de la criptografía moderna.

La criptografía deja de ser artística y se convierte en científica.

**Cifrado de Vernam**: cifra un texto plano con una serie cifrante.

---
### Elementos de un Criptosistema
- **Mensajes sin cifrar**: documento original.
- **Mensajes cifrados (criptogramas)**: una vez se ha cifrado. (C)
- **Conjunto de claves**: datos o claves para cifrar (K)
- **Transformación del cifrado**: existe una transformación diferente para cada K. (E)
- **Transformación de descifrado**: (D)

---
### Tipos de clave

**Simétrica**: se utiliza la misma clave para cifrar y descifrar.
- Es rápido y eficiente.
- Necesita una clave diferente por cada par de interlocutores
- Requiere control para el intercambio de claves
- Vulnerable a ataques de fuerza bruta.

**Asimétrica**: utiliza un par de claves, una privada que sólo conoce el propietario y una pública que puede conocer cualquiera; se cifra con una y se descifra con la otra.
- la clave pública se distribuye libremente, no hay problemas de intercambios
- Menos rápido que la simétrica
- Cifrados son más grandes que la versión original

---
### Algoritmos de cifrado
**DES**: Data Encryption Standard, usa criptografía simétrica, su versión mejorada es **3DES**.    
    (usaba claves de 56bits).
**AES**: Advanced Encryption Standard, criptografía simétrica, usa claves mayores, sustituyó DES en 2002.
**Hash**: Garantiza la integridad, mapea el contenido de un conjunto de datos.

---
### Métodos de cifrado
- Por **Bloques**: divide el mensaje en pequeños fragmentos y los cifra, llena el último bloque de información no útil (para que todos queden igual)
- Por **Flujo de Datos**: procesa la información secuencialmente y en tiempo real.

---
### Firma Digital
Es el conjunto de datos que se añade al mensaje original para asegurar la dentidad y el contenido.
- **Verifica** que es del emisor que dice ser
- **Integridad**, el mensaje se mantiene igual que cuando se ha firmado
- **No repudio**, quien firma no puede decir que no lo ha hecho
**Funcionamiento**:
crea un resumen hash del documento original, este se cifra con clave privada y se envía junto al documento.

---
### Certificados
Garantizan vínculos existentes (persona, entidad, claves, ...).
Es un documento identificado por un número de serie único, también tiene un periodo de validez.
Lo emite una **Autoridad de Certificación** (ej: Fábrica Nacional de Moneda y Timbre).

Contiene:
- Nombre, dirección
- Identificación
- Clave pública
- Número de serie
- Fecha de emisión y expiración
- Firma digital
 
---
### PKI
La Publick Key Infrastructure, es el conjunto de recursos, procedimientos de actuación, personas y herramientas que permiten implantar un sistema de seguridad mediante clave 
pública.

No dependen de ninguna tecnología, son un conjunto de reglas para establecer comunicaciones seguras.
Proporciona un entorno de trabajo que se adapta a cada caso.

- **Suscriptor**: quien pide claves y certificado
- **Autoridad de registro**: encargada de identificar usuarios
- **Autoridad de Certificación (AC)**: Entidad de confianza que da legitimidad a una relación de clave y usuario
- **Consumidor**: validan el certificado (navegadores web).

Hay diferentes tipos de certificado: 
- **Certificado de firma electrónica**: para firmar documentos
- **SSL/TLS**: Sitios web.

---
### DNI Electrónico
Es una versión avanzada del físico, es compatible con estándares europeos.
Cada 2 años se debe renovar con huella dactilar.

---
### Protocolos Seguros
- **Secure Shell (SSH)**: Conexión remota segura.
  Proporciona una sesión cifrada con autenticación de clave pública.
- **Secure Socket Layer (SSL)**: Establece una conexión segura cliente-servidor.
  Trabaja a nivel de transporte, con niveles y funciones definidas.
- **Transport Layer Security (TLS)**: evolución de SSL, garantiza intercambio de datos en entornos seguros, (HTTP, IMAP, FTP, POP3, LDAP)
- **IP Security (IPSec)**: a nivel de red, ofrece seguridad a IP y superiores,
  Muy utilizado en VPNs, permite crear túneles, es de IPv6, lo cifra todo.

---
### Cifrado de archivos
Consiste en convertir una información legible en ilegible, mediante un algoritmo seguro.
