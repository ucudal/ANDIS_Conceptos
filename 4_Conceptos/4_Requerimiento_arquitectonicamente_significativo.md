# Conceptos

## Requerimiento arquitectónicamente significativo

Un requisito arquitectónicamente significativo —o ASR, *architecturally
significant requirement* por sus siglas en inglés— es un requerimiento que
tendrá un efecto profundo en la arquitectura, es decir, la arquitectura podría
ser radicalmente diferente si no existiera ese requerimiento[^1].

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Los requerimientos arquitectónicamente significativos a menudo —pero no siempre—
toman la forma de requerimientos de [atributos de
calidad](./4_Atributos_de_calidad.md): el rendimiento, la seguridad, la
capacidad de ser modificado, la disponibilidad, la facilidad de uso, etc., que
la arquitectura debe proporcionar al sistema.

### Fuentes

Los requerimientos arquitectónicamente significativos deberían estar obviamente
en el documento de especificación de requerimientos como [requerimientos
atómicos](/3_Plantillas/3_1_Requerimiento_atomico.md), en particular como
requerimientos de tipo no funcional, restricciones del proyecto o de diseño, o
como impulsores.

La realidad es que mucha de la información en esos documentos no afecta la
arquitectura; sólo la que corresponda con atributos de calidad.

Los requerimientos que están documentados como tales son explícitos; los demás
son implícitos[^2].

Algunos requerimientos arquitectónicamente significativos se derivan de los
objetivos del negocio como veremos más adelante.

Aunque no estén en forma explícita, otros requerimientos funcionales pueden
implicar requerimientos arquitectónicamente significativos. Algunas cosas
específicas a buscar son las siguientes:

* **Uso**. Roles de usuario versus modos de sistema, internacionalización,
  distinciones de idioma.
* **Tiempo**. Oportunidad y coordinación de elementos.
* **Elementos externos**. Sistemas externos, protocolos, sensores o actuadores
  —dispositivos—, middleware.
* **Redes**. Propiedades y configuraciones de red —incluidas sus propiedades de
  seguridad—.
* **Orquestación**. Pasos de procesamiento, flujos de información.
* **Propiedades de seguridad**. Roles de usuario, permisos, autenticación.
* **Datos**. Persistencia y vigencia.
* **Recursos**. Tiempo, concurrencia, uso de memoria, planificación, múltiples
  usuarios, múltiples actividades, dispositivos, uso de energía, recursos
  blandos —por ejemplo, buffers, colas— y requisitos de escalabilidad.
* **Gestión de proyectos**. Planes para trabajar en equipo, conjuntos de
  habilidades, capacitación, coordinación de equipos.
* **Opciones de hardware**. Procesadores, familias de procesadores, evolución de
  procesadores.
* **Flexibilidad de funcionalidad, portabilidad, calibraciones,
  configuraciones**.
* **Tecnologías con nombre, paquetes comerciales**.

Los interesados pueden no saber qué deben indicar cuáles son los requerimientos
no-funcionales o las restricciones de diseño a tener en cuenta. O pueden asumir
que esos requerimientos o restricciones son obvias y no es necesario
especificarlas. En estos casos es conveniente realizar un taller con los
interesados. Más información sobre estos talleres está disponible
[aquí](https://insights.sei.cmu.edu/library/quality-attribute-workshop-collection/).

Los objetivos del negocio también pueden ser una fuente de requerimientos
arquitectónicamente significativos; pero también pueden no serlo:

* Los objetivos de negocio a menudo derivan en requerimientos de atributos de
  calidad.
* Los objetivos de negocio pueden afectar la arquitectura sin que implique un
  requerimientos de atributo de calidad en absoluto
* No hay influencia de los objetivos del negocio en la arquitectura.

Richards y Ford proponen una relación entre objetivos del negocio y atributos de
calidad —características arquitectónicas en su terminología—[^2]:

|Preocupación del dominio|Características de la arquitectura|
|-|-|
|Fusiones y adquisiciones|Interoperabilidad, escalabilidad, adaptabilidad, extensibilidad|
|Tiempo de comercialización|Agilidad, capacidad de prueba, capacidad de implementación|
|Satisfacción del usuario|Rendimiento, disponibilidad, tolerancia a fallas, facilidad de ser probado, capacidad de implementación, agilidad, seguridad|
|Ventaja competitiva|Agilidad, facilidad de ser probado, capacidad de implementación, escalabilidad, disponibilidad, tolerancia a fallas|
|Tiempo y presupuesto|Simplicidad, viabilidad|

#### Tabla 1. Traducción de las preocupaciones del dominio a características de la arquitectura. Tomado de [^2].

[^2]: Richards, M., Ford, N. (2020). Fundamentals of Software Architecture-An
    Engineering Approach. O'Reilly.