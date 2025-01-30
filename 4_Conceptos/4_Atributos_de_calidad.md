# 4 Conceptos

## Atributos de calidad

Los atributos de calidad, también llamados características arquitectónicas o
características de calidad, son propiedades medibles o comprobables de un
sistema que se utilizan para indicar qué tan bien el sistema satisface las
necesidades de los [interesados](/4_Conceptos/4_Interesado.md) más allá de la
funcionalidad básica del sistema[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Algunos autores prefieren usar el término características arquitectónicas, en
lugar de atributos de calidad, o incluso requerimientos no-funcionales[^2]. Los
atributos de calidad en inglés se conocen tabién como *"ilities"* porque suelen
terminar con el sufijo *-ility*: *availability*, *deployability*,
*integrability*, etc.

[^2]: Richards, M., Ford, N. (2020). Fundamentals of Software Architecture-An
    Engineering Approach. O'Reilly.

Los arquitectos pueden colaborar en el análisis de requerimientos, pero tienen
la responsabilidad clave de definir, descubrir y analizar todas las cosas que el
software debe hacer que no están directamente relacionadas con el dominio del
problema y la funcionalidad del producto: los atributos de calidad.

Los atributos de calidad tienen las siguientes características[^2]:

* **Especifican una consideración de diseño que no pertenece al dominio del
  problema**. Al diseñar producto, los requerimientos especifican lo que este
  debe hacer; los atributos de calidad especifican criterios operativos y de
  diseño para el éxito, en relación con cómo implementar los requerimientos y
  por qué tomar ciertas decisiones. Por ejemplo, un atributo de calidad
  importante y muy frecuente especifica un cierto nivel de rendimiento para el
  producto, que a menudo no aparece en un documento de requerimientos. Aún más,
  probablemente ningún documento de requerimientos establezca “prevenir la deuda
  técnica”, pero es una consideración de diseño común para arquitectos y
  desarrolladores.

* **Influye en algún aspecto estructural del diseño**. La razón principal por la
  que los arquitectos intentan describir atributos de calidad en los proyectos
  se refiere a consideraciones de diseño: ¿esta característica de la
  arquitectura requiere una consideración estructural especial para tener éxito?
  Por ejemplo, la seguridad es una preocupación en prácticamente todos los
  proyectos, y todos los sistemas deben tomar ciertas precauciones básicas
  durante el diseño y la construcción. Sin embargo, se eleva al nivel de
  característica de la arquitectura cuando el arquitecto necesita diseñar algo
  especial.

* **Crítico o importante para el éxito del producto**. Los productos podrían
  admitir una gran cantidad de atributos de calidad... pero no deberían. La
  compatibilidad con cada atributo de calidad agrega complejidad al diseño. Por
  lo tanto, una tarea fundamental para los arquitectos consiste en elegir la
  menor cantidad posible de atributos de calidad en lugar de la mayor cantidad
  posible.

Existen muchas clasificaciones y definiciones de atributos de calidad; cualquier
lista será necesariamente incompleta. El estándar ISO/IEC 25010 define los
siguientes[^3]:

[^3]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering‑Systems and software Quality Requirements and Evaluation
    (SQuaRE) ‑ System and software quality models.

<table>
  <tr>
    <td>
      <a href="#adecuación-funcional">Adecuación funcional</a>
    </td>
    <td>
      <a href="#eficiencia-de-desempeño">Eficiencia de desempeño</a>
    </td>
    <td>
      <a href="#compatibilidad">Compatibilidad</a>
    </td>
    <td>
      <a href="#capacidad-de-interacción">Capacidad de interacción</a>
    </td>
    <td>
      <a href="#fiabilidad">Fiabilidad</a>
    </td>
    <td>
      <a href="#seguridad">Seguridad</a>
    </td>
    <td>
      <a href="#facilidad-de-mantenimiento">Facilidad de mantenimiento</a>
    </td>
    <td>
      <a href="#flexibilidad">Flexibilidad</a>
    </td>
    <td>
      <a href="#protección">Protección</a>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Completitud funcional<br>
      Corrección funcional<br>
      Pertinencia funcional<br>
    </td>
    <td>
      Comportamiento temporal<br>
      Utilización de recursos<br>
      Capacidad<br>
    </td>
    <td>
      Coexistencia<br>
      Interoperabilidad<br>
    </td>
    <td>
      Capacidad de reconocer la adecuación<br>
      Facilidad de aprendizaje<br>
      Facilidad de operación<br>
      Protección contra errores de usuario<br>
      Participación del usuario<br>
      Inclusión<br>
      Asistencia al usuario<br>
      Autodescripción<br>
    </td>
    <td>
      Ausencia de fallos<br>
      <a href="./4_Disponibilidad.md">Disponibilidad</a><br>
      Tolerancia a fallos<br>
      Capacidad de recuperación<br>
    </td>
    <td>
      Confidencialidad<br>
      Integridad<br>
      No repudio<br>
      Responsabilidad<br>
      Autenticidad<br>
      Resistencia<br>
    </td>
    <td>
      Modularidad<br>
      Facilidad de reúso<br>
      Facilidad de análisis<br>
      <a href="./4_Facilidad_de_modificacion.md">Facilidad de modificación</a><br>
      Capacidad para ser probado<br>
    </td>
    <td>
      Adaptabilidad<br>
      Escalabilidad<br>
      Facilidad de instalación<br>
      Facilidad de reemplazo<br>
    </td>
    <td>
      Restricción operativa<br>
      Identificación de riesgos<br>
      Protección ante fallos<br>
      Advertencia de peligro<br>
      Integración segura<br>
    </td>
  </tr>
</table>

### Adecuación funcional

Representa la capacidad del producto software para proporcionar funciones que
satisfacen las necesidades declaradas e implícitas de los usuarios cuando el
producto se usa en las condiciones especificadas. Esta característica se
subdivide a su vez en las siguientes sub-características:

#### Completitud funcional

Grado en el que el conjunto de funcionalidades del producto cubre todas las
tareas y los objetivos de usuario especificados.

#### Corrección funcional

Capacidad del producto o sistema para proveer resultados exactos cuando es usado
por los usuarios especificados

#### Pertinencia funcional

Capacidad del producto software para proporcionar un conjunto de funciones que
facilitan la consecución de tareas y objetivos de usuario especificados.

### Eficiencia de desempeño

Vean además el artículo completo sobre [rendimiento](./4_Rendimiento.md).

Esta característica representa el desempeño de un producto en la realización de
sus funciones dentro de unos parámetros de tiempo y rendimiento especificados y
con un uso eficiente de recursos de CPU, memoria, almacenamiento, energía, etc.
utilizados bajo determinadas condiciones. Esta característica se subdivide a su
vez en las siguientes sub-características:

#### Comportamiento temporal

Grado en que un producto realiza sus funciones de forma que el tiempo de
respuesta y el ratio de rendimiento cumple los requerimientos especificados.

#### Utilización de recursos

Grado en que la cantidad y tipos de recursos utilizados por el producto al
llevar a cabo su función bajo condiciones determinadas no exceden lo
especificado.

#### Capacidad

Grado en que el producto cumple los requerimientos relativos a límites máximos para
un parámetro (ítems almacenados, usuarios concurrentes, ancho de banda de
comunicaciones...).

### Compatibilidad

Capacidad de un producto de intercambiar información con otros productos y/o
llevar a cabo sus funciones requeridas cuando comparten un mismo entorno y
recursos. Esta característica se subdivide a su vez en las siguientes
sub-características:

#### Coexistencia

Capacidad del producto para coexistir con otro software independiente, en un
entorno común, compartiendo recursos comunes sin detrimento.

#### Interoperabilidad

Capacidad de dos o más sistemas o componentes para intercambiar información y
utilizar la información intercambiada.

### Capacidad de interacción

Capacidad del producto software para que el usuario interactúe mediante su
interfaz intercambiando información para completar determinadas tareas. Esta
característica se subdivide a su vez en las siguientes sub-características:

#### Capacidad de reconocimiento de la adecuación

Capacidad del producto que permite al usuario entender si el software es
adecuado para sus necesidades.

#### Facilidad de aprendizaje

Capacidad del producto que permite al usuario aprender su funcionamiento dentro
de un tiempo especificado.

#### Facilidad de operación

Capacidad del producto que permite al usuario operarlo y controlarlo con
facilidad. Protección contra errores de usuario. Capacidad del sistema para
prevenir errores en su operación.

#### Participación del usuario

Capacidad del producto de presentar sus funciones e información de forma
atractiva y motivadora, fomentando la interacción continua.

#### Inclusión

Capacidad de un producto para ser utilizado por personas con distintos contextos
(edad, habilidades, cultura, raza, lenguaje, género...).

#### Asistencia al usuario

Capacidad del producto que permite que sea utilizado por usuarios con
determinadas características y capacidades logrando objetivos específicos.

#### Autodescripción

Capacidad de un producto para presentar la información adecuada, haciendo su uso
inmediatamente evidente para el usuario sin interacciones excesivas con el
producto u otros recursos (documentación, help desks, otros usuarios...).

### Fiabilidad

Capacidad de un sistema o componente para desempeñar las funciones
especificadas, cuando se usa bajo unas condiciones y periodo de tiempo
determinados sin interrupciones o fallos. Esta característica se subdivide a su
vez en las siguientes sub-características:

#### Ausencia de fallos

Capacidad del sistema de llevar a cabo sus funciones sin fallos bajo condiciones
normales de operación.

#### Disponibilidad

Capacidad del sistema o componente de estar operativo y accesible para su uso
cuando se requiere.

#### Tolerancia a fallos

Capacidad del sistema o componente para operar según lo previsto en presencia de
fallos hardware o software.

#### Capacidad de recuperación

Capacidad del producto software para recuperar los datos directamente afectados
y restablecer el estado deseado del sistema en caso de interrupción o fallo.

### Seguridad

Vean además el artículo completo sobre [seguridad](./4_Seguridad.md).

Capacidad de protección de la información y los datos de manera que las personas
u otros productos tengan el grado de acceso a los datos adecuado a sus tipos y
niveles de autorización, y para defenderse de los patrones de ataque de agentes
malintencionados. Esta característica se subdivide a su vez en las siguientes
sub-características:

#### Confidencialidad

Capacidad de asegurar que los datos solo son accesibles a aquellos con
autorización para ello.

#### Integridad

Capacidad de un producto para garantizar que el estado de su sistema y sus datos
están protegidos frente a modificaciones o eliminaciones no autorizadas, ya sea
por acciones malintencionadas o por errores informáticos.

#### No repudio

Capacidad de demostrar las acciones o eventos que han tenido lugar, de manera
que dichas acciones o eventos no puedan ser repudiados posteriormente.

#### Responsabilidad

Capacidad de rastrear de forma inequívoca las acciones de una entidad.
Autenticidad. Capacidad de un producto para demostrar que la identidad de un
sujeto o recurso es la que se afirma.

#### Resistencia

Capacidad de mantener la operación de un producto bajo condiciones de ataque de
un actor malicioso.

### Facilidad de mantenimiento

Esta característica representa la capacidad del producto software para ser
modificado efectiva y eficientemente, debido a necesidades evolutivas,
correctivas o perfectivas. Esta característica se subdivide a su vez en las
siguientes sub-características:

#### Modularidad

Capacidad de un producto para evitar que los cambios en un componente afecten a
otros componentes.

#### Facilidad de reúso

Capacidad de un activo que permite que sea utilizado en más de un sistema
software o en la construcción de otros activos.

#### Facilidad de análisis

Facilidad con la que se puede evaluar el impacto de un determinado cambio sobre
el resto del software, diagnosticar las deficiencias o causas de fallos en el
software, o identificar las partes a modificar.

#### Facilidad de modificación

Capacidad del producto que permite que sea modificado de forma efectiva y
eficiente sin introducir defectos o degradar su calidad.

#### Facilidad de ser probado

Facilidad con la que se pueden establecer criterios de prueba para un sistema o
componente y con la que se pueden llevar a cabo las pruebas para determinar si
se cumplen dichos criterios.

### Flexibilidad

Capacidad del producto para adaptarse a cambios en sus requerimientos, contextos
de uso o entorno del sistema. Esta característica se subdivide a su vez en las
siguientes sub-características:

#### Adaptabilidad

Capacidad del producto que le permite ser adaptado de forma efectiva y eficiente
a diferentes entornos determinados de hardware, software, operacionales o de
uso.

#### Escalabilidad

Capacidad del producto para gestionar cargas de trabajo crecientes o
decrecientes y para adaptar su capacidad a la variabilidad.

#### Facilidad de instalación

Facilidad con la que el producto se puede instalar o desinstalar de forma
exitosa en un determinado entorno.

Vean también [facilidad de despliegue](./4_Facilidad_de_despliegue.md).

#### Facilidad de reemplazo

Capacidad del producto para ser utilizado en lugar de otro producto software
determinado con el mismo propósito y en el mismo entorno.

### Protección

Vean además el artículo completo sobre [protección](./4_Proteccion.md).

Esta característica representa la capacidad del producto, en condiciones
definidas, de evitar un estado en el que se ponga en peligro la vida humana, la
salud, la propiedad o el medio ambiente. Esta característica se subdivide a su
vez en las siguientes sub-características:

#### Restricción operativa

Capacidad de un producto para limitar su funcionamiento a unos parámetros o
estados seguros cuando se enfrenta a un peligro operativo

#### Identificación de riesgos

Capacidad de un producto para identificar situaciones u operaciones que pueden
exponer la vida, la propiedad o el medio ambiente a un riesgo inaceptable.

#### Protección ante fallos

Capacidad de un producto para ponerse automáticamente en un modo de
funcionamiento seguro o para volver a una condición segura en caso de fallo.

#### Advertencia de peligro

Capacidad de un producto para alertar de riesgos inaceptables, de modo que
puedan reaccionar con tiempo suficiente para mantener la seguridad de las
operaciones.

#### Integración segura

Capacidad de un producto para mantener la seguridad durante y después de la
integración con uno o varios componentes.

Nos enfocaremos en los siguientes:

* [Disponibilidad](./4_Disponibilidad.md)
* [Performance](./4_Rendimiento.md)
