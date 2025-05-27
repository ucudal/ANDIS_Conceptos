# 2 Técnicas y herramientas

## 2.13 Integración de aplicaciones

## 2.13.3  *Remote Procedure Invocation* o invocación de procedimiento remoto

La invocación de procedimientos remotos es un mecanismo que permite [integrar
aplicaciones](./2_13_.Integracion_aplicaciones.md) que fueron construidas
independientemente, en lenguajes diferentes, en plataformas diferentes[^1].

<!-- cSpell:ignore Hohpe -->

[^1]: Hohpe, G. & Woolf, B. (2003). Enterprise Integration Patterns: Designing,
Building, and Deploying Messaging Solutions. Addison-Wesley Professional.

> [!NOTE]
> La invocación de procedimientos remotos definida en [^1] es también llamada
> [RPC](/4_Conceptos/4_RPC.md) en otros contextos. Preferimos usar invocación de
> procedimientos remotos cuando hablamos de un mecanismo de integración de
> aplicaciones siguiendo la terminología de [^1] y usar RPC en los demás
> casos.

Los mecanismos de transferencia de datos tales como [File
Transfer](./2_13_1_File_Transfer.md) y [Shared
Database](./2_13_2_Shared_Database.md) permiten compartir datos entre
aplicaciones; compartir datos es importante pero no es suficiente para integrar
aplicaciones: [Shared Database](./2_13_2_Shared_Database.md) rompe el
[encapsulamiento](/4_Conceptos/4_Encapsulamiento.md) y aunque [File
Transfer](./2_13_1_File_Transfer.md) no lo hace, las actualizaciones no son
inmediatas.

Lo que se necesita es un mecanismo para que una aplicación invoque
una función en otra aplicación, pasando los datos que necesitan ser compartidos,
e indicándole a la aplicación receptora cómo procesar esos datos.

> Para integrar aplicaciones desarrolla cada aplicación como un [componente](/4_Conceptos/4_Componente.md)
> a gran escala con datos encapsulados. Proporciona una
> [interfaz](/4_Conceptos/4_Interfaz.md) para permitir que otras aplicaciones
> interactúen con la aplicación en ejecución.

<span id="figura-1"/>

![Integración de aplicaciones mediante invocación a procedimiento remoto](/diagrams/Remote_Procedure_Invocation.svg)

*Figura 1: Integración de aplicaciones mediante invocación a procedimiento remoto*.
Tomado de [^1].

> [!TIP]
> Consulta el documento sobre [RPC](/4_Conceptos/4_RPC.md) para conocer cómo
> funciona el mecanismo mostrado en la [Figura 1](#figura-1).

La invocación de procedimiento remoto usa encapsulamiento para la integración de
aplicaciones: cada aplicación mantiene control sobre sus propios datos y otras
aplicaciones acceden o modifican esos datos solo a través de llamadas remotas.
Esto preserva la integridad de datos y permite que cada aplicación cambie su
estructura interna independientemente.

> [!WARNING]
> La invocación de procedimientos remotos es simple para los desarrolladores que
> ya están acostumbrados a usar llamadas a procedimientos y las tecnologías con
> las que se implementa hacen bastante transparente su uso.
>
> Esto no es una ventana sino un problema, porque hay enormes diferencias en
> términos de [desempeño](/4_Conceptos/4_Rendimiento.md) y
> [confiabilidad](/4_Conceptos/4_Disponibilidad.md) entre invocaciones locales y
> remotas. Cuando estas diferencias no son tenidas en cuenta, el uso puede
> conducir a sistemas lentos y poco confiables.
