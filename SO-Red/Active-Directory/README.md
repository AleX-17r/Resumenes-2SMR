### ¿Qué és?
Es una herramienta que  permite administrar credenciales durante el inicio de sesión de los equipos de una red, nos permite también administrar las políticas de toda la red.
Es una base de datos jerárquica.
### Cómo funciona?
Junta otros protocolos.
**Kerberos**: se levanta en un proceso y autentica.
**LDAP**: realiza consultas y autenticaciones en credenciales de susuarios.
**Grupos de seguridad**: 
**GPO**: Políticas de grupo
**Trazabilidad**: logs, SIEM, herramientas monitoring.
### ¿Para qué sirve?
- Gestiona permisos y accesos
- Gestiona políticas
- Control de identidades
- Registro y trazabilidad
- Escalabilidad
- Integrable con otras herramientas

---
### Componentes
 **Dominio**: es una colección de objetos dentro del AD que forman un conjunto administrativo, pueden existir diferentes dominios dentro de un bosque.
 Para poner nombre a los dominios utiliza DNS.
 
 **Unidad Organizativa (UO)**: es un contenedor de objetos, permite organizarlos juntos y simplifican la delegación de autoridad.

 **Objeto**: nombre genérico para referirnos a cualquier componente del directorio (impresora, carpeta, usuario, grupo, UO, ...). Se organizan en Usuarios, Recursos (elementos a los que acceder), Servicios (funciones a las que acceder).
 
 **Árbol**: colección de dominios con raíz común.
 (ej: dom1.apellido.lan; dom2.apellido.lan)
  Si se crea un usuario en un dominio, se reconoce en el resto que dependan de este.
  
  **Bosque**: mayor contenedor de AD, contiene los dominios, los cuales se conectan por Relaciones de Confianza Transitivas, que se contruyen automáticamente.
  El primero será el dominio raíz del bosqie que contendrá el Esquema del Bosque que compartirá con el resto de dominios.

  **Relación de Confianza**: son un método de comunicación seguro entre dominios, árboles y bosques; permiten que usuarios de un dominio se autentiquen en otro.
  
  **DNS**: Utiliza DNS para poner nombre a los dominios.

---
### Group Policy Objects (GPO)
### ¿Qué és?
Es un conjunto de reglas que controlan lo que los usuarios pueden hacer, esto permite una gestión centralizada de configuracion de equipos, cuentas de usuarios, y aplicaciones.
Controla lo que los usuarios pueden hacer.
Se crean con las herramienta Administración de Directivas de grupo.
Inicio → Herramientas administrativas → Administración de directivas de grupo.

---
### Prioridad en la ejecución de GPO
La configuración de la GPO se procesa en el orden:
- **Objeto de directiva a de grupo local**: Cada equipo tiene uno almacenado en local, controla el procesamiento de las directivas de equipo y usuario. son **las primeras que se ejecutan**. 
- **Sitio**: Todas las GPO vinculadas al sitio al que pertenece se ejecutan a continuación
- **Dominio**: Después las GPO vinculadas al dominio
- **UO**: las vinculadas a la UO
- **Controlador de Dominio**: por último, las vinculadas al Controlador de Dominio

---
### Directivas de Grupo por Defecto
La instalación de AD crea 2 GPO predeterminadas, que establecen configuraciones generales.
- **Default Domain Controller Policy**: opciones de configuración de directiva para Controladores de Dominio.
- **Default Domain Policy**: opciones de configuración de directiva para todos los equipos y usuarios del dominio.
Se recomienda dejar estas por defecto y crear otras.

### Creación de una GPO
Administración de directivas de grupo, seleccionamos nuestro dominio y abrimos el árbol, pulsamos botón derecho en el contenedor Objetos de Directiva de Grupo y escogemos Nuevo para crear una nueva GPO, que llamaremos Directiva1.

Para activarla la enlazaremos.
Desde "Configuración" podemos ver las configuracines que hemos activado.
### Edición de una GPO
Click derecho sobre la GPO y seleccionamos la opción Editar. Esto nos abrirá la ventana de edición de GPO
### Componentes de una GPO
Cada GPO consta de 2 partes principales:
- **Configuración del equipo**: configuraciones específicas de los equipos (cuotas de disco, auditorías, gestor de eventos, ...)
- **Configuración del usuario**: configuraciones específicas de los usuarios (aplicaiones, carpetas, elementos de escritorio, menú de inicio, ...)

Cada una de estas partes, se divide en 2 ramas:
- **Directivas**: incluye: 
    - Configuración de **software** (opciones de instalación automática), 
    - configuración de **Windows** (seguridad, scripts, redirección carpeta), 
    - **Plantillas admin**. (configuración del Registro de Windows, controlan funcionamiento y apariencia)
- **Preferencias**: incluye: 
    - Configuración de **Windows** (creación de variables de entorno, accesos directos, unidades de red), 
    - Configuración de **Panel de Control** (instalación de dispositivos, opciones de energía, tareas programadas, servicios,...)
### Intervalo de refresco
Por defecto tarda 90 minutos, es decir, si hacemos un cambio, puede tardar 90min en aplicarse, esto podemos forzarlo con **gpupdate /force**.
Para los usuarios, se aplicará al iniciar sesión y en el intervalo de refresco.
