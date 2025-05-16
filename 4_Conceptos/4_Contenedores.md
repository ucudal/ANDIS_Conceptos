# 4 Conceptos

## Contenedores o *containers*

Este documento está basado en [^1], [^2] y [^3].

[^1]: Bass, L.; Klein, J. (2022). Deployment and Operations for Software
    Engineers: A DevOps Engineering text. Publicado independientemente por Len
    Bass and John Klein. Parcialmente disponible
    [aquí](https://www.researchgate.net/publication/335635819_Deployment_and_Operations_for_Software_Engineers).

[^2]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

[^3]: Microsoft. (2025). About Windows containers. Microsoft Learn. Disponible
    [aquí](https://learn.microsoft.com/en-us/virtualization/windowscontainers/about/).

Los contenedores —o *containers*— son un mecanismo para mantener las ventajas de
la virtualización, pero reduciendo el tamaño —y en consecuencia el tiempo de
transferencia— de las imágenes y el tiempo de inicio[^1].

> [!TIP]
> Vean también el documento sobre
> [virtualización](/4_Conceptos/4_Virtualizacion.md), que incluye algunos
> [problemas con las máquinas
> virtuales](./4_Virtualizacion.md#problemas-con-las-máquinas-virtuales), en
> particular con las [imágenes](./4_Virtualizacion.md#imágenes).

Un contenedor proporciona la capacidad de empaquetar y ejecutar una aplicación
en un entorno ligeramente aislado y liviano. El aislamiento y la seguridad
permiten ejecutar muchos contenedores simultáneamente en un sistema operativo
anfitrión. Los contenedores son livianos pero contienen todo lo necesario para
ejecutar aplicaciones, por lo que no dependen de lo que esté instalado en el
anfitrión. Los contenedores se pueden replicar con la seguridad de que todas las
réplicas funcionan de la misma manera[^3][^4].

<!-- cSpell:ignore Dockerdocs -->

[^4]: Docker. (2025). What is Docker? Dockerdocs. Disponible
    [aquí](https://docs.docker.com/get-started/docker-overview).

En la [Figura 1](#figura-1), a continuación, se muestran varios contenedores
funcionando bajo el control de un motor de contenedores —o *container runtime
engine*—, que a su vez se ejecuta sobre un sistema operativo, que puede estar
instalado directamente sobre hardware —*bare metal*— o incluso en un hipervisor
—en una máquina virtual—. Así como todas las máquinas virtuales en una
computadora anfitrión física comparten el mismo hardware físico subyacente,
todos los contenedores comparten el mismo *kernel* del sistema operativo; y a
través del sistema operativo, comparten el mismo hardware físico —o virtual—
subyacente.

<span id="figura-1"/>

![](/diagrams/Containers.svg)

<!-- cSpell:ignore hipervisor -->

*Figura 1: Contenedores en un motor de contenedores sobre un sistema
operativo sobre un hipervisor o hardware*. Basado en [^1] y  [^3].

Como los contenedores comparten el *kernel* del sistema operativo anfitrión,
están limitados por sus capacidades. Un contenedor Linux requiere un *kernel*
Linux en el anfitrión y un contenedor Windows requiere un *kernel* Windows en el
anfitrión; las distribuciones de Linux en el anfitrión y en el contenedor pueden
ser diferentes, así como también pueden ser diferentes las versiones de Windows
Server[^6].

[^6]: Es posible ejecutar contenedores Linux en Windows, pero eso requiere que
    el [Windows anfitrión tenga instalado el Windows Subsystem for
    Linux](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers).

<!-- cSpell:ignore irrestricto -->

Aunque un contenedor comparte el *kernel* con el sistema operativo anfitrión, el
contenedor no obtiene acceso irrestricto a ese sistema operativo ni a la
computadora anfitrión. Por el contrario, el contenedor obtiene una vista aislada
—y en algunos casos virtual— de la computadora anfitrión. Por ejemplo, un
contenedor puede acceder al sistema de archivos del anfitrión, pero los cambios
que haga no serán visibles para los demás contenedores y serán descartados
cuando el contenedor se detenga. Para guardar datos de forma persistente el
contenedor puede montar un almacenamiento persistente externo.

Un contenedor se construye sobre el *kernel*, pero el *kernel* no proporciona
todos servicios que las aplicaciones en el contenedor necesitan; estos otros
servicios están implementados en bibliotecas —*libraries*— provistas por
archivos del sistema —*system files*— que ejecutan en [modo usuario o
no—protegido](https://en.wikipedia.org/wiki/Protection_ring) —a diferencia del
*kernel* que ejecuta en modo protegido—.

Por lo tanto, el contenedor necesita su propia copia de estos archivos del
sistema en modo usuario, que están empaquetados en lo que se conoce como una
imagen base. La imagen sirve como la capa fundamental sobre la cual se construye
un contenedor, proporcionándole aquellos servicios del sistema operativo que no
son proporcionados por el *kernel*[^3].

Los contenedores se crean entonces a partir de imágenes de contenedores. Una
imagen de contenedor es un conjunto de archivos organizados en capas que reside
en un archivo local o en un registro de contenedores remoto. Además de los
archivos del sistema operativo en modo de usuario necesarios para ejecutar las
aplicaciones, la imagen incluye los archivos de los entornos de ejecución
—*runtimes*— y demás dependencias de las aplicaciones, más otros archivos de
configuración que la aplicación necesite.

Las imágenes de los contenedores se construyen en capas. Cada capa contiene una
parte de esos archivos, que cuando se superponen, representan la imagen
completa. Por ejemplo, una capa puede contener sólo los archivos de modo usuario
de una distribución particular de Linux, otra capa encima los archivos de un
entorno de ejecución en particular en Python, otra capa encima los archivos de
otro entorno de ejecución con Django, y así sucesivamente.

### Aspectos internos de los contenedores

Para lograr las características de los contenedores que los diferencian de las
máquinas virtuales es necesario:

* Evitar que un contenedor deba incluir una copia completa del sistema operativo
  y de las bibliotecas que las aplicaciones en ese contenedor necesiten para
  funcionar —como sucede con las máquinas virtuales—.

* Lograr que los recursos a los que tiene acceso un contenedor queden aislados
  de los demás recursos de los otros contenedores.

* Que exista algún tipo de control o límite en los recursos que puede consumir
  cada contenedor.

Estos aspectos pueden ser logrados utilizado tres mecanismos disponibles en el
*kernel* de Linux—:

<!-- cSpell:ignore enrutamiento -->

* **Espacios de nombres o *namespaces***. Los *namespaces* son un mecanismo de
  aislamiento que permite separar recursos del sistema para que parezcan estar
  dedicados exclusivamente a un conjunto específico de procesos. Los namespaces
  permiten tener múltiples instancias aisladas de recursos globales del sistema,
  haciendo que los procesos dentro de un *namespace* específico vean su propia
  versión aislada de estos recursos. Existen varios *namespaces* que permiten
  aislar los procesos —el *namespace* PID—, los recursos de red —el *namespace*
  NET— tales como interfaces, reglas de *firewall*, tablas de enrutamiento, etc.,
  los puntos de montaje del sistema de archivos -el *namespace* MNT*—, los
  recursos de comunicación entre procesos —el *namespace* IPC—, entre otros.

  Los *namespaces* son clave para las tecnologías de contenedores porque
  permiten aislar los recursos de un contenedor de los de los demás contenedores
  y de los del sistema operativo anfitrión.

<!-- cSpell:ignore jerárquicamente -->
<!-- https://dle.rae.es/jerárquicamente -->

* **Sistemas de archivos de unión o *union filesystems***. Los *union
  filesystems* son un tipo de sistema de archivos que crea una vista virtual
  unificada de múltiples sistemas de archivos subyacentes superpuestos en capas.
  Combinan múltiples directorios en una única vista unificada, mediante capas
  organizadas jerárquicamente: las capas superiores pueden ocultar o modificar
  archivos en las capas inferiores. Cuando se modifica un archivo en una capa de
  sólo lectura, primero se copia a una capa superior de escritura para realizar
  allí la modificación. Las aplicaciones acceden a los archivos sin necesidad de
  conocer la estructura de capas subyacente.

  Los *union filesystems* son clave para las tecnologías de contenedores porque
  permiten imágenes en capas inmutables con una capa superior de escritura,
  facilitan compartir capas base entre múltiples contenedores, permiten imágenes
  livianas y eficientes en almacenamiento, y posibilitan actualizaciones
  incrementales de las imágenes.

* **Grupos de control o *control groups* o *cgroups***. Los *cgroups* limitan,
  contabilizan y aíslan el uso de recursos de los grupos de procesos.
  Proporcionan un mecanismo para organizar jerárquicamente los procesos y
  distribuir los recursos del sistema entre ellos. Permiten restringir la
  cantidad de un recurso del sistema —procesador, memoria, red, etc.— que un
  grupo de procesos puede usar, controlar cómo se dividen los recursos entre los
  grupos que compiten, realizar un seguimiento del uso de recursos para generar
  informes y realizar monitoreo, gestionar los procesos colectivamente como
  grupos en lugar de individualmente y organizar los procesos en estructuras de
  árbol heredando las limitaciones.

  Los *cgroups* son clave para las tecnologías de contenedores porque
  proporcionan aislamiento y limitación de recursos, distribuyendo los recursos
  entre los contenedores y habilitando un rendimiento predecible entre varios
  contenedores huésped.

Estos mecanismos existen en Linux mucho antes de que se popularizara la
tecnología de contenedores, aunque hoy en día son fundamentales para su
funcionamiento.

### Motores de contenedores

<!-- cSpell:ignore containerd Kata Moby -->

Ejemplos de contenedores incluyen:

* [Docker](https://www.docker.com). Es el pionero y el más popular de los
  motores de contenedores.

* [Podman](https://podman.io). Es una alternativa sin *daemon* a Docker,
  compatible con la mayoría de los comandos de Docker y sin requerir privilegios
  de root.

* [containerd](https://containerd.io). Es el motor de contenedores que se utiliza
  como base para Docker, pero puede usarse de forma independiente. Funciona
  tanto en Linux como en Windows.

* [CRI-O](https://cri-o.io). Es desarrollado específicamente para
  [Kubernetes](https://kubernetes.io) como una implementación ligera del
  [Container Runtime
  Interface](https://kubernetes.io/docs/concepts/architecture/cri/).

* [LXC](https://linuxcontainers.org/lxc/introduction/)/[LXD](https://canonical.com/lxd).
  Son ambas plataformas de contenedores de Linux que ofrecen una experiencia
  similar a máquinas virtuales pero con la eficiencia de los contenedores.

* [OpenVz](https://openvz.org). Es una tecnología de virtualización a nivel de
  sistema operativo para Linux.

* [Singularity](https://sylabs.io/docs/). Popular en entornos de computación
científica y de alto rendimiento —HPC—.

* [Kata Containers](https://katacontainers.io). Combina la seguridad de las
  máquinas virtuales con la velocidad y eficiencia de los contenedores.

* [Windows
  Containers](https://learn.microsoft.com/en-us/virtualization/windowscontainers/).
  Es la tecnología que permite ejecutar aplicaciones Windows en contenedores
  cuando el sistema operativo anfitrión es Windows Server y no Linux como en la
  mayoría de los demás casos.

* [Mirantis Container
  Runtime](https://www.mirantis.com/software/mirantis-container-runtime/). Es la
  evolución de Docker Enterprise Edition. Funciona tanto en Linux como en
  Windows.

* [Moby](https://mobyproject.org). Es un *framework* para ensamblar sistemas de
  contenedores que también usa containerd como motor de ejecución de
  contenedores. Funciona tanto en Linux como en Windows.

### Contenedores versus máquinas virtuales

La tabla siguiente muestra algunas diferencias y similitudes entre los
contenedores y las máquinas virtuales:

<table >
  <tr>
    <th>Característica</th>
    <th style="width:50%;">Máquina virtual</th>
    <th style="width:50%;">Contenedor</th>
  </tr>
  <tr style="vertical-align: top;">
    <td>Arquitectura</td>
    <td>Cada máquina virtual ejecuta un sistema operativo completo, incluyendo
    el <i>kernel</i>. Cada máquina virtual corre sobre un hipervisor. Cada
    máquina virtual incluye su propio sistema operativo, bibliotecas y
    aplicaciones.</td>
    <td>Cada contenedor comparte el <i>kernel</i> con el sistema operativo
    anfitrión. El contenedor corre directamente sobre el sistema operativo
    anfitrión. Cada contenedor incluye sólo lo necesario: las dependencias y la
    aplicación.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Uso de recursos</td>
    <td>Consume más recursos —procesamiento, memoria, almacenamiento— porque
    cada máquina virtual está ejecutando un sistema operativo completo.</td>
    <td>Es más ligero porque todos los contenedores comparten el <i>kernel</i>
    del sistema operativo anfitrión.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Tiempo de inicio</td>
    <td>Iniciar una máquina virtual es más lento porque implica iniciar todo el
    sistema operativo.</td>
    <td>Iniciar un contenedor es már rápido porque el sistema operativo ya está
    iniciado.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Aislamiento</td>
    <td>Proporciona un aislamiento completo del sistema operativo anfitrión y de
    otras máquinas virtuales.</td>
    <td>Generalmente proporciona un aislamiento ligero del anfitrión y de otros
    contenedores, pero no ofrece una frontera de seguridad tan sólida como una
    máquina virtual.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Sistema operativo</td>
    <td>Ejecuta un sistema operativo completo, incluido el <i>kernel</i>, por
    lo que requiere más recursos —procesador, memoria y almacenamiento—.</td>
    <td>Ejecuta solo la parte en modo usuario del sistema operativo —y no el <i>kernel</i>—, y puede adaptarse para incluir únicamente los servicios
    necesarios para las aplicaciones, utilizando así menos recursos.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Compatibilidad de invitado con el anfitrión</td>
    <td>Ejecuta prácticamente cualquier sistema operativo dentro de la máquina virtual.</td>
    <td>Ejecuta la misma versión del sistema operativo que el anfitrión.
    Actualmente el sistema operativo puede ser solamente Linux, Windows o iOS.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Actualizaciones del sistema operativo</td>
    <td>Es necesario descargar e instalar las actualizaciones del sistema
    operativo en cada máquina virtual. Instalar una nueva versión del sistema
    operativo requiere una actualización o, a menudo, crear una nueva máquina
    virtual.</td>
    <td>Actualizar el sistema operativo dentro de un contenedor implica
    actualizar la versión base y reconstruir la imagen del contenedor con esta
    nueva imagen base</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Despliegue y portabilidad</td>
    <td>Se despliegan como archivos grandes, ya sean imágenes o
    <i>snapshots</i>; eso hace que sea práctico descargar imágenes de máquinas
    virtuales. Las imágenes creadas para un hipervisor no son portables a otro
    hipervisor de otro proveedor.</td>
    <td>Las imágenes de los contenedores son más fáciles de empaquetar,
    distribuir y desplegar; esto hace que sea posible tener repositorios de
    imágenes de contenedores desde las cuales descargar las imágenes cada vez
    que sea necesario. Las imágenes creadas compatibles con la
    <a href="https://opencontainers.org">Open Container Initiative</a> son
    portables entre motores de contenedores que soporten ese estándar.</td>
  </tr>
  <tr style="vertical-align: top;">
    <td>Persistencia</td>
    <td>Las máquinas virtuales persisten luego de la terminación de los
    servicios que ejecutan en ella; el re-inicio de una máquina virtual parte
    del estado inmediato anterior.</td>
    <td>Los contenedores no persisten cuando terminan los servicios que los
    ejecutan; cada inicio de un contenedor es un inicio "fresco".</td>
  </tr>
</table>
