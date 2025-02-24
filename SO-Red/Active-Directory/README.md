### ¿Qué és?
Es una herramienta que  permite administrar credenciales durante el inicio de sesión de los equipos de una red, nos permite también administrar las políticas de toda la red.
Es una base de datos jerárquica.

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
  
  **DNS**: Utiliza DNS para poner nombre a los dominios.
