
### Protección Física
Su planificación debe asegurar la protección de los activos físicos y debe prevenir futuros rediseños.

Los Centros de Procesamientos de Datos (CPD) son grandes salas donde se concentra la mayoría de la tecnología de una organización.
Estos están compuestos por:
 - Instalación física: área y espacios
 - Suministro eléctrico: energía, SAIs
 - Climatización: elementos que extraen el calor.
 - Sistema de protección contra incendios: Sistemas de detección y extinción
 - Diseño de la red: Racks, topologías de re, cableado, ...
 - Sistemas de seguridad: identificación, videovigilancia, monitoramiento.
Para mantener estos entornos seguros, debemos tener en cuenta:
 - Espacio y accesos
 - Accesos para operaciones
 - Accesos centralizados
 - Salidas de emergencia
 - Evitar interferencia electromagnética
 - Control de inundación
 - En subsuelo o plantas intermedias.

**Control de acceso**, debemos evitar el acceso no autorizado. Podemos con:
 - Sistemas de vigilancia: ej. cámaras
 - Código de seguridad: ej. contraseñas
 - Acceso mediante dispositivos: ej. llaves, tarjetas.
 - Sistemas biométricos: ej. huella dactilar

**Ubicación**, se recomienda una zona diáfana, lejos de zonas de riesgos. Debemos tener en cuenta en caso de cambiar los equipos y la salida de emergencia.
También los sistemas que produzcan ruido o vibraciones, deben estar en zonas que se puedan amortiguar.
Debe haber la menor interferencia magnética posible.

**Condiciones**:
 - Facilitar planificación de uso de energía
 - Estudio de comunicaciones, cableado, armarios, ...
 - Analisis de climatización
 - Estructura, debe ser lo suficientemente fuerte
 - Previsión de elementos voluminosos
 - Espacio que ocupan los equipos
Para los **suelos**, se recomienda que sean suelos flotantes, ya que permiten pasar el cableado, paso de aire acondicionado, y detección y extinción de incendios.
Pavimentación antiestática, para evitar el polvo.
Para el techo, también se recomienda, se suele utilizar para sistemas antiincendios.

Es importante tener en cuenta:
 - Enchufes
 - Comunicaciones
 - Climatización
 - Salida de emergencia
 - Elementos voluminosos y pesados
 - Vías, suelos, espacios y divisiones

**Ambientales, eléctricas y detección de incendios**
Es necesario tener un control de la temperatura y humedad.
Debe haber pasillos fríos y calientes, para así garantizar la refrigeración de los equipos.
También debe haber un apagado de emergencia.
El cableado, para evitar interferencias o incluso chispas, se deben cubrir con un tubo corrugado.

Con respecto a los aspectos eléctricos, los circuitos eléctricos deben estar aislados, tamibén hay que tener en cuenta conductos de agua y sistema antiincendios.
Debe haber diferenciales, interruptores magneto-térmicos, ...
Regletas de distribución, son regletas que alimentan un Rack, se deben dsitribuir correctamente.
Es importante tener tomas de tierra.

Los picos de tensión pueden ser fatales, debe haber elementos que protejan a los equipos (estabilizadores de voltage).

Es importante tener en cuenta:
 - Apagado de emergencia
 - Cableado
 - Conductos eléctricos
 - Diferenciales
 - PDU (Regletas dist)
 - Toma de tierra
 - Transitorios (regular picos)
 - Control de voltage

Con respecto a los incendios, todos los materiales de la sala, deben ser imnífugos, y deben ofrecer resistencia contra el fuego, el agua también es peligrosa, todo debe estar sellado, para esto podemos usar **pasamuros**.

Los elementos principales de la detección de incendios son:
 - Señalización
 - Detectores
 - Pulsadores manuales
 - Sistemas auxiliares
La extinción del incendio puede ser mediante gas o agua nebulizada;
El gas, no conduce la electricidad, no deja residuos, actúa más rápidamente y provoca menos daños.

