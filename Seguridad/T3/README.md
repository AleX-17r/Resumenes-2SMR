Las copias de seguridad permiten la integridad y disponibilidad del sistema operativo, aplicaciones y datos, en caso de ocurrir un problema con estos.

---
Dentro de los tipos de Copias podemos diferenciar:
**Granularidad**:
 **Copia completa**: contiene todos los archivos
  - +Tamaño
  - +Fácil de recuperar
  - -Velocidad (creación)

 **Copia diferencial**: contiene archivos creados o actualizados desde la última **completa** 
  - Intermedio

 **Copia incremental**: contiene los archivos modificados desde su última copia. 
  - -Tamaño
  - -Fácil de recuperar
  - +Velocidad (creación)

**Operatividad del sistema**:
 **Copias en frío**: 
  - se hacen sobre archivos o bases de datos sin accesos
 **Copias en caliente**: 
  - El acceso a datos no se detiene, se realiza sobre archivos y bases de datos en uso.
---
**Director de Seguridad**
 - Marca las prioridades, los responsables y los recursos.

**Plan de Contingencia**: para responder lo más rápido y eficaz posible.
 - Define la información a incluir en las copias
 - El tipo de soporte (Discos duros)
 - Periodicidad y dónde (cada cuanto tiempo; en qué soporte)
 - Definir pruebas periódicas para verificar el buen funcionamiento.

---
#### Pasos a Seguir
Distinguir entre: 
 - Copia de seguridad de **Datos**: Copia los datos
 - Imagen de **Sistema**: Contiene el sistema operativo completo, con todos sus datos.
 Identificar datos a salvar:
  - Archivos
  - Sistemas complejos (Bases de datos)
 Frecuencia de soporte
  - Cada cuanto podemos hacerla (diaria, semanal,...)

---
Diferencias entre tipos de información:
**Confidencial**: 
 - Sensible o personal
 - Acceso restringido
 - En caso de salir, debe ser cifrada
**Interna**: 
 - Información de la orgranización, generalmente accesible a todos dentro de la organización.
**Pública**:
 - Cualquier información que no tenga restricción para difundir

----
#### Medios (Soporte)
Es importante la planificación de qué medio físico vamos a utilizar y para qué datos.
Los principales son:
 - **Cintas magnéticas**: duran muchos años
 - **Discos Ópticos**: Duran poco, no se usan para copias masivas
 - **Discos Duros**: facilidad de configuración, buen rendimiento, RAID
 - **Memorias Fash**: rápidos, pero caros, menor capacidad.
#### Nube
 - No requiere de una infraestructura local, es decir, no necesitamos los recursos hardware, ya que de eso se encargará la empresa que nos guarde los datos
 - Dependes de otra empresa
 - Es de pago
 - Se puede acceder a esa información desde cualquier lugar
#### Soluciones Mixtas
 Ofrecen una combinación de diferentes soportes:
 - D2D2T: Disk to Disk to Tape
 - D2D2C: Disk to Disk to Cloud
 - C2C: Cloud to Cloud
#### Estrategia 3-2-1
Disversifica las copias para garantizar que siempre sea recuperable.

Mantener 3 copias de cada archivo
Almacenar las copias en 2 soportes diferentes
Tener 1 copia de seguridad fuera de la empresa

---
#### Recuperación de datos eliminados
En caso de perder datos y no tener ninguna copia de respaldo, se puede acudir a una empresa espcializada, o usar herramientas como TestDisk 

---
#### Imagen de Sistema
Consiste en copia exacta de todo (OS, Aplicaciones, Archivos, ...)
Existen de diferentes tipos:
 - Disco a Disco: copia de un disco a otro
 - Partición a Partición: COpiar de una partición a otra (en el mismo disco o en otro)
 - Archivo de imagen: Se copia todo a una imagen de disco (.iso)

---
#### Poíticas de Copias de Seguridad
Definen el tipo de copias, periodicidad, soportes, y ubicaciones de centros de soporte.

**Centros de soporte**:son ubicaciones en las que se guardan las copias de seguridad, al crearse deben etiquetarse con:
 - Identificador: para identificarla
 - Tipo de Copia: indica si es Completa, Diferencial o Incremental
 - Fecha y hora: cuando se hizo
 - Contenido: el contenido que almacena
 - Personal a cargo: el técnico que realizó esa copia
 - Lugar: Ubicación física donde se encuentra

#### Recuperación:
**RTO: Recovery Time Objective**
  Es el tiempo máximo en que recuperar el servicio después de su caída.
  Se estima por el personal técnico.
**RPO: Recovery Point Objective**
  Determina el periodo máximo en el que se puede asumir una pérdida de datos, es decir, se tendrán que hacer las copias cada menos. Si se pasa este tiempo, podemos asumir que los datos están desactualizados.
**MTD: Maximum Tolerable Downtime**
  Determina el tiempo máximo de caída del servidor que podemos permitirnos
**ROL: Revised Operating Level**
  Nivel mínimo que debemos recueperar, aunque no sea el óptimo

#### Borrado de datos
  Cuando se deben retiran los soportes que han sido utilizados para realizar copias de seguridad, se deben destruir de forma segura.
  Es muy importante asegurarse de que esa información no vuelva a ser accesible para evitar accesos maliciosos
  Se debe subcontratar una empresa de destrucción certificada. (datos sensibles o personales)

   Para cintas o DVDs, lo mejor es triturarlos,
   Para Discos Duros o Pendrives, sobreescribir
#### Período de conservación de las copias
  Varía dependiendo de las necesidades de cada organización y sus requisitos legales.
  Debemos tener en cuenta:
   - La información es de utilidad? si no lo es se puede borrar, teniendo en cuenta el tiempo de mantenerlo por ley
   - Vida útil del soporte
   - Conservar diversas copias anteriores a la última realizada
   - ---
#### Cifrado
Debemos tener en cuenta que las copias de seguridad nos permiten integridad y disponibilidad, para tener también la confidencialidad, deberemos cifrar estas, así nos aseguraremos de que no las consigan usuarios ajenos.
