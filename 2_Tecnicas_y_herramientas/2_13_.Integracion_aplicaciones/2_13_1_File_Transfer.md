# 2 Técnicas y herramientas

## 2.13 Integración de aplicaciones

### 2.13.1 *File Transfer* o transferencia de archivos

La transferencia de archivos es un mecanismo que permite [integrar
aplicaciones](./2_13_.Integracion_aplicaciones.md) que fueron construidas
independientemente, en lenguajes diferentes, en entornos diferentes[^1].

[^1]: Hohpe, G. & Woolf, B. (2003). Enterprise Integration Patterns: Designing,
Building, and Deploying Messaging Solutions. Addison-Wesley Professional.

> [!TIP]
> Además de consultar [^1] puedes ver el resumen de este estilo de integración
> que está disponible en línea
> [aquí](https://www.enterpriseintegrationpatterns.com/patterns/messaging/FileTransferIntegration.html).

Aunque idealmente nos imaginamos que el software de una organización es un
conjunto de piezas cohesivas diseñadas para funcionar de forma unificada y
coherente, la realidad con la que nos vamos a encontrar es diferente:

* Las organizaciones compran —o consumen en la modalidad de
  *software-as-a-service* en la nube— diferentes paquetes de software
  [COTS](https://en.wikipedia.org/wiki/Commercial_off-the-shelf) —*commercially
  off-the-shelf*— de proveedores diferentes.

* También las organizaciones van construyendo aplicaciones en diferentes
  momentos: mientras los nuevos desarrollos pueden usar tecnologías más nuevas
  —y está bien—, los existentes van a usar tecnologías obsoletas —y no siempre
  es bueno reemplazarlos[^2]—.

[^2]: Por un lado está el costo de hacer algo de nuevo y por otro la máxima ≪lo
    que funciona no se toca≫.

* Aunque las organizaciones construyan varias aplicaciones al mismo tiempo, los
  equipos que las construyen —que pueden tener experiencias y preferencias
  diferentes— pueden optar por usar diferentes enfoques.

* Terminar una aplicación que funciona y se adopta puede generar más valor a la
  organización que integrarla con aplicaciones existentes, sobre todo cuando la
  integración no agrega ningún valor a la nueva aplicación —ni al negocio—.

<!-- cSpell:ignore compartición https://dle.rae.es/compartición -->

Como resultado, cualquier organización —independientemente de su tamaño— va a
tener que lidiar con la compartición de información entre aplicaciones. Vincular
tales aplicaciones requiere una comprensión técnica y del negocio —y el esfuerzo
asociado— que puede no valer la pena si lo único que se requiere es transferir
datos de una aplicación a otra.

Los archivos son un mecanismo de almacenamiento universal, soportados por
cualquier sistema operativo y manejables desde cualquier lenguaje de
programación[^3]. El mecanismo más simple para integrar aplicaciones es mediante
la transferencia de archivos.

[^3]: En la medida que el archivo tenga un formato que las aplicaciones
    comprendan, como veremos más adelante.

> Para integrar aplicaciones cada aplicación produce archivos que contienen la
> información que las demás aplicaciones deben consumir. Los integradores asumen
> la responsabilidad de transformar los archivos en diferentes formatos. Puede
> ser necesario producir los archivos a intervalos regulares de acuerdo con la
> naturaleza del negocio.

<span id="figura-1"/>

![Integración de aplicaciones mediante transferencia de archivos](/diagrams/File_Transfer.svg)

*Figura 1: Integración de aplicaciones mediante transferencia de archivos*.
Tomado de [^1].

Una decisión importante en este caso es el formato de los archivos. A lo largo
del tiempo han surgido estándares como
[CSV](https://en.wikipedia.org/wiki/Comma-separated_values) —*comma-separated
values*—, [XML](https://en.wikipedia.org/wiki/XML) —*extensible markup
language*— o [JSON](https://en.wikipedia.org/wiki/JSON) —JavaScript object
notation—, entre otros.

Una consecuencia de esta forma de integración es que los desarrolladores de la
aplicación que consume el archivo no precisan conocer detalles de la aplicación
que los produce. Aunque el formato y el contenido del archivo podrían ser
negociados entre los desarrolladores de las aplicaciones a integrar, esto no
siempre es posible, especialmente cuando la aplicación que produce el archivo es
un paquete COTS.

En estos casos, el archivo con su formato se convierte en una
[interfaz](/4_Conceptos/4_Interfaz.md) pública.

Otro tema importante es cada cuanto producir y consumir estos archivos.
Típicamente esto se sincroniza con los ciclos del negocio: diariamente
—típicamente durante la noche, cuando el negocio está cerrado al público— para
las operaciones del día, mensualmente para los cierres del mes, por ejemplo.

<!-- cSpell:ignore removibles https://dle.rae.es/removible -->

Otra cuestión es cómo hacer llegar el archivo desde la aplicación que los
produce a la que los consume. Ubicaciones de red compartidas, dispositivos de
almacenamiento removibles, correo electrónico, entre otras, son formas válidas
de transmitir los archivos.

Esta forma de integrar aplicaciones es simple, pero los desarrolladores deben
realizar cierto trabajo manual: ponerse de acuerdo en la convención de nombres
de los archivos —por ejemplo, para representar diferentes conjuntos de datos, o
diferentes días del mes del mismo conjunto de datos—, la ubicación de los
archivos en el medio de transferencia, bloquear los archivos mientras se
procesan, borrar los archivos ya importados, etc.

Otro problema es que las actualizaciones de datos demoran tanto como la
frecuencia con la que ocurre la integración: en algunos casos no hay problema
—muchos negocios realizan actualizaciones de datos en lotes —*batch*— durante la
noche, para sincronizar los datos que cambiaron durante el día—, pero en otros
puede ser necesario que la actualización sea inmediata. En este último caso la
integración mediante transferencia de archivos puede no ser el mecanismo más
adecuado —otros mecanismos como [mensajería](./2_13_4_Messaging.md), [bases de
datos compartidas](./2_13_2_Shared_Database.md), o [RPC](./2_13_3_RPC.md) pueden
ser más apropiados—.
