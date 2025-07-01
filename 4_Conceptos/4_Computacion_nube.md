# 4 Conceptos

## Computación en la nube o *cloud computing*

Este documento no se propone tratar todos los temas asociados con la computación
en la nube, sino resumir algunos aspectos que son importantes para las
decisiones arquitectónicas. Está basado en [^1] y [^2].

> [!TIP]
> Te recomendamos que consultes [Azure Well-Architected
> Framework](https://learn.microsoft.com/en-us/azure/well-architected/) o [AWS
> Well-Architected](https://aws.amazon.com/architecture/well-architected) para
> conocer más detalles sobre arquitectura de aplicaciones en la nube.

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

<!-- cSpell:ignore Mell Grance -->

[^2]: Mell, P.; Grance, T. (2011). The NIST Definition of Cloud Computing,
    Special Publication 800-145. National Institute of Standards and Technology,
    U.S. Department of Commerce. Disponible
    [aquí](https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-145.pdf).

El [NIST](https://www.nist.gov) —*National Institute of Standards and
Technology* o Instituto Nacional de Estándares y Tecnología del Departamento de
Comercio de los Estados Unidos— define la computación en la nube como un modelo
tecnológico que permite acceder a recursos informáticos compartidos —redes,
servidores, almacenamiento, aplicaciones y servicios— a través de Internet de
forma rápida y sencilla, sin necesidad de gestión compleja[^2].

Cuando hablamos coloquialmente de "la nube" nos referimos a:

* Recursos —cómputo, almacenamiento, etc.— por los que alguien —y no quién los
  consume— es responsable de comprarlos, de mantenerlos, etc.

* Poder acceder a esos recursos a través de Internet.

* Pagar sólo por los recursos que se usan.

* A que los recursos son elásticos, se puede consumir más o menos según sea necesario.

* A que una vez que creada una cuenta en el proveedor de nube, el titular de esa
  cuenta puede crear y eliminar recursos según sea necesario.

### Características

Formalmente, el ya mencionado NIST define como características esenciales de la
nube[^2]:

* **Autoservicio bajo demanda**. Un consumidor puede aprovisionar
  unilateralmente capacidades —cómputo, almacenamiento, etc.— según sus
  necesidades, de forma automática, sin necesidad de interacción humana con cada
  proveedor de servicios.

* **Amplio acceso a través de la red**. Las capacidades están disponibles en la
  red y se accede a ellas mediante mecanismos estándar que facilitan su uso por
  plataformas heterogéneas de clientes ligeros o pesados —dispositivos móviles,
  *tablets*, portátiles y estaciones de trabajo—.

* ***Pooling* de recursos**. Los recursos del proveedor se agrupan para atender
  a múltiples consumidores mediante un modelo *multi-tenant* —múltiples
  inquilinos—, con diferentes recursos físicos y virtuales asignados y
  reasignados dinámicamente según la demanda del consumidor. Existe una
  sensación de independencia de la ubicación, ya que el cliente generalmente no
  tiene control ni conocimiento sobre la ubicación exacta de los recursos
  proporcionados, pero puede especificar la ubicación con un mayor nivel de
  abstracción —país, estado o centro de cómputo—. Algunos ejemplos de recursos
  incluyen almacenamiento, procesamiento, memoria y ancho de banda de red.

* **Rápida elasticidad**. Las capacidades se pueden aprovisionar y liberar de
  forma elástica, en algunos casos de forma automática, para escalar rápidamente
  hacia afuera y hacia adentro según la demanda. Para el consumidor, las
  capacidades disponibles para el aprovisionamiento a menudo parecen ilimitadas
  y pueden asignarse en cualquier cantidad y en cualquier momento.

* **Servicio medido**. Los sistemas en la nube controlan y optimizan
  automáticamente el uso de recursos mediante una capacidad de medición —por
  tiempo o por uso— con un nivel de abstracción adecuado al tipo de servicio
  —por ejemplo almacenamiento, procesamiento, ancho de banda y cuentas de usuario
  activas—. El uso de recursos se puede supervisar, controlar y reportar, lo que
  proporciona transparencia tanto al proveedor como al consumidor del servicio
  utilizado.

### Modelos de despliegue

El NIST también define modelos de despliegue, entre ellos[^2]:

* **Nube pública** o *public cloud*. Las nubes públicas son infraestructuras
  ofrecidas por proveedores comerciales a cualquier cliente que pague y acepte
  sus términos. Los servicios construidos sobre estas plataformas son
  típicamente accesibles desde Internet, pero se pueden implementar controles de
  seguridad y conexiones privadas sobre redes públicas.

* **Nube privada** o *private cloud*. Las nubes privadas son infraestructuras
  en uno o más centros de cómputo que una organización posee y opera
  exclusivamente para su propio uso. Se eligen por razones de control, seguridad
  y costos. Tanto la infraestructura como los servicios son accesibles sólo
  dentro de la red interna de la organización.

* **Nube híbrida** o *hybrid cloud*. La nubes híbridas combinan nubes privadas
  y públicas para diferentes cargas de trabajo —*workloads*—. Se utilizan
  durante procesos de migración entre modelos de nube o cuando ciertos datos
  requieren niveles de control y supervisión más estrictos que los que puede
  ofrecer una nube pública por motivos legales o por regulaciones.

### Modelos de servicio

El NIST ya mencionado define tres modelos de servicio de computación
en la nube[^2]:

* **SaaS** o *software as a service* o software como servicio. La capacidad que
  se ofrece al consumidor consiste en utilizar las aplicaciones del proveedor
  que se ejecutan en una infraestructura en la nube. Se puede acceder a las
  aplicaciones desde diversos dispositivos cliente a través de una interfaz de
  cliente ligero, como un navegador web —por ejemplo, correo electrónico web—, o
  una interfaz de programación —por ejemplo, SMTP—. El consumidor no gestiona ni
  controla la infraestructura en la nube subyacente, incluyendo la red, los
  servidores, los sistemas operativos, el almacenamiento ni las capacidades
  individuales de las aplicaciones, con la posible excepción de la configuración
  limitada de las aplicaciones específicas del usuario.

* **PaaS** o *platform as a service*. La capacidad de programación que se ofrece
  al consumidor consiste en implementar en la infraestructura en la nube
  aplicaciones creadas o adquiridas por el consumidor, creadas con lenguajes,
  bibliotecas, servicios y herramientas compatibles con el proveedor. El
  consumidor no gestiona ni controla la infraestructura en la nube subyacente,
  incluyendo la red, los servidores, los sistemas operativos ni el
  almacenamiento, pero sí controla las aplicaciones implementadas y las posibles
  opciones de configuración del entorno donde están alojadas las aplicaciones.

* **IaaS** o *infrastructure as a service*. La capacidad que se ofrece al
  consumidor consiste en aprovisionar procesamiento, almacenamiento, redes y
  otros recursos informáticos fundamentales, donde el consumidor puede
  implementar y ejecutar software arbitrario, incluyendo sistemas operativos y
  aplicaciones. El consumidor no administra ni controla la infraestructura de
  nube subyacente, pero sí controla los sistemas operativos, el almacenamiento y
  las aplicaciones implementadas, y posiblemente un control limitado sobre
  determinados componentes de red —por ejemplo, los *firewalls* del *host*—.

<span id="figura-1"/>

![Comparación entre los modelos IaaS, PaaS y SaaS de nube e infraestructura en
instalaciones propias](/assets/Iaas_vs_PaaS_vs_SaaS.png.jpg)

*Figura 1: Comparación entre los modelos IaaS, PaaS y SaaS de nube e
infraestructura en instalaciones propias.*

### *Public Cloud Data Centers*

Un centro de cómputo de nube pública contiene decenas de miles de servidores
—típicamente entre 5.000 y 25.000— y almacenamiento del orden de petabytes a
exabytes, en galpones del tamaño de varias canchas de fútbol —entre poco menos
de una a más de 50—. La limitante del tamaño de los centros de cómputo es el
consumo de energía y —en consecuencia— la capacidad para controlar el calor que
disipan los servidores: un centro de cómputo consume entre 40 a más de 100
megawatts —que equivale a lo que consumen ciudades enteras de entre 100.000 a
más de 300.000 habitantes—.

Los servidores en realidad están compuestos de *blades* de cómputo —con varios
procesadores cada uno— y de discos —con varios discos mecánicos o de estado
sólido cada uno—. Los *blades* están organizados en *racks* y cada *rack* tiene
entre 25 y 50 servidores. El centro de cómputo tiene hileras de *racks*
conectados por *switches* de alta velocidad.

El centro de cómputo tiene además fuentes de energía redundante como UPS y
generadores para asegurar la alimentación continua de energía eléctrica.

<span id="figura-1"/>

<!-- cSpell:ignore Daoducquan -->

<a title="Daoducquan, CC BY-SA 4.0
&lt;https://creativecommons.org/licenses/by-sa/4.0&gt;, via Wikimedia Commons"
href="https://commons.wikimedia.org/wiki/File:Data_Center_c%E1%BB%A7a_CMC_Telecom_(1).jpg"><img
width="512" alt="Centro de datos de CMC Telecom en Vietnam"
src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fc/Data_Center_c%E1%BB%A7a_CMC_Telecom_%281%29.jpg/512px-Data_Center_c%E1%BB%A7a_CMC_Telecom_%281%29.jpg?20180528075613"></a>

*Figura 1: Centro de datos de CMC Telecom en Vietnam*. © Daoducquan, [CC BY-SA
4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en), via [Wikimedia
Commons](https://commons.wikimedia.org/).

> [!TIP]
> ¿Alguna vez te has preguntado cómo es un *public cloud data center* por
> dentro? Puedes ver este [tour
> virtual](https://datacenters.microsoft.com/tour/).

<!-- cSpell:ignore GRDP -->

Cuando accedes a servicios de un proveedor de nube pública estás accediendo a
conjuntos de servidores alojados en alguna parte del mundo. Los proveedores
organizan los centros de cómputo en regiones o *regions*. Las regiones son un
agrupamiento físico y lógico que aseguran que los servidores dentro de la región
están relativamente cerca geográficamente de los usuarios que los acceden y
además que satisfacen restricciones impuestas por regulaciones como
[GRDP](https://gdpr-info.eu).

Una región tiene múltiples centros de cómputo agrupados en zonas de
disponibilidad —*availability zones*—. Las zonas están separadas geográficamente
de forma de minimizar la probabilidad de que cortes de energía o desastres
naturales afecten a todas las zonas simultáneamente.

Elegir la región y las zonas de disponibilidad es una decisión arquitectónica
importante.

El acceso a la nube pública se realiza a través de Internet. Hay dos puertas de
enlace: *management gateway* y *messaging gateway*. La primera permite a los
operadores gestionar los recursos en la nube mientras que la segunda permite a
las aplicaciones comunicarse con los recursos en la nube. El *management
gateway* típicamente incluye un portal web y una API REST; habitualmente hay una
interfaz de línea de comandos —o CLI, *command line interface*— encima de esta
API REST—.

### Fallos en la nube pública

Como los centros de cómputo tienen tantos servidores, aumentan las
probabilidades de que alguno falle en algún momento. Amazon informa que en un
centro de cómputo con alrededor de 64.000 servidores, cada una con dos unidades
de disco giratorios, aproximadamente 5 servidores y 17 discos fallarán cada día
[^1]. También pueden fallar los *switches* y hasta el centro de cómputo
completo.

Aunque el proveedor de nube pública tenga pocas interrupciones totales, alguno
de los servidores físicos asociados a un recurso puede fallar; y si puede
fallar, fallará. Es importante conocer el nivel de
[disponibilidad](/4_Conceptos/4_Disponibilidad.md) de cada uno de los recursos
involucrados en una solución arquitectónica.

### Tiempos de espera o *timeouts*

Los tiempos de espera o *timeouts* son una [táctica de
disponibilidad](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_01_Tacticas_disponibilidad.md).
Cuando se agota el tiempo de espera de una solicitud, no es posible distinguir
una falla —falta de respuesta— de una respuesta lenta —una respuesta que demora
más del tiempo de espera—. Esto hace que cuando ocurre un *timeout* tengamos que
asumir que ocurre una falla, aunque no sepamos cuál es la falla y menos dónde
ocurrió la falla —y en los [sistemas
distribuidos](/4_Conceptos/4_Computacion_distribuida.md) puede estar en varios
lados—.

> [!TIP] Existen patrones de arquitectura como [Circuit
> Breaker](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura.md/2_09_Circuit_breaker.md)
> y
> [Retry](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura.md/2_09_Retry.md)
> para manejar fallas eventuales o intermitentes, pues usualmente hay un costo
> asociado a las acciones de recuperación de las fallas.

### Latencia de cola larga

La latencia de cola larga se refiere al fenómeno en el que un pequeño porcentaje
de solicitudes experimenta tiempos de respuesta —latencia— significativamente
más largos que la mayoría. Esta cola larga de respuestas lentas puede afectar
desproporcionadamente el rendimiento general del sistema distribuido y la
experiencia del usuario, incluso si la latencia promedio parece baja. Esta
latencia se debe a la congestión en alguna parte del camino de procesamiento de
cada solicitud.

<span id="figura-2"/>

![Ejemplo de latencia de cola larga](/assets/Long_Tail_Latency.png)

*Figura 2: Ejemplo de latencia de cola larga. Los datos son simulados pero
podrían representar —por ejemplo— el tiempo de respuesta a una solicitud a una
aplicación web en la nube.*

En la [Figura 2](#figura-2) anterior, el eje de las abscisas muestra la latencia
—el tiempo que transcurre entre que se envía una solicitud hasta que se comienza
a recibir la respuesta a o el resultado de esa solicitud— y el eje de las
ordenadas muestra la cantidad de solicitudes que tuvieron cierta latencia. La
mayoría de las solicitudes tienen una latencia de 12 milisegundos y el promedio
de la latencia es del orden de 18 milisegundos; pero hay respuestas que demoran
40 milisegundos o más. En este ejemplo pueden ver como, aunque el promedio de la
demora en obtener una respuesta puede ser tolerable, hay una cantidad de
respuestas que van a demorar el doble, el triple, o más que el promedio —estas
son las solicitudes que están en la parte larga de la cola—.

Un patrón para abordar este problema es [Request
Hedging](/2_Tecnicas_y_herramientas/2_09_.Patrones_de_arquitectura.md/2_09_Request_Hedging.md).
Otros patrones y técnicas aparecen también en [^3].

<!-- cSpell:ignore Timbó -->

[^3]: Dean, J., & Barroso, L. A. (2013). The Tail at Scale. Communications of
    the ACM, 56(2), 74–80. Disponible [aquí](
    https://doi-org.proxy.timbo.org.uy/10.1145/2408776.2408794) vía
    [Timbó](https://timbo.org.uy/home)

> [!TIP]
> Otros temas tratados en [^1] bajo computación en la nube son comunes a los
> sistemas distribuidos en general y están incluidos en el documento sobre
> [computación distribuida](./4_Computacion_distribuida.md):
>
> * [Múltiples instancias para escalabilidad y
>   disponibilidad](./4_Computacion_distribuida.md#múltiples-instancias-para-escalabilidad-y-disponibilidad)
>
> * [Balanceo de carga](./4_Computacion_distribuida.md#balanceo-de-carga)
>
> * [Manejo del estado](./4_Computacion_distribuida.md#manejo-del-estado)
>
> * [Coordinación de la
>   hora](./4_Computacion_distribuida.md#coordinación-de-la-hora)
>
> * [Coordinación de los
>   datos](./4_Computacion_distribuida.md#coordinación-de-los-datos)

### Auto-escalado o *autoscaling*

En un centro de cómputo tradicional con servidores físicos es necesario asignar
recursos suficientes como para manejar las cargas pico —las cargas más altas que
se pueda llegar a tener—. Cuando la carga no está en el pico —lo cual
generalmente sucede la mayor parte del tiempo— los recursos están ociosos —pero
el costo de comprarlos y operarlos existe igualmente aunque no se usen—.

Dos de las características mencionadas al comienzo sobre la computación en la
nube son que se paga sólo por los recursos que se usan y que los recursos son
elásticos, es decir, se pueden consumir más o menos recursos según sea
necesario. Al usar ambas características juntas es posible construir soluciones
capaces de manejar diferentes cargas sin pagar más de lo necesario.

Las cargas pueden ser relativamente estables o pueden variar de forma predecible
—por ejemplo, en ciertas épocas del año—. En estos casos la asignación de
recursos se puede hacer de forma manual. Pero también es posible que las cargas
suban o bajen rápidamente y de forma impredecible. En estos otros casos
necesitamos poder agregar o quitar instancias dinámicamente.

Los proveedores de nube pública ofrecen el servicio de auto-escalado que
consiste en crear nuevas instancias cuando la carga aumenta y eliminarlas cuando
disminuye. El servicio típicamente usa el [balanceo de
carga](./4_Computacion_distribuida.md#balanceo-de-carga) para analizar la
latencia o la capacidad de las instancias y así aumentar o disminuir la cantidad
de las instancias detrás del balanceador de carga.

Supongan un par de [máquinas
virtuales](./4_Virtualizacion.md#máquinas-virtuales-e-hipervisores) iguales.
Cuando alguna de ellas recibe más solicitudes de las que puede procesar —el
balanceador de carga puede detectar el aumento de la latencia— o cuando los
recursos disponibles bajan de cierto umbral —que el balanceador de carga puede
monitorear—, el auto-escalado crea una nueva instancia de la máquina virtual a
partir de la misma imagen que las anteriores, la registra con el balanceador de
carga, y éste comienza a enviarle solicitudes de la misma forma que lo hace con
las anteriores; esto debería disminuir la cantidad de solicitudes a las otras
dos máquinas virtuales. Como los clientes no saben qué máquina virtual procesa
las solicitudes, esto es transparente para ellos.

El auto-escalado implica que cuando no es necesaria una de las máquinas
virtuales, debe ser removida. Cuando el servicio de auto-escalado remueve una
instancia, no solamente apaga la máquina virtual. Antes debe quitarla del
balanceador de carga —para que no siga recibiendo solicitudes— y avisarle de que
va a ser apagada —para que los procesos que están en curso puedan terminar—;
después de unos instantes, la apaga. Este proceso se conoce como «drenado» o *draining*.

Para configurar el auto-escalado típicamente es necesario indicar:

* La imagen de la máquina virtual y cualquier configuración que ella necesite.

* Los umbrales de las métricas —por ejemplo, porcentaje de utilización del
  procesador, del ancho de banda de entrada y salida, de la memoria, etc.— a lo
  largo de un período de tiempo[^4] a partir de los cuales se crea una nueva
  instancia.

* Los umbrales de las métricas a lo largo de un período de tiempo por debajo de
  los cuales se elimina una nueva instancia.

* La cantidad mínima y máxima de instancias a gestionar de forma automática.

[^4]: La métrica utilizada para escalar —en este caso la utilización del
    procesador— no se evalúa de forma instantánea sino a lo largo de un período
    de tiempo. En casos puntuales la métrica puede ser mayor —o menor— que el
    porcentaje indicado para crear -o eliminar- una instancia por breves
    instancias, en cuyo caso no es conveniente tomar ninguna acción. Hay que
    tener en cuenta que levantar una nueva máquina virtual puede requerir cierto
    tiempo, y el período durante el cual se evalúa la métrica tiene que tener
    relación esto. Una regla de auto-escalado puede ser "crear una nueva
    instancia cuando el porcentaje de utilización del procesador sea superior al
    80% durante 5 minutos".

La configuración de auto-escalado también puede incluir la creación o
eliminación de instancias en momentos predeterminados, siguiendo los patrones de
aumento y disminución de carga conocidos de antemano.

> [!IMPORTANT]
> El auto-escalado es aplicable también a otros servicios y recursos, no sólo a
> máquinas virtuales; aunque los detalles en otros casos van a ser diferentes,
> van a ser análogos a estos en términos generales.

> [!TIP]
> Puedes ver más información sobre auto-escalado de otros servicios en
> proveedores de nube
> [aquí](https://learn.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-resource-manager-autoscaling)
> y
> [aquí](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html).
