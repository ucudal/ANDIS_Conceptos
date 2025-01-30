# 4 Conceptos

## Requerimiento arquitectónicamente significativo

Un requerimiento arquitectónicamente significativo —o ASR, *architecturally
significant requirement* por sus siglas en inglés— es un requerimiento que
tendrá un efecto profundo en la arquitectura, es decir, la arquitectura podría
ser radicalmente diferente si no existiera ese requerimiento[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
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
  blandos —por ejemplo, buffers, colas— y requerimientos de escalabilidad.
* **Gestión de proyectos**. Planes para trabajar en equipo, conjuntos de
  habilidades, capacitación, coordinación de equipos.
* **Opciones de hardware**. Procesadores, familias de procesadores, evolución de
  procesadores.
* **Flexibilidad de funcionalidad, portabilidad, calibraciones,
  configuraciones**.
* **Tecnologías con nombre, paquetes comerciales**.

Los [interesados](/4_Conceptos/4_Interesado.md) pueden no saber qué deben
indicar cuáles son los requerimientos no-funcionales o las restricciones de
diseño a tener en cuenta. O pueden asumir que esos requerimientos o
restricciones son obvias y no es necesario especificarlas. En estos casos es
conveniente realizar un taller con los interesados. Más información sobre estos
talleres está disponible
[aquí](https://insights.sei.cmu.edu/library/quality-attribute-workshop-collection/).

A continuación aparece una guía pra identificar algunos requerimientos
arquitectónicamente significativos implícitos en los proyectos:

<table>
  <tr>
    <th>Aspecto</th>
    <th>Descripción</th>
    <th>Posibles atributos de calidad</th>
  </tr>
  <tr>
    <td>
      Funciones con alto retorno para el negocio
    </td>
    <td>
      Son procesos que directamente generan un valor considerable para la
      organización, contribuyendo de manera sustancial a los objetivos
      estratégicos
    </td>
    <td>
      Eficiencia de rendimiento, Fiabilidad
    </td>
  </tr>
  <tr>
    <td>
      Operaciones críticas de negocio
    </td>
    <td>
      Refiere a aquellas funciones cuya interrupción podría afectar gravemente
      las operaciones diarias y la continuidad del negocio
    </td>
    <td>
      Fiabilidad
    </td>
  </tr>
  <tr>
    <td>
      Funcionalidades esenciales del sistema
    </td>
    <td>
      Son características fundamentales sin las cuales el sistema no podría
      cumplir su propósito principal
    </td>
    <td>
      Fiabilidad
    </td>
  </tr>
  <tr>
    <td>
      Usuarios influyentes
    </td>
    <td>
      Involucra a aquellos usuarios cuya satisfacción o insatisfacción tiene un
      impacto significativo en la percepción y adopción del sistema. Estos
      usuarios pueden ser líderes de opinión dentro de la organización o
      clientes clave
    </td>
    <td>
      Adecuación funcional, capacidad de interacción
    </td>
  </tr>
  <tr>
    <td>
      Usuarios móviles
    </td>
    <td>
      Considera a los usuarios que acceden al sistema desde diferentes
      ubicaciones o dispositivos móviles, lo que podría requerir soporte
      adicional en términos de conectividad y experiencia de usuario
    </td>
    <td>
      Capacidad de interacción
    </td>
  </tr>
  <tr>
    <td>
      Cobertura amplia y uso de múltiples componentes arquitectónicos
    </td>
    <td>
      Los procesos que interactúan con varios subsistemas o componentes de la
      arquitectura son críticos porque su correcto funcionamiento depende de la
      integración y comunicación efectiva entre diferentes partes del sistema
    </td>
    <td>
      Compatibilidad
    </td>
  </tr>
  <tr>
    <td>
      Requerimientos de seguridad
    </td>
    <td>
      Procesos que manejan información sensible o deben cumplir con normativas
      de seguridad específicas son vitales para la protección de datos y la
      conformidad con las regulaciones
    </td>
    <td>
      Seguridad, protección
    </td>
  </tr>
  <tr>
    <td>
      Complejidad de las reglas de negocio
    </td>
    <td>
      Los procesos que incluyen reglas de negocio complejas o condiciones que
      deben cumplirse de manera precisa representan un desafío significativo en
      el diseño y la implementación
    </td>
    <td>
      Adecuación funcional, facilidad de mantenimiento
    </td>
  </tr>
  <tr>
    <td>
      Exigencias altas en términos de desempeño y disponibilidad
    </td>
    <td>
      Procesos que deben funcionar bajo cargas pesadas o requieren una alta
      disponibilidad para no interrumpir las operaciones son cruciales para la
      arquitectura
    </td>
    <td>
      Fiabilidad, eficiencia de desempeño
    </td>
  </tr>
  <tr>
    <td>
      Alto potencial de cambio
    </td>
    <td>
      Aquellos procesos que están sujetos a cambios frecuentes o requieren una
      adaptación continua deben ser diseñados con flexibilidad para evitar que
      el sistema quede obsoleto rápidamente.
    </td>
    <td>
      Facilidad de mantenimiento, flexibilidad
    </td>
  </tr>
  <tr>
    <td>
      Sincronización y comunicación con sistemas externos
    </td>
    <td>
      Procesos que dependen de la integración con otros sistemas, ya sean
      internos o externos, presentan desafíos adicionales en términos de
      compatibilidad y sincronización
    </td>
    <td>
      Compatibilidad, protección
    </td>
  </tr>
  <tr>
    <td>
      Riesgos o problemas identificados
    </td>
    <td>
      Identificar procesos que podrían representar riesgos potenciales o que ya
      han mostrado problemas en implementaciones anteriores es fundamental para
      diseñar medidas preventivas
    </td>
    <td>
      Protección
    </td>
  </tr>
</table>

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

#### *Tabla 1. Traducción de las preocupaciones del dominio a características de la arquitectura. Tomado de [^2].*

Por último, los requerimientos arquitectónicamente significativos no son todos:

> [!TIP]
> Usar la **regla del 80/20** Se trata de aplicar el principio de Pareto,
> identificando el 20% de los requerimientos que cubren el 80% de la actividad
> de los usuarios, permitiendo un enfoque estratégico en los elementos de mayor
> impacto.

[^2]: Richards, M., Ford, N. (2020). Fundamentals of Software Architecture-An
    Engineering Approach. O'Reilly.
