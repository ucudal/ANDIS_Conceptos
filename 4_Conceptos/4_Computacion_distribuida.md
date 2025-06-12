# 4 Conceptos

## Computación distribuida

Este documento está basado en [^1] y [^2].

<!-- cSpell:ignore Tannenbaum -->

[^1]: van Steen, M., Tannenbaum, A. (2025). Distributed Systems: Principles and
    Paradigms, 4<sup>th</sup> edition. Maarten van Steen. Disponible
    [aquí](https://www.distributed-systems.net/index.php/books/ds4/).

[^2]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

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

El enorme desarrollo y aceptación de la [computación en la
nube](./4_Computacion_nube.md) de los últimos años hace relevante la comprensión
de diversos aspectos de los sistemas distribuidos, pues esencialmente un sistema
de computación en la nube es necesariamente un sistema distribuido.

### Sistemas descentralizados y distribuidos

Existen dos perspectivas sobre cómo las computadoras llegan a conectarse en red:

* **Visión integradora**: Surge de la necesidad de conectar sistemas de
   computación existentes para que sus servicios estén disponibles a nuevos
   usuarios y aplicaciones —por ejemplo, la integración de servicios dentro de
   organizaciones o la conexión de recursos científicos costosos en computadoras
   en [*grid*](https://aws.amazon.com/what-is/grid-computing)—.

* **Visión expansiva**: Ocurre cuando un sistema existente necesita ampliarse
  con computadoras adicionales, ya sea para acercar servicios a donde se
  necesitan o para mejorar la confiabilidad mediante redundancia; incluye la
  creación de aplicaciones web o móviles para acceso remoto.

La distinción entre ambas visiones no siempre es clara, pero llevan a dos tipos
de sistemas:

* **Un sistema descentralizado** es un sistema informático en red en el cual los
  servicios[^3] están **necesariamente** distribuidos en múltiples computadoras
  —por ejemplo, [blockchain](https://aws.amazon.com/what-is/blockchain)—.

<!-- cSpell:ignore Gmail -->
* **Un sistema distribuido** es un sistema informático en red en el cual los
  servicios están **suficientemente** distribuidos en múltiples computadoras
  —por ejemplo, un servicio de correo electrónico como Gmail o un
  [CDN](https://aws.amazon.com/what-is/cdn/)—.

[^3]: Usamos en el término «servicio» aunque en [^1] se utiliza «recurso»; el
    primero incluye de alguna forma al segundo, pues para acceder a un recurso
    —como un archivo— se utiliza un servicio —como un servicio de archivos—.

Tanto los sistemas descentralizados como los distribuidos son inherentemente
complejos y sufren de las [falacias de la computación
distribuida](./4_Falacias_computacion_distribuida.md) La distinción se hace
porque muchas veces se distribuyen servicios no porque se necesite —no es
descentralizado— sino porque se decide que lo estén —que sea distribuido—. Esa
es una decisión arquitectónica que se debe tomar con cuidado.

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
  remotos](/4_Conceptos/4_RPC.md),
  [intercambio de mensajes de alto
  nivel](/2_Tecnicas_y_herramientas/2_13_.Integracion_aplicaciones/2_13_4_Messaging.md)
  y comunicación entre conjuntos de procesos.

* **Perspectiva de coordinación**: Considera tareas fundamentales de
  coordinación necesarias en la mayoría de sistemas distribuidos, como compensar
  la falta de un reloj global o realizar acceso exclusivo a recursos
  compartidos.

* **Perspectiva de nomenclatura**: Aborda los esquemas de nombres con los que se
  accede a servicios. Aunque parece simple, la nomenclatura es decisiva y
  existen muchas formas de implementarla.

* **Perspectiva de consistencia y replicación**: Considera los compromisos entre
  consistencia, replicación y rendimiento. La replicación mejora la eficiencia y
  confiabilidad, pero mantener la consistencia durante las actualizaciones es un
  desafío. Vean el [teorema de Brewer](/4_Conceptos/4_Teorema_Brewer.md).

* **Perspectiva de tolerancia a fallos**: Considera los medios para enmascarar
  fallos y su recuperación, un aspecto complejo debido a los numerosos
  compromisos necesarios y a la imposibilidad de enmascarar completamente todos
  los fallos.

* **Perspectiva de seguridad**: Incluye las garantías para el acceso autorizado
  a los servicios, abordando la confianza y la autenticación en los sistemas
  distribuidos . Aunque aparece al final, proporciona instrumentos básicos
  necesarios para entender su papel en las perspectivas anteriores.

### Objetivos de diseño de los sistemas distribuidos

Aunque es posible construir un sistema que sea distribuido, no necesariamente es
una buena idea: hay cuatro objetivos que se deben cumplir para que el esfuerzo
valga la pena:

* **Compartir servicios**. Un objetivo de los sistemas distribuidos debe ser
  permitir acceder y compartir servicios remotos a aplicaciones y usuarios de
  forma fácil. Existen muchas razones para esto: una evidente es la económica
  —el costo de un servicio compartido es menor que si fueran múltiples servicios
  individuales—. Otra razón es que conectar usuarios y servicios también
  facilita la colaboración y el intercambio de información.

* **Transparencia de la distribución**. Otro objetivo debe ser ocultar —hacer
  transparente— el hecho de que los servicios están físicamente distribuidos
  entre múltiples computadoras conectadas a través de una red y posiblemente
  separadas por grandes distancias. Existen diferentes formas de transparencia:

  * **Acceso**. Oculta las diferencias en la representación de los datos y en
    cómo se accede a un servicio.

  * **Ubicación**. Oculta dónde se encuentra un servicio.

  * **Re-ubicación**. Oculta que un servicio puede ser movido a otra ubicación
    mientras está en uso.

  * **Migración**. Oculta que un servicio puede moverse a otra ubicación.

  * **Replicación**. Oculta que un servicio está replicado.

  * **Concurrencia**. Oculta que un servicio puede ser compartido por varios
    clientes[^4] independientes.

  * **Fallo**. Oculta el fallo y la recuperación de un servicio.

  Aunque generalmente se considera preferible la transparencia en la
  distribución para cualquier sistema distribuido, hay situaciones en las que
  intentar ocultar todos los aspectos de la distribución a los clientes sin
  cuestionarlo no es una buena idea o directamente debe ser evitado —considera
  por ejemplo las consecuencias derivadas de la latencia de la red o de mantener
  réplicas consistentes—.

[^4]: En este contexto los clientes pueden ser usuarios, componentes o
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

### Múltiples instancias para escalabilidad y disponibilidad

<!-- cSpell:ignore indisponible https://dle.rae.es/indisponible -->

Cuando un servicio recibe más solicitudes de las que puede procesar con cierta
latencia queda indisponible —la latencia es el tiempo que transcurre entre que
se envía una solicitud hasta que se comienza a recibir la respuesta a o el
resultado de esa solicitud— . Esto puede ocurrir porque el servicio tiene
asignados recursos insuficientes.

En algunos casos esto se puede resolver moviendo el servicio a un servidor o
creando una instancia del servicio que tenga más recursos. Esto es conocido como
«escalado vertical» o «*scale up*» y corresponde con la táctica de desempeño de
[aumentar los
recursos](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_02_Tacticas_rendimiento.md#aumentar-los-recursos).
Hay límites en el escalado vertical, porque los recursos son finitos —o aunque
no se haya llegado al límite, son muy costosos—.

En otros casos se puede resolver la situación agregando más servidores o más
instancias del servicio iguales. Esto otro es conocido como «escalado
horizontal» o «*scale out*» y corresponde con la táctica de desempeño de
[mantener múltiples copias del
cómputo](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_02_Tacticas_rendimiento.md#mantener-múltiples-copias-del-cómputo).
El escalado horizontal involucra tener múltiples copias —instancias— del mismo
servicio utilizando un balanceador de carga para distribuir las solicitudes
entre ellas.

### Balanceo de carga

Los balanceadores de carga —o NLB por *network load balancer*— son un
[componente](/4_Conceptos/4_Componente.md) que se sitúa en el camino de cada
solicitud entre un cliente y un servicio.
[Aquí](https://learn.microsoft.com/en-us/azure/load-balancer/load-balancer-overview)
y
[aquí](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)
puedes ver ejemplos de balanceadores de carga en la nube.

Cuando hay varias instancias iguales de un servicio detrás de un balanceador de
cargo, éste resuelve el problema de distribuir las solicitudes que llegan entre
ellas —algo análogo ocurre cuando el balanceador de carga distribuye las
solicitudes entre múltiples servidores iguales—. El balanceador de carga recibe
una solicitud de un cliente —el cliente cree que está enviando la solicitud al
servicio— y la envía a la primera instancia del servicio; cuando recibe otra
solicitud la envía a la segunda instancia; y así sucesivamente. De aquí el
nombre de balanceador de carga, porque logra que la carga de solicitudes se
distribuya entre todas las instancias.

El mecanismo de balanceo descrito es conocido como *round-robin*. Este algoritmo
no tiene en cuenta qué tan cargadas están las instancias, pero hay otros
algoritmos que sí.

Tengan en cuenta que el cliente no conoce la dirección de las instancias, sólo
la dirección del balanceador de carga. Tampoco sabe cuántas instancias hay
detrás del balanceador de carga, ni qué instancia está respondiendo a la
solicitud, lo que permite agregar, quitar, o reemplazar instancias según sea
necesario, sin que el cliente se entere. Esto corresponde con la táctica de
facilidad de modificación de [usar un
intermediario](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_05_Tacticas_facilidad_de_modificacion.md#usar-un-intermediario).

La respuesta a la solicitud puede ir directamente al cliente —la solicitud HTTP
que llega a la instancia incluye la dirección del cliente— o puede pasar por el
balanceador de carga. En el primer caso, el balanceador de carga no tiene cómo
saber si la solicitud fue procesada —es decir, si la instancia está
"saludable"—, ni cuál fue la latencia de esa solicitud —es decir, si la
instancia está "sobrecargada"—. Para obtener esta información, el balanceador de
carga puede implementar alguna las [tácticas de
disponibilidad](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_01_Tacticas_disponibilidad.md)
para detectar fallas como
[monitoreo](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_01_Tacticas_disponibilidad.md#monitoreo),
[ping-echo](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_01_Tacticas_disponibilidad.md#pingecho),
etc.

<!-- cSpell:ignore indisponibilidad https://dle.rae.es/indisponibilidad-->
<!-- cSpell:ignore indisponibles https://dle.rae.es/indisponible-->

La indisponibilidad de una instancia puede ser temporal, por lo cual el
balanceador de carga debe chequear su estado de salud —determinar si esá
"saludable"— periódicamente.

Cuando una instancia o el servidor quedan indisponibles por una falla
permanente, puede ser necesario reiniciarlos, o incluso puede ser necesario
agregar un nuevo servidor. Cuando eso ocurre es necesario registrar nuevamente
el servicio con el balanceador de carga.

Aún con un balanceador de carga que implementa el chequeo de salud, es posible
que un cliente no obtenga la respuesta a una solicitud. Los clientes deben ser
diseñados para volver a enviar las solicitudes de las que no obtienen
respuestas, implementando por ejemplo patrones como [Circuit
Breaker](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura.md/2_09_Circuit_breaker.md)
o
[Retry](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura.md/2_09_Retry.md).

### Manejo del estado

El «estado» se refiere a la información interna de un servicio que afecta la
forma como calcula la respuesta a un cliente —esencialmente es el conjunto de
valores de sus variables y estructuras de datos—. El estado en un momento dado
depende las solicitudes que el servicio ha recibido hasta ese momento.

El manejo del estado es importante cuando el servicio está implementado en una
aplicación que es capaz de procesar varias solicitudes en paralelo —multi-hilos
o *multithreading*— o cuando hay varias instancias del servicio detrás de un
balanceador de carga.

Hay tres opciones para manejar el estado:

* La historia de las solicitudes se guarda en cada instancia, en cuyo caso el
  servicio se describe como *stateful* o «con estado».

* La historia se mantiene en cada cliente, en cuyo caso se describe el servicio
  como *stateless* o «sin estado».

* La historia se guarda fuera del servicio y del cliente, en una base de datos,
  en cuyo el servicio se describe también como *stateless* o «sin estado».

La práctica más común es —o el objetivo de diseño debería ser— diseñar servicios
sin estado. Los servicios con estado tienen el problema que pierden la historia
cuando es necesario reiniciarlos.

> [!TIP]
> Puedes ver [este
> artículo](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/app-state?view=aspnetcore-9.0)
> para conocer más detalles sobre cómo implementar el manejo de estado en ASP
> .NET Core y [este
> otro](https://www.digitalocean.com/community/tutorials/java-session-management-servlet-httpsession-url-rewriting)
> para Java Server Pages.

Hay veces en las que es difícil o es ineficiente diseñar un servicio sin estado.
En esos casos, cuando llega la primera solicitud de un nuevo cliente, el
balanceador de carga puede permitir establecer una sesión directamente entre el
cliente y la instancia que responde a esa primera solicitud —*direct sessions*—,
para que las siguientes solicitudes de ese mismo cliente vayan directamente a
esa instancia. También es posible que el balanceador de carga asigne siempre la
misma instancia a las solicitudes del mismo cliente —*sticky sessions*—.
Obviamente que en ese caso no se obtendrán todas las ventajas de escalabilidad y
disponibilidad que se consiguen con el balanceo de carga.

### Coordinación de la hora

Determinar exactamente qué hora es puede parecer trivial pero no es nada fácil.
Los relojes de las computadoras atrasan o adelantan más o menos un segundo cada
12 días. Por lo tanto dos instancias del mismo servicio en dos servidores
diferentes pueden no tener la misma hora. En caso de que el servicio deba usar
*timestamps* —por ejemplo— que no tengan la misma hora es un problema.

<!-- cSpell:ignore milisegundo https://dle.rae.es/milisegundo -->

Existe un protocolo para sincronizar los relojes de diferentes computadoras:
[NTP](https://www.rfc-editor.org/rfc/rfc5905) o *Network Time Protocol*. La
exactitud que se logra con NTP en una red de área local es del orden del
milisegundo; en una red pública es del orden de 10 milisegundos. Cuando un
servicio recibe miles de solicitudes por segundo, los milisegundos pasan a ser
relevantes.

Los centros de cómputo de los proveedores de [nube
pública](./4_Computacion_nube.md#modelos-de-despliegue) tienen relojes muy
exactos: usan un reloj atómico que atrasa o adelanta un segundo en 300 años; o
toman la hora del GPS que es exacta en más o menos 100 nanosegundos—.

Otro protocolo usado dentro de los centros de cómputo de los proveedores de nube
pública para sincronizar los relojes es
[PTP](https://standards.ieee.org/ieee/1588/4355/) o *Precision Time Protocol*.
En este caso la hora es exacta en al menos el orden de microsegundos.

Para la mayoría de las aplicaciones, una hora exacta al nivel de NTP es
suficiente. En otros casos, la hora exacta en la que ocurre un evento no es tan
importante como el orden en el que ocurren los eventos.

### Coordinación de los datos

Una condición de carrera o *race condition* es una situación que surge cuando
dos o más instancias de un servicio o dos o más servicios acceden
simultáneamente a un recurso compartido y el resultado final depende del orden
impredecible en el que acceden a él.

Para evitar las condiciones de carrera hay varios mecanismos como bloqueos
—*locks*—, semáforos o mutex. En el caso de sistemas distribuidos la
implementación de estos mecanismos es extremadamente compleja. Uno de los
primeros algoritmos para resolver este problema es
[Paxos](https://martinfowler.com/articles/patterns-of-distributed-systems/paxos.html);
este y otros algoritmos similares se basan en el consenso entre las instancia
