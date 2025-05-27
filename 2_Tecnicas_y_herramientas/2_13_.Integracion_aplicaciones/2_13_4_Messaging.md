# 2 Técnicas y herramientas

## 2.13 Integración de aplicaciones

### 2.13.4 *Messaging* o mensajería

La mensajería es un mecanismo que permite [integrar
aplicaciones](./2_13_.Integracion_aplicaciones.md) que fueron construidas
independientemente, en lenguajes diferentes, en plataformas diferentes[^1].

<!-- cSpell:ignore Hohpe -->

[^1]: Hohpe, G. & Woolf, B. (2003). Enterprise Integration Patterns: Designing,
Building, and Deploying Messaging Solutions. Addison-Wesley Professional.

Los mecanismos como [File Transfer](./2_13_1_File_Transfer.md) y [Shared
Database](./2_13_2_Shared_Database.md) permiten que las aplicaciones compartan
sus datos pero no su funcionalidad, mientras que [Remote Procedure
Invocation](./2_13_3_Remote_Procedure_Invocation.md) permite que las
aplicaciones compartan funcionalidad, pero también las acopla estrechamente: hay
enormes diferencias en términos de [desempeño](/4_Conceptos/4_Rendimiento.md) y
[confiabilidad](/4_Conceptos/4_Disponibilidad.md) entre invocaciones locales y
remotas, y cuando estas diferencias no son tenidas en cuenta, el uso puede
conducir a sistemas lentos y poco confiables.

Lo que se necesita es la posibilidad de enviar datos como en [File
Transfer](./2_13_1_File_Transfer.md), pero que la aplicación que los recibe se
entere cuando lleguen. El envío de datos puede desencadenar un comportamiento en
la aplicación receptora como en [Remote Procedure
Invocation](./2_13_3_Remote_Procedure_Invocation.md), pero sin los problemas
recién mencionados. El envío debe ser asíncrono para que la aplicación que envía
los datos no tenga que esperar por la aplicación que los recibe.

> Para integrar aplicaciones usa  mensajería y transfiere paquetes de datos de
> forma frecuente, inmediata, confiable y asíncrona, utilizando formatos
> personalizables.

<span id="figura-1"/>

![Integración de aplicaciones por mensajería](/diagrams/Messaging.svg)

*Figura 1: Integración de aplicaciones por mensajería*. Tomado de [^1]

La mensajería asíncrona es una solución pragmática a los problemas de los
sistemas distribuidos al no requerir que ambos sistemas estén disponibles al
mismo tiempo y al reconocer la latencia inherente de las comunicaciones remotas.
Esto tiende a un aumento en la [cohesión](/4_Conceptos/4_Cohesion.md) —al
promover una preferencia por el procesamiento local— y un baja en el
[acoplamiento](/4_Conceptos/4_Acoplamiento.md) —al llevar a minimizar
interacciones remotas—.

La mensajería comparte algunas de las características de [File
Transfer](./2_13_1_File_Transfer.md) pues el envío de los mensajes queda
desacoplado de la recepción y el mensaje puede ser transformado en el camino sin
que la aplicación que envía el mensaje o la que lo recibe lo sepa.

Este desacoplamiento también permite que varias aplicaciones reciban el mismo
mensaje transmitido por otra. Esto separa las decisiones de integración de
aplicaciones las decisiones de desarrollo de aplicaciones.

Cuando las aplicaciones puedan tener diferentes modelos conceptuales de los
datos enviados en los mensajes, se podrán aplicar las mismas medidas que se
aplican en [Shared Database](./2_13_2_Shared_Database.md) para tener esquemas
compartidos entre las aplicaciones que intercambian mensajes.

Enviar mensajes no sólo permite que las aplicaciones intercambien datos, sino
también que una desencadene un comportamiento en la otra, pues los mensajes
pueden invocar acciones en los receptores. Esto no será tan eficiente como con
[Remote Procedure Invocation](./2_13_3_Remote_Procedure_Invocation.md), pero la
aplicación que envía el pedido puede seguir trabajando mientras la que lo recibe
lo procesa.

Usar mensajería implica conocer algunas prácticas comunes para los nuevos temas
que surgen:

* ¿Cómo transferir los paquetes de datos? El ≪remitente≫ —la aplicación que
  envía el mensaje— lo envía a través de un [Message
  Channel](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageChannel.html)
  o ≪canal de mensajes≫ que conecta el remitente con el ≪receptor≫ —la
  aplicación que recibe el mensaje—.

<!-- cSpell:ignore enrutador https://dle.rae.es/enrutador -->

* ¿Cómo saber dónde enviar los mensajes? Los mensajes pueden ser enviados a un
  [Message
  Router](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageRouter.html)
  o ≪enrutador de mensajes≫, el que enviará el mensaje al receptor adecuado.

* ¿Cómo saber qué formato de datos utilizar? El remitente pueden enviar los
  mensajes a un [Message
  Translator](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageTranslator.html)
  o ≪traductor de mensajes≫ que convertirá el mensaje al formato adecuado para
  el receptor y luego le enviará el mensaje.

* ¿Cómo conectar la aplicación con el sistema de mensajería? La aplicación debe
  implementar [Message
  Endpoint](https://www.enterpriseintegrationpatterns.com/patterns/messaging/MessageEndpoint.html)
  para realizar el envío y recepción de mensajes.

> [!TIP]
> Para conocer más sobre mensajería puedes consultar además de [^1] el sitio
> [Enterprise Integration
> Patterns](https://www.enterpriseintegrationpatterns.com) de sus mismos
> autores.
