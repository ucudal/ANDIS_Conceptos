# 4 Conceptos

## RPC o *remote procedure call*

RPC ‑o llamada a procedimiento remoto en español‑ es un estilo de interacción
entre [componentes](/4_Conceptos/4_Componente.md) que se basa en las llamadas a
procedimientos ‑sub-rutinas‑ de los lenguajes imperativos, excepto que el
procedimiento llamado se encuentra en otro componente en un espacio de
direccionamiento diferente ‑en otra parte de la red‑[^1].

<!-- cSpell:ignore Tannenbaum -->

[^1]: van Steen, M., Tannenbaum, A. (2025). Distributed Systems: Principles and
    Paradigms, 4<sup>th</sup> edition. Maarten van Steen. Disponible
    [aquí](https://www.distributed-systems.net/index.php/books/ds4/).

El programador codifica la llamada al procedimiento como si se estuviera
llamando a un procedimiento local. La llamada se traduce en un mensaje que se
envía al componente remoto donde se invoca el procedimiento real. Finalmente los
resultados se envían como un mensaje al procedimiento que realizó la llamada.
Este proceso se puede ver de forma esquemática en el [diagrama de
secuencia](/2_Tecnicas_y_herramientas/2_04_.Modelos_de_comportamiento/2_04_03_Diagramas_de_secuencia_UML.md)
de la [Figura 1](#figura-1):

<span id="figura-1"/>

![Diagrama de secuencia de una invocación RPC](/diagrams/RPC.svg)

*Figura 1: Diagrama de secuencia de una invocación RPC*. Basado en [^1].

La secuencia para el llamado al procedimiento remoto es así:

1. El código del lado del cliente realiza una llamada a un procedimiento de la
   forma normal, pero en lugar de invocarse ese procedimiento se invoca un
   *stub* del lado del cliente. Esto se realiza de forma transparente.

2. El *stub* del lado del cliente prepara un mensaje incluyendo los parámetros
   del procedimiento llamado —*marshaling*—.

3. El *stub* del lado del cliente utiliza funciones del sistema operativo
   local para enviar el mensaje al servidor remoto.

4. El sistema operativo local envía el mensaje al sistema operativo remoto.

5. El sistema operativo remoto pasa el mensaje recibido a un *skeleton*[^2] del lado
   del servidor.

6. El *skeleton* del lado del servidor decodifica —*un marshalling*— el mensaje
   para obtener los parámetros del procedimiento llamado.

7. El *skeleton* del lado del servidor invoca el procedimiento de forma normal
   pasando los parámetros recibidos.

[^2]: En [^1] es llamado *stub* del lado del servidor, pero *skeleton* es más
    utilizado para evitar usar *stub* de ambos lados de la interacción.

El proceso es exactamente análogo para devolver el resultado.

> [!TIP]
> Vean la sección **4.2 Remote Procedure Call** de [^1] para obtener más
> información sobre RPC.

Los orígenes del concepto de RPC se remontan a los años '80. Existen diferentes
implementaciones del concepto de RPC que van desde los más antiguos como
[DCE](https://publications.opengroup.org/c706) hasta los más modernos como
gRPC:

* [gRPC](https://grpc.io) es un *framework* de RPC de alto rendimiento, de
  código abierto y que no depende del lenguaje, desarrollado por Google. En gRPC
  los parámetros se transmiten en formato binario, es asíncrono, soporta
  autenticación, flujos de datos bi-direccionales, control de flujo, cancelación
  y tiempos de espera; usa HTTP 2.0 para transporte.

<!-- cSpell:ignore CORBA -->

* [CORBA](https://www.corba.org) —*Common Object Request Broker Architecture*—
  es un estándar de arquitectura e infraestructura abierta e independiente del
  proveedor desarrollado por el Object Management Group
  —[OMG](https://www.omg.org)— que permite que diferentes componentes de
  software se comuniquen e interactúen a través de una red, incluso si están
  escritos en diferentes lenguajes o se ejecutan en diferentes plataformas.

* Java
  [RMI](https://www.oracle.com/java/technologies/javase/remote-method-invocation-home.html)
  es un mecanismo que permite que un objeto Java que se ejecuta en una máquina
  virtual —JVM o *Java virtual machine*— invoque métodos en un objeto Java que
  reside en otra JVM, potencialmente en un servidor diferente.

<!-- cSpell:ignore DCOM -->

* [DCOM](https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-dcom/4a893f3d-bd29-48cd-9f43-d9777a4415b0)
  o *Distributed Component Object Model* es una tecnología de Microsoft que
  permite que componentes de software se comuniquen a través de una red;
  actualmente está descontinuado.

* [.NET
  Remoting](https://learn.microsoft.com/en-us/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
  es un *framework* de computación distribuida que formaba parte de Microsoft
  .NET Framework —versiones 1.0 a 4.8— y que permitía a las aplicaciones
  comunicarse con objetos ubicados en diferentes dominios de aplicación
  reemplazado por WCF.

* [WCF](https://learn.microsoft.com/en-us/dotnet/framework/wcf/) o *Windows
  Communication Foundation* es un *framework* unificado para crear aplicaciones
  orientadas a servicios en .NET.

> [!TIP]
> Consulta el documento sobre [Remote Procedure
> Invocation](/2_Tecnicas_y_herramientas/2_13_.Integracion_aplicaciones/2_13_3_Remote_Procedure_Invocation.md)
> para entender RPC en el contexto de [integración de
> aplicaciones](/2_Tecnicas_y_herramientas/2_13_.Integracion_aplicaciones/).