Es importante tener en cuenta:
 - Pasamuros
 - Alarmas
 - Central, detectores, ....
 - Extinción por agua nebulizada
 - Estanquedad (de lo que se utilice para extinguir el incendio)
 - Refrigeración

Para el diseño de la red y recuperación ante desastres,
Los armarios necesitan llave, targetas, o sistemas biométricos.

Para prevenir desastres, se utilizan DRS (Disaster Recovery Sites), que son répiclas del CPD principal, en caso de que falle, podremos utilizar este.
Para esto, existen 3 formas, que varían en coste y velocidad.
 - Cold Site: es un espacio con todo lo necesario para trasladar nuestros servidores
 - Hot Site: Tiene todo funcionando, sólo habría que trasladar los datos
 - Mirror Site: los datos son replicados en tiempo real
 - Mutual Backup: se llega  aun acuerdo con otra organización, estas reservarán un espacio en su CPD para la otra.
 - Activo-Activo: Los sistemas están configurados en clústeres geográficos, esto permite que no se pierda ningún momento.

---

### SAI
Es un dispositivo que suministra energía en caso de interrupción eléctrica (funciona con baterías y correctores de corriente)

Los problemas de suministro eléctrico pueden deberse a:
 - Errores humanos, cortes, interrupciones, sabotages, cortocircuitos
 - Inundaciones, tempestas, vientos fuertes, terremotos
 - Interferencia generada por elementos como ascensores, gruas, equipos de soldadura, máquinas con motores.
 Imperfectos de la alimentación eléctrica:
  - Corte de energía
  - Distorsión
  - Microcortes
  - Ruido eléctrico
  - Subidas de tensión
Conceptos:
 - Carga: conjunto de equipos conectados
 - Autonomía: tiempo que puede suministrar energía a una carga
 - Capacidad: potencia máxima que suministrar a la carga
El SAI está compuesto por:
 - Batería
 - Bloque bypass: conmuta entre energía eléctrica que ofrece el SAI y la red.
 - Bloque rectificador: asegura que el SAI pueda mantener las baterías cargadas y proveer energía constante y limpia.
 - Bloque inversor/ondulador: convierte entre contínua y alterna.
 - Filtro: elimina perturbaciones de la red
 - Panel de control, informa sobre el estado del SAI
 - Pulsador de emergencia: permite la desonexión total e inmediata.
 - Software de control y comunicación
Los diferentes tipos son:
 - Estático:  conmuta entre energía de la red y de la batería.
 - Mecánico o Rotativo: tiene motor (combustión o corriente continua).
 - Híbrido o Mixto: mezcla elementos estáticos y mecánicos.
Sus modos de funcionamiento son:
 - Offline: conmuta entre corriente de la red y su batería
 - Line Interactive: Además filtra la señal
 - Online: Proporciona su propia energía al equipo mientras carga sus baterías, lo que ofrece mayor estabilidad y protección.
Con respecto a la configuración, se puede hacer de forma:
 - Distribuida: cada equipo en un SAI diferente
 - Centralizada: Todos los equipos están en el mismo SAI
Su arquitectura, puede ser:
 - Modular: varios SAIs independientes funcionando juntos como módulos para uno sólo.
 - Modular Granual: en caso de que uno falle, no afecta al ersto
Comunicación: normalmente se utiliza una aplicación con la que monitorear (los SAIs tendrán tarjeta de red).

Para diferenciar SAIs, nos fijaremos en sus características, como:
 - Autonomía (tiempo que puede alimentar)
 - Potencia (La energía que puede suministrar)

### Calcular Potencia de un SAI
 (se mide en)
  - Intensidad - A
  - Voltage - V
  - Potencia - W
Pasar Voltiamperios (VA) a Watts (W)
	W = VA×fdp
Calcular Potencia a partir de Intensidad y Voltage
	P=V×I

---

### Dispositivos de Almacenamiento
Pueden ser
 - Dispositivos locales 
 - (Continuar página 51)
