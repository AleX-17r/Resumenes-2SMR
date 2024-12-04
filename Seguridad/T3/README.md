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

 **Copia integral**: contiene los archivos modificados desde última copia. 
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


---

Debemos identificar los datos a salvar (datos relevantes); 
La frecuencia en la que haremos las copias
Los archivos o sistemas complejos (bases de datos)

Images de disco: copia completa de TODO

Al crear una copia mantienes la integridad y la disponibilidad, en el caso de cifrarla, también entraría la confidencialidad

Copias de seguridad por sí mismas **NO** ofrecen confidencialidad, para ello hay que cifrarlas. Es un **peligro** si no se protegen.
