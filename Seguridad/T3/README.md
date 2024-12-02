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

---

Debemos identificar los datos a salvar (datos relevantes); 
La frecuencia en la que haremos las copias
Los archivos o sistemas complejos (bases de datos)

Images de disco: copia completa de TODO

Al crear una copia mantienes la integridad y la disponibilidad, en el caso de cifrarla, también entraría la confidencialidad

Copias de seguridad por sí mismas **NO** ofrecen confidencialidad, para ello hay que cifrarlas. Es un **peligro** si no se protegen.
