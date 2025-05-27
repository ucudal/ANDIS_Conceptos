# 4 Conceptos

## Virtualización

Este documento está basado en [^1], [^2] y [^3].

[^1]: Bass, L.; Klein, J. (2022). Deployment and Operations for Software
    Engineers: A DevOps Engineering text. Publicado independientemente por Len
    Bass and John Klein. Parcialmente disponible
    [aquí](https://www.researchgate.net/publication/335635819_Deployment_and_Operations_for_Software_Engineers).

[^2]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

<!-- cSpell:ignore Tannenbaum -->

[^3]: van Steen, M., Tannenbaum, A. (2025). Distributed Systems: Principles and
    Paradigms, 4<sup>th</sup> edition. Maarten van Steen. Disponible
    [aquí](https://www.distributed-systems.net/index.php/books/ds4/).

### Un poco de historia

En los años sesenta era prácticamente imposible compartir recursos de una
computadora física —memoria, almacenamiento, procesador, etc.—  entre varias
aplicaciones independientes. Las aplicaciones se ejecutaban de una a la vez, por
lo que era necesario descargar una aplicación y sus datos para poder cargar
otra, lo que implicaba mucho tiempo ocioso —sólo se usaba del 10% del
tiempo[^2]—. Esto era un problema porque las computadoras eran sumamente
costosas —del orden de millones de dólares[^2]—  pero se utilizaba una fracción
de los recursos disponibles—.

<span id="figura-1"/>

<a title="Unidentified US government agent, Public domain, via Wikimedia
Commons"
href="https://commons.wikimedia.org/wiki/File:Supercomputer_NSA-IBM360_85.jpg"><img
width="512" alt="Margaret Hamilton, of NASA, at the IBM 360"
src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Supercomputer_NSA-IBM360_85.jpg/512px-Supercomputer_NSA-IBM360_85.jpg?20141014131020"></a>

*Figura 1: Una consola de IBM 360 de la NSA. Dominio público, via
[Wikimedia Commons](https://commons.wikimedia.org/).*

En esa época comenzaron a aparecer diversos mecanismos que permitían aislar una
aplicación de otra, dando la ilusión de que compartían los mismos recursos
físicos. El aislamiento permitía a los desarrolladores escribir aplicaciones
como si fueran las únicas que usan la computadora, mientras que compartir
recursos permitía que esas varias aplicaciones se ejecutaran en la computadora
al mismo tiempo. Esa ilusión tenía —tiene— sus limitaciones, pero los mecanismos
—con algunas modificaciones— son usados todavía.

Otro de los problemas a resolver en aquél entonces era ejecutar en esas costosas
computadoras las aplicaciones legadas —o *legacy*— creadas para computadoras
obsoletas. La forma de solucionarlo se muestra en la [Figura 2](#figura-2), a
continuación.

<span id="figura-2"/>

![Organización de una aplicación, una interfaz, y un sistema —a la izquierda— y
la misma aplicación e interfaz, pero ejecutando sobre otro
sistema](/diagrams/Virtualization.svg)

*Figura 2: Organización de una aplicación, una interfaz, y un sistema —a la
izquierda— y la misma aplicación e interfaz, pero ejecutando sobre otro
sistema —a la derecha—.* Basado en [^3].

A la izquierda de la [Figura 2](#figura-2) se ve una aplicación que usa una
interfaz con A para ejecutar en un cierto hardware o software A. Un ejemplo, con
hardware: A puede ser un procesador y la interfaz con A sería su conjunto de
instrucciones; otro ejemplo, ahora con software: A puede ser un sistema
operativo y la interfaz con A la API de ese sistema operativo.

A la derecha de la [Figura 2](#figura-2) aparece la misma aplicación que usa la
misma interfaz, pero esa interfaz está sobre una implementación que imita A
sobre otro hardware o software B.

Esto fue lo que hizo el *mainframe* [IBM
System/370](https://www.ibm.com/history/system-370) —y sus sucesores— para
permitir ejecutar aplicaciones legadas —por ejemplo, las creadas para el I[BM
System/360](https://www.ibm.com/history/system-360) anterior—.

### Tipos de virtualización

Para poder entender las diferencias entre los distintos tipos de virtualización,
es importante reconocer que los sistemas computacionales ofrecen cuatro tipos de
interfaces en tres distintos niveles —uno de ellos es el que apareció antes en la
[Figura 2](#figura-2)—:

* **La interfaz entre hardware y software**. Es la arquitectura del conjunto de
   instrucciones —*instruction set*— que incluye las instrucciones privilegiadas
   o de [modo protegido](https://en.wikipedia.org/wiki/Protection_ring) y las
   instrucciones generales o de modo usuario o no-protegido.

* **La interfaz de llamadas al sistema o *system calls***. Es la API
   proporcionada por el sistema operativo para acceder a sus funciones.

* **La interfaz de llamadas a bibliotecas**. Es otra API que suele ocultar las
   llamadas al sistema mencionadas anteriormente para exponer funcionalidades
   más complejas.

Esto se muestra en la [Figura 3](#figura-3), a continuación:

<span id="figura-3"/>

![Las diversas interfaces ofrecidas por los sistemas
computacionales](/diagrams/Virtualization_Interfaces.svg)

*Figura 3: Las diversas interfaces ofrecidas por los sistemas computacionales*
Basado en [^3].

Cuando la virtualización consiste en proveer un conjunto de instrucciones
abstracto para la ejecución de aplicaciones, podemos estar frente a un
intérprete —como es el caso de la [Java Virtual
Machine](https://docs.oracle.com/en/java/javase/24/vm/java-virtual-machine-technology-overview.html)
o el [Common Language Runtime de
.NET](https://learn.microsoft.com/en-us/dotnet/standard/clr)— o un emulador.
Esta situación se puede ver en la [Figura 4](#figura-4), a continuación.

<span id="figura-4"/>

![Una máquina virtual de proceso](/diagrams/Virtualization_Process.svg)

*Figura 4: Una máquina virtual de proceso*. Basado en [^3].

Este tipo de virtualización se llama ≪máquina virtual de proceso≫ para enfatizar
que la virtualización es de un proceso solamente —y no de un sistema operativo
completo—.

Un enfoque alternativo para la virtualización, mostrado en la [Figura
5](#figura-5) a continuación, consiste en proporcionar una capa encima del
hardware original, pero que ofrece como interfaz el conjunto completo de
instrucciones de ese mismo u otro hardware. Este enfoque se conoce como
≪hipervisor de tipo 1≫[^4] y está explicado en detalle más adelante.

<span id="figura-5"/>

![Un hipervisor de tipo 1](/diagrams/Virtualization_Native.svg)

*Figura 5: Un hipervisor de tipo 1*. Basado en [^3].

[^4]: van Steen y Tannenbaum en [^3] lo llaman ≪monitor de máquina virtual
    nativo≫.

De esta forma es posible ejecutar al mismo tiempo diferentes sistemas operativos
independientemente unos de otros.

Un hipervisor de tipo 1 tiene que proveer acceso no sólo al procesador del
hardware en el que está montado, sino también a otros recursos como memoria,
almacenamiento, conexión de red, etc. Esto implica que debe proveer
controladores —*drivers*— para esos recursos.

Una alternativa es ejecutar el hipervisor encima de un sistema operativo, tal
como se muestra en la [Figura 6](#figura-6), a continuación. Este enfoque es
llamado ≪hipervisor de tipo 2≫[^5] y también está explicado en detalle más
adelante.

<span id="figura-6"/>

![](/diagrams/Virtualization_Hosted.svg)

*Figura 6: Un hipervisor de tipo 2*. Basado en [^3].

De esta otra forma también es posible ejecutar al mismo tiempo diferentes
sistemas operativos pero aprovecha las funcionalidades ya implementadas en el
sistema operativo en el que corre el hipervisor.

[^5]: van Steen y Tannenbaum en [^3] lo llaman ≪monitor de máquina virtual
    anfitrión.

### Recursos que se pueden ser compartidos

Los recursos de una computadora que pueden ser compartidos entre diferentes
aplicaciones son:

* **Procesamiento**. Las computadoras modernas tienen múltiples unidades
  centrales de procesamiento
  —[CPU](https://en.wikipedia.org/wiki/Central_processing_unit)— y cada CPU
  puede tener múltiples núcleos —*cores*— de procesamiento; además pueden tener
  una o más unidades de procesamiento gráfico
  —[GPU](https://en.wikipedia.org/wiki/Graphics_processing_unit)— u otros
  procesadores de propósito especial, como una unidad de procesamiento tensorial
  —[TPU](https://en.wikipedia.org/wiki/Tensor_Processing_Unit)—.

* **Memoria**. La computadora física tiene una cantidad fija de memoria física.

* **Disco**. Los discos proporcionan almacenamiento persistente para el código y
  los datos que sobreviven el apagado y reinicio de la computadora. Una
  computadora física tiene uno o más discos conectados, cada uno con una
  capacidad de almacenamiento fija.

* **Conexión de red**. Las redes fueron una adición posterior al conjunto de
  recursos que pueden ser compartidos entre aplicaciones —surgieron en la década
  de los setenta—. Hoy en día prácticamente cualquier computadora tiene una o
  más conexiones de red a través de las cuales pasan todos los mensajes.

<!-- cSpell:ignore compartición -->

### Mecanismos de aislamiento y compartición

Los mecanismos para aislar y compartir los recursos antes mencionados son:

* La **compartición del procesador** se logra mediante el mecanismo de planificación
  de hilos —*thread scheduling*—. El planificador —*scheduler*— selecciona y
  asigna un hilo —*thread*— a un procesador disponible, y ese hilo mantiene el
  control hasta que el procesador es re-planificado. Ningún otro hilo puede
  tomar el control de este procesador sin pasar por el planificador. La
  re-planificación ocurre cuando el hilo cede el control del procesador, cuando
  expira un intervalo de tiempo fijo, o cuando ocurre una interrupción.

* A medida que las aplicaciones crecieron, el código y los datos no cabían todos
  en la memoria física, lo que dio origen al mecanismo de gestión de **memoria
  virtual** —*virtual memory*—. Este mecanismo divide la memoria utilizada por
  un proceso en páginas, e intercambia páginas entre la memoria física y el
  almacenamiento en disco según sea necesario. Las páginas que están en memoria
  física pueden accederse inmediatamente, mientras que otras páginas se
  almacenan en el disco hasta que se usen.

  En una visión simplificada de la memoria virtual, para cada lectura o
  escritura en memoria se comprueba si la ubicación referenciada está
  actualmente en la memoria física. Si lo está, la lectura o escritura procede.
  Si no, se genera una interrupción de falta de página —*page-fault*— y la
  página relevante se recupera del disco y se coloca en memoria. Luego se repite
  la lectura o escritura. Este mecanismo evolucionó para asociar las páginas en
  memoria con el el proceso que las usa, proporcionando aislamiento entre
  procesos en una máquina física. La virtualización extiende esta asociación
  entre páginas y procesos para aislar páginas de memoria entre máquinas
  virtuales, y entre procesos dentro de cada máquina virtual.

* La compartición y el aislamiento del disco se logran mediante varios
  mecanismos. En primer lugar, los discos físicos solo pueden accederse a través
  de un controlador, que asegura que los flujos de datos hacia y desde cada hilo
  se entreguen en secuencia. Por otro lado, el sistema operativo puede etiquetar
  los hilos en ejecución y el contenido del disco —archivos y directorios— con
  información como identificación de usuario y grupo, y restringir la
  visibilidad o el acceso comparando las etiquetas del hilo que solicita acceso
  y el contenido del disco.

<!-- cSpell:ignore hipervisor -->

* El aislamiento de red se logra mediante la **identificación de mensajes**.
  Cada máquina virtual tiene una dirección que se utiliza para identificar
  mensajes hacia o desde esa máquina virtual. El hipervisor
  —o [hypervisor](https://en.wikipedia.org/wiki/Hypervisor)— implementa
  infraestructura de red dentro de la máquina física que permite a las máquinas
  virtuales compartir y aislar el uso de la interfaz de red física, utilizando
  los mismos enfoques y protocolos empleados para redes entre máquinas físicas.

### Máquinas virtuales e hipervisores

<!-- cSpell:ignore hipervisores -->

La [Figura 7](#figura-7), a continuación, muestra varias máquinas virtuales
ejecutándose en una computadora física. La computadora física es llamada
computadora anfitrión —o *host computer*— y las máquinas virtuales son llamadas
computadoras invitadas —o *guest computers*—. También se muestra un hipervisor
que ejecuta directamente sobre la computadora física y que en este caso
habitualmente se llama hipervisor de tipo 1 —o *Type 1 hypervisor* o *bare-metal
hypervisor*—. Estos hipervisores típicamente se encuentran en centros de cómputo
—*data centers*— o en la nube.

<span id="figura-7"/>

![Un hipervisor de tipo 1 o bare-metal
hypervisor](/diagrams/Type_1_Hypervisor.svg)

*Figura 7: Un hipervisor de tipo 1 o *bare-metal hypervisor**. Basado en [^1].

Ejemplos de este tipo de hipervisor incluyen:

* VMware ESXi parte de [VMware
  vSphere](https://www.vmware.com/products/cloud-infrastructure/vsphere)

* [Hyper-V](https://learn.microsoft.com/en-us/windows-server/virtualization/hyper-v/hyper-v-overview?pivots=windows-server)

* [Xen Project](https://xenproject.org)

La [Figura 8](#figura-8), a continuación, muestra otro tipo de hipervisor
llamado de tipo 2 —o *Type 2 hypervisor*—. Estos hipervisores son un servicio
—una aplicación— que se ejecuta sobre un sistema operativo en una máquina
física; este servicio a su vez alberga las máquinas virtuales. Estos
hipervisores típicamente se encuentran en computadoras portátiles o de
escritorio y su uso principal es ejecutar en una máquina virtual aplicaciones
que no están disponibles para el sistema operativo anfitrión.

<span id="figura-8"/>

![Un hipervisor de tipo 2 o hosted
hypervisor](/diagrams/Type_2_Hypervisor.svg)

*Figura 8: Un hipervisor de tipo 2 o *hosted hypervisor**. Basado en [^1].

Ejemplos de este otro tipo de hipervisor incluyen:

* [VirtualBox](https://www.virtualbox.org)

* [VMware
  Workstation](https://www.vmware.com/products/desktop-hypervisor/workstation-and-fusion)

Un hipervisor requiere que sus máquinas virtuales usen el mismo conjunto de
instrucciones que el procesador físico de computador anfitrión: el hipervisor no
traduce ni simula la ejecución de instrucciones.

Existe otra tecnología relacionada con los hipervisores para la ejecución entre
procesadores diferentes, llamada emulador. Un emulador lee el código binario
para el procesador invitado y simula la ejecución de instrucciones invitadas en
el procesador anfitrión. El emulador a menudo también simula dispositivos de
hardware de entrada o salida del invitado.

Un ejemplo de emulador es [QEMU](https://www.qemu.org/).
[UTM](https://mac.getutm.app) es un emulador basado en QEMU para MacOS.

Un hipervisor desempeña dos funciones principales:

* Gestionar el código ejecutándose en cada máquina virtual

* Gestionar las propias máquinas virtuales

#### Gestión del código en las máquinas virtuales

Cuando el código en la máquina virtual solicita acceder a un disco o una
interfaz de red virtual —o cualquier otro dispositivo de entrada o salida
virtual—, es interceptado por el hipervisor y ejecutado por éste en nombre de la
máquina virtual. Esto permite al hipervisor asociar estas solicitudes con la
máquina virtual que las realiza, para enviar luego las respuestas a la máquina
virtual correcta.

Las respuestas a los accesos a disco o a una interfaz de red son interrupciones
asíncronas inicialmente manejadas por el hipervisor. El hipervisor reenvía la
respuesta a la máquina virtual que oportunamente realizó la solicitud de acceso.

Las llamadas al sistema —o *system calls*— en el código en la máquina virtual
—que frecuentemente implican cambiar a [modo *kernel* o
protegido](https://en.wikipedia.org/wiki/Protection_ring)— pueden generar
interrupciones que son inicialmente captadas por el hipervisor y reenviadas a la
máquina virtual apropiada, en forma análoga a como se manejan los acceso a los
dispositivos de entrada o salida.

#### Gestión de las máquinas virtuales

El hipervisor gestiona el ciclo de vida —creación, inicio o *boot*, detención o
*shutdown*, destrucción, etc.— de las máquinas virtuales, actuando según
instrucciones de un usuario o de la infraestructura en la nube.

El hipervisor realiza comprobaciones de salud y monitorea el uso de recursos de
las máquinas virtuales. También forma parte del perímetro de seguridad defensiva
contra ataques.

El hipervisor asegura que una máquina virtual no exceda sus límites de
utilización de recursos —procesador, memoria, ancho de banda de disco y red—.
Antes de iniciar una máquina virtual, verifica que haya suficientes recursos
físicos disponibles y luego hace cumplir esos límites durante la ejecución.

### Implicaciones de las máquinas virtuales en la arquitectura

Hay dos implicaciones principales de las máquinas virtuales para la
arquitectura[^2]:

* **Rendimiento**. La virtualización impacta en el rendimiento. Mientras que los
  hipervisores de tipo 1 tienen solo una modesta penalización en el rendimiento,
  los hipervisores de tipo 2 pueden imponer una sobrecarga significativamente
  mayor.

* **Separación de asuntos —o *concerns*—**: La virtualización permite tratar los
  recursos de ejecución como materias primas, delegando las decisiones de
  aprovisionamiento y despliegue.

### Imágenes

El contenido desde el cual se inicia —es decir, desde el cual se hace el *boot*
de— una máquina virtual es llamado la imagen. La imagen incluye el contenido del
disco que tiene volumen de inicio y el sistema operativo huésped de la máquina
virtual, con los programas y los datos de ésta, más un programa para cargar e
iniciar la máquina virtual —un *boot loader*—.

Hay varias formas de crear una imagen:

* Copiando una imagen de una máquina virtual existente.

* Agregando software a una imagen de una biblioteca de imágenes.

* Instalando el sistema operativo, los controladores y las aplicaciones desde
  cero. Este último mecanismo es el más complicado, pues implica iniciar la
  máquina virtual por primera vez desde un medio de instalación, instalar el
  sistema operativo y los controladores de los dispositivos virtuales —y
 eventualmente también sus respectivas actualizaciones—, más el resto del
  contenido de la máquina virtual.

Una imagen de una máquina virtual puede contener, además de los datos en disco
necesarios para iniciarla, los datos en memoria en un momento dado. A estas
imágenes se les suele llamar *snapshots*. Esto permite al hipervisor ejecutar la
máquina virtual a partir del momento en el que se creó la imagen, en lugar de
iniciarla —es decir, sin hacer el *boot*—. Entre otras cosas, los *snapshots*
permiten mover una máquina virtual de un hipervisor a otro.

### Problemas con las máquinas virtuales

Las máquinas virtuales fueron una gran evolución en la infraestructura de
computación, y continúan siendo un componente clave de los centros de cómputo,
pero presentan algunos problemas:

* **Sobrecarga de recursos**. Cada máquina virtual ejecuta su propio sistema
  operativo completo, lo que consume una cantidad significativa de memoria,
  espacio en disco y capacidad del procesador.

* **Tiempo de inicio**. Las máquinas virtuales pueden tardar minutos en
  arrancar completamente, ya que necesitan iniciar todo un sistema operativo.

* **Tamaño**. Las imágenes de las máquinas virtuales ocupan gigabytes de
  espacio debido a que incluyen datos de los discos —sistema operativo completo,
  programas y datos— y eventualmente datos en memoria.

* **Portabilidad**. A pesar de ser "portátiles", las máquinas
  virtuales menudo no son compatibles entre diferentes hipervisores y
  plataformas.

* **Gestión de imágenes**. No existe un mecanismo estandarizado para construir,
  distribuir y versionado las imágenes de las máquinas virtuales.

* **Compartir imágenes**. El gran tamaño de las imágenes de las máquinas
  virtuales hace difícil su distribución en repositorios compartidos o registros
  centralizados, pues transferir imágenes a través de la red puede ser muy
  lento.

* **Actualización**. Aunque es posible crear una imagen a partir de otra, en
  caso de que sea necesario realizar actualizaciones, hay que hacerlo tanto en
  la imagen original como en todas las imágenes derivadas a partir de ella. Esto
  hace complejo mantener y seguir la traza de las diferentes versiones de una
  máquina virtual.

  La alternativa de mantener múltiples versiones de las imágenes de una máquina
  virtual es extremadamente costosa en términos del costos de almacenamiento.

  Actualizar el software dentro de una máquina virtual frecuentemente requiere
  reiniciar la máquina completa o reemplazar toda la imagen.

* **Configuración**: La configuración post-instalación de las máquinas virtuales
 suele requerir *scripts* complejos o intervención manual.

* **Gestión declarativa**. Aunque las tecnologías de [*desired state
  configuration*](https://learn.microsoft.com/en-us/powershell/dsc/overview?view=dsc-3.0)
  pueden ser utilizadas en las máquinas virtuales, es difícil mantener una
  definición clara y reproducible del estado deseado de una máquina virtual.

Para resolver estos problemas surgió la tecnología de
[contenedores](/4_Conceptos/4_Contenedores.md), que introducen un sistema de
imágenes en capas, registros centralizados, construcción declarativa,
inmutabilidad por diseño y una gestión mucho más eficiente de los recursos
compartidos.

> [!TIP]
> Lean más sobre virtualización en [este
> sitio](https://aws.amazon.com/what-is/virtualization/) de AWS.
