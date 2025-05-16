# 4 Conceptos

## Computación distribuida

Este documento está basado en [^1].

<!-- cSpell:ignore Tannenbaum -->

[^1]: van Steen, M., Tannenbaum, A. (2025). Distributed Systems: Principles and
    Paradigms, 4<sup>th</sup> edition. Maarten van Steen. Disponible
    [aquí](https://www.distributed-systems.net/index.php/books/ds4/).

### Un poco de historia

El avance de los sistemas de computación ha sido vertiginoso. Entre 1945 y 1985,
computadoras grandes y costosas funcionaban de forma aislada al no poder
conectarse entre sí.

<!-- cSpell:ignore Iain,Callum -->
<span id="figura-1"/> <a title="Iain MacCallum, CC BY 3.0
&lt;https://creativecommons.org/licenses/by/3.0&gt;, via Wikimedia Commons"
href="https://commons.wikimedia.org/wiki/File:University_of_Manchester_Atlas,_January_1963.JPG"><img
width="512" alt="University of Manchester Atlas, January 1963"
src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/University_of_Manchester_Atlas%2C_January_1963.JPG/512px-University_of_Manchester_Atlas%2C_January_1963.JPG?20201105033817"></a>

*Figura 1. University of Manchester Atlas, January 1963. © Iain MacCallum, [CC
BY 3.0](https://creativecommons.org/licenses/by/3.0), via [Wikimedia
Commons](https://commons.wikimedia.org/).*

A mediados de los '80, dos avances transformaron esta realidad:

* **Desarrollo de procesadores potentes**: Evolucionaron rápidamente de 8
  bits a procesadores de 64 bits *multi-core*. Las máquinas actuales tienen la
  potencia de los antiguos mainframes pero cuestan mil veces menos.

* **Creación de redes de alta velocidad**: Las redes locales
  —[LAN](https://www.cisco.com/c/en/us/products/switches/what-is-a-lan-local-area-network.html)—
  conectan miles de computadoras en un mismo espacio, permitiendo velocidades de
  entre uno y cientos de gigabits por segundo. Las redes globales
  —[WAN](https://www.cisco.com/c/en/us/products/switches/what-is-a-wan-wide-area-network.html)—
  vinculan cientos de millones de máquinas en todo el mundo a velocidades de
  entre un megabit por segundo y decenas o cientos de gigabits por segundo.

Estos avances revolucionaron la forma en que las computadoras operan, pasando de
máquinas aisladas a sistemas interconectados globalmente.

Mientras se desarrollaban equipos más potentes y conectados, ocurría
simultáneamente una impresionante miniaturización. Los smartphones representan
el mayor logro: dispositivos con múltiples sensores, mucha memoria y potentes
procesadores *multi-core* que funcionan como computadoras completas con
capacidades de red.

<!-- cSpell:ignore Cloudwatt,Datacenter -->
<span id="figura-2"/>
<a title="Cloudwatt, CC BY-SA 3.0
&lt;https://creativecommons.org/licenses/by-sa/3.0&gt;, via Wikimedia Commons"
href="https://commons.wikimedia.org/wiki/File:Datacenter_Cloudwatt.jpg"><img
width="512" alt="Datacenter Cloudwatt"
src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Datacenter_Cloudwatt.jpg/512px-Datacenter_Cloudwatt.jpg?20131212112639"></a>

<!-- cSpell:ignore Normandía, Reuil -->
*Figura 2. Centro de datos Normandía de Cloudwatt en Val-de-Reuil (Eure). ©
Cloudwatt, [CC BY-SA
3.0](https://creativecommons.org/licenses/by-sa/3.0/deed.en), via [Wikimedia
Commons](https://commons.wikimedia.org/).*

Paralelamente surgieron las nano computadoras: sistemas de placa única del
tamaño de una tarjeta de crédito, como [Raspberry
Pi](https://www.raspberrypi.com) y [Arduino](https://www.arduino.cc), que
ofrecen rendimiento comparable al de una computadora de escritorio en un formato
extremadamente reducido.

### Sistemas descentralizados y distribuidos

Existen dos perspectivas sobre cómo las computadoras llegan a conectarse en red:

* **Visión integradora**: Surge de la necesidad de conectar sistemas de
   computación existentes para que sus servicios estén disponibles a nuevos
   usuarios y aplicaciones —por ejemplo, la integración de servicios dentro de
   organizaciones o la conexión de recursos científicos costosos en computadoras
   en [*grid*](https://aws.amazon.com/what-is/grid-computing)—.

* **Visión expansiva**: Ocurre cuando un sistema existente necesita ampliarse
  con computadoras adicionales, ya sea para acercar recursos a donde se
  necesitan o para mejorar la confiabilidad mediante redundancia, incluye la
  creación de aplicaciones web o móviles para acceso remoto.

La distinción entre ambas visiones no siempre es clara, pero llevan a dos tipos
de sistemas:

* **Un sistema descentralizado** es un sistema informático en red en el cual los
  procesos y recursos están **necesariamente** distribuidos en múltiples
  computadoras —por ejemplo,
  [blockchain](https://aws.amazon.com/what-is/blockchain)—.

<!-- cSpell:ignore Gmail -->
* **Un sistema distribuido** es un sistema informático en red en el cual los
  procesos y recursos están **suficientemente** distribuidos en múltiples
  computadoras —por ejemplo, un servicio de correo electrónico como Gmail o un
  [CDN](https://aws.amazon.com/what-is/cdn/)—.

Tanto los sistemas descentralizados como los distribuidos son inherentemente
complejos y sufren de las [falacias de la computación
distribuida](./4_Falacias_computacion_distribuida.md) La distinción se hace
porque muchas veces se distribuyen procesos y recursos no porque se necesite —no
es descentralizado— sino porque se decide que lo estén —que sea distribuido—.
Esa decisión debe ser considerada cuidadosamente.

### Perspectivas de los sistemas distribuidos

Los sistemas distribuidos pueden organizarse de muchas formas. Existen varias
perspectivas fundamentales para comprender su funcionamiento:

* **Perspectiva arquitectónica**: Aborda los [estilos comunes de
  arquitectura](/2_Tecnicas_y_herramientas/2_07_.Estilos_arquitectura/2_07_.Estilos_arquitectura.md),
  ayudando a entender cómo interactúan y dependen entre sí los diversos
  [componentes](/4_Conceptos/4_Componente.md).

* **Perspectiva de procesos**: Considera las diferentes formas de proceso que
   ocurren en los sistemas distribuidos: hilos, virtualización, clientes,
   servidores. Los procesos constituyen la columna vertebral de estos sistemas.

* **Perspectiva de comunicación**: Aborda las capacidades de los sistemas
  distribuidos para intercambiar datos entre procesos, incluyendo [llamadas a
  procedimientos
  remotos](/2_Tecnicas_y_herramientas/2_13_.Integracion_aplicaciones/2_13_3_RPC.md),
  [intercambio de mensajes de alto
  nivel](/2_Tecnicas_y_herramientas/2_13_.Integracion_aplicaciones/2_13_4_Messaging.md)
  y comunicación entre conjuntos de procesos.

* **Perspectiva de coordinación**: Considera tareas fundamentales de
  coordinación necesarias en la mayoría de sistemas distribuidos, como compensar
  la falta de un reloj global o realizar acceso exclusivo a recursos
  compartidos.

* **Perspectiva de nomenclatura**: Aborda los esquemas de nombres que
  conducen a procesos, recursos u otras entidades. Aunque parece simple, la
  nomenclatura es crucial y existen muchas formas de implementarla.

* **Perspectiva de consistencia y replicación**: Considera los compromisos entre
  consistencia, replicación y rendimiento. La replicación mejora la eficiencia y
  confiabilidad, pero mantener la consistencia durante las actualizaciones es un
  desafío. Vean el [teorema de Brewer](/4_Conceptos/4_Teorema_Brewer.md).

* **Perspectiva de tolerancia a fallos**: Considera los medios para enmascarar
  fallos y su recuperación, un aspecto complejo debido a los numerosos
  compromisos necesarios y a la imposibilidad de enmascarar completamente todos
  los fallos.

* **Perspectiva de seguridad**: Incluye las garantías para el acceso autorizado
  a los recursos, abordando la confianza en sistemas distribuidos y la
  autenticación. Aunque aparece al final, proporciona instrumentos básicos
  necesarios para entender su papel en las perspectivas anteriores.

### Objetivos de diseño de los sistemas distribuidos

Aunque es posible construir sistemas distribuidos, no necesariamente es una
buena idea: hay cuatro objetivos que se deben cumplir para que el esfuerzo valga
la pena:

A
distributed system should make resources easily accessible; it should hide the
fact that resources are distributed across a network; it should be open; and it
should be scalable.

* **Compartir recursos**. Un objetivo de los sistemas distribuidos debe ser
  permitir acceder y compartir recursos remotos a aplicaciones y usuarios de
  forma fácil. Existen muchas razones para querer compartir recursos. Una
  evidente es la económica: el costo de un recurso compartido es menor que si
  fueran múltiples recursos individuales. Otra razón es que conectar usuarios y
  recursos también facilita la colaboración y el intercambio de información.

* **Transparencia de la distribución**. Otro objetivo debe ser ocultar —hacer
  transparente— el hecho de que los procesos y recursos están físicamente
  distribuidos entre múltiples computadoras conectadas a través de una red y
  posiblemente separadas por grandes distancias. Existen diferentes formas de
  transparencia:

  * **Acceso**. Oculta las diferencias en la representación de los datos y en
    cómo se accede a un objeto[^2].

  * **Ubicación**. Oculta dónde se encuentra un objeto.

  * **Re-ubicación**. Oculta que un objeto puede ser movido a otra ubicación
    mientras está en uso.

  * **Migración**. Oculta que un objeto puede moverse a otra ubicación.

  * **Replicación**. Oculta que un objeto está replicado.

  * **Concurrencia**. Oculta que un objeto puede ser compartido por varios
    clientes[^3] independientes.

  * **Fallo**. Oculta el fallo y la recuperación de un objeto.

  Aunque generalmente se considera preferible la transparencia en la
  distribución para cualquier sistema distribuido, hay situaciones en las que
  intentar ocultar todos los aspectos de la distribución a los clientes sin
  cuestionarlo no es una buena idea o directamente debe ser evitado —considera
  por ejemplo las consecuencias derivadas de la latencia de la red o de mantener
  réplicas consistentes—.

[^2]: En este contexto un objeto es un proceso o un recurso.

[^3]: En este contexto los clientes pueden ser usuarios, componentes o
    aplicaciones.

* **Apertura**. Otro objetivo de los sistemas distribuidos es que sean abiertos.
  Esencialmente un sistema distribuido abierto es el que ofrece componentes que
  pueden ser fácilmente utilizados o integrados en otros sistemas. A su vez, un
  sistema distribuido abierto suele estar compuesto por componentes que
  provienen de otros lados.

  Ser abierto significa que los componentes deben adherir a reglas estándar que
  describan la sintaxis y la semántica de lo que esos componentes ofrecen —qué
  servicios proporcionan—. Lo difícil es especificar con precisión qué hacen
  esos servicios —la semántica de las interfaces—.

  La **interoperatividad** caracteriza el grado en que dos implementaciones de
  sistemas o componentes de distintos proveedores pueden coexistir y trabajar
  juntos, confiando únicamente en los servicios de cada uno según lo
  especificado por un estándar común.

  La **portabilidad** caracteriza hasta qué punto una aplicación desarrollada
  para un sistema distribuido A puede ejecutarse, sin modificaciones, en un
  sistema distribuido B que implemente las mismas interfaces que A.

  Otro objetivo importante de un sistema distribuido abierto es que debe ser
  fácil configurar el sistema a partir de diferentes componentes —posiblemente
  de distintos proveedores—. Además, debe ser sencillo agregar nuevos
  componentes o reemplazar los existentes sin afectar a aquellos que permanecen.
  En otras palabras, un sistema distribuido abierto también debe ser
  **extensible**.

  Para lograr flexibilidad en sistemas distribuidos abiertos, es esencial
  organizarlos en componentes pequeños y reemplazables, definiendo tanto
  interfaces de alto nivel como internas. Este enfoque contrasta con los
  sistemas monolíticos tradicionales, donde modificar un componente afecta a
  todo el sistema, con lo que el sistema resultante tiende a ser cerrado y no
  abierto. Lo que se necesita es separar la **política** —o *policy*— del
  **mecanismo** —o *mechanism*—. El componente provee un mecanismo para una
  política definida por el compuesto.

* **Confiabilidad** o -*dependability*-. Como su nombre lo indica, la
  confiabilidad se refiere al grado en que se puede confiar en que un sistema
  informático funcionará según lo previsto. La confiabilidad en sistemas
  distribuidos es compleja debido a los fallos parciales: componentes que fallan
  mientras el sistema sigue funcionando parcialmente. A diferencia de los
  sistemas de un solo computador, las redes de computadoras complican la
  situación, debiendo asumirse que siempre ocurren fallos parciales. Un objetivo
  clave de los sistemas distribuidos es enmascarar estos fallos y su
  recuperación, lo que constituye la **tolerancia a fallos**.

  Vean también [disponibilidad](/4_Conceptos/4_Disponibilidad.md),
  [seguridad](/4_Conceptos/4_Seguridad.md), facilidad de
  [modificación](/4_Conceptos/4_Facilidad_de_modificacion.md) y
  [despliegue](/4_Conceptos/4_Facilidad_de_despliegue.md) y
  [error](/4_Conceptos/4_Error.md).

* **Escalabilidad**. Otro objetivo es que sean escalables. La escalabilidad
  tiene al menos tres dimensiones diferentes:

  * Escalabilidad de tamaño: Un sistema puede ser escalable en función de su
    tamaño, lo que significa que podemos añadir fácilmente más usuarios y
    recursos sin ninguna pérdida apreciable de rendimiento.

  * Escalabilidad geográfica: Un sistema geográficamente escalable es aquel en
    el que los usuarios y los recursos pueden estar muy separados, pero los
    retrasos significativos en la comunicación pasan prácticamente
    desapercibidos.

  * Escalabilidad administrativa: Un sistema administrativamente escalable es
    aquel que puede gestionarse fácilmente incluso si abarca muchas
    organizaciones administrativas independientes.

> [!TIP]
> Para conocer más información acerca de estos temas, consulta la sección **1.2
> Design Goals**, del capítulo **1 Introduction**, de [^1].
