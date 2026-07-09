# 4 Conceptos

## ADP o *Acyclic Dependencies Principle*

Una consecuencia de usar componentes[^1] para desarrollar una aplicación es que
cada componente puede ser desarrollado independientemente de los demás, incluso
por desarrolladores o equipos de desarrollo diferentes. Cuando alguien libera
una nueva versión de un componente, los que desarrollan otros componentes que
dependen de ese pueden decidir si utilizan la nueva versión o no. Esto previene
que los cambios en un componente afecten negativamente a los componentes de los
demás desarrolladores o equipos de desarrollo.

[^1]: En esta definición, ≪componente≫ significa ≪unidad de despliegue≫, por
    ejemplo, una DLL, un JAR, etc.; comparar con esta otra definición de
    [componente](./4_Componente.md).

Para que esto funcione, es necesario gestionar la estructura de las dependencias
entre componentes: no puede haber ciclos; si los hay, cambios en un componente sí
pueden afectar a los otros que dependen de él.

El principio dice[^2][^3]:

[^2]: Martin, R. C. (1997). Stability. The C++ Report. Recuperado de Object
    Mentor [aquí](https://objectmentor.com/resources/articles/stability.pdf).

[^3]: Martin, R. C. (2018). Clean architecture: A craftsman’s guide to software
    structure and design. Pearson.

> No debe haber ciclos en el grafo de dependencias de componentes.

Vean el diagrama de componentes en la [Figura 1](#figura-1), a continuación.
Noten que es un grafo en el que los nodos son componentes y los arcos son
las dependencias entre componentes; este grafo es dirigido, porque las
dependencias tienen un sentido, `Database` depende de `Entities`, y no al revés.

<span id="figura-1"/>

![Un diagrama de componentes con sus dependencias](https://www.plantuml.com/plantuml/png/TL9DQy904BtFhnZeMUgffo3694AWGYZ5I_2mDKDTN7TbTgJOud_lkXF5Gxk7xFkOURo5pACObjF1GH7bx6W6cCvR288_6Iez-Q4Ax8bnUbSNPhl_PBLSO7ndu-FHC7cvpv2ZG-8FMOZBu4KtdgRJbwPSFdYBm0FnV-whzVItTm7z5i_ZAo3khKzbp05TsfBpaV0OtFbA02HyakpIQxHNlpBMRz14N2clKaKEpX5djL9rRUahypLSGANM2x7PIk2OdLRbZYdIrLArKxKyoIwm_HvJIu2-Dc8-JAGirD0tNgnOqhK6O8r5CKcjLZYPpLAFT5z1TmDj1XcMDwrEM-DKXphKvfWQQZMQ98oWlENeI0KDJlgT7GRo6qs5EVdX-eFy0W00)

*Figura 1: Un diagrama de componentes con sus dependencias.* Tomado de [^3]

<!-- cSpell:ignore acíclico -->

Noten una cosa más: el grafo es acíclico, es decir, no tiene ciclos: no importa
por qué componente comiencen a recorrer el grafo, nunca vuelven a ese
componente.

Siguiendo este diagrama es posible determinar que una nueva versión de
`Presenter`, por ejemplo, afecta a `View` y a `Main` —hay que seguir las
flechas de las dependencias en sentido contrario—. Los desarrolladores de `View`
y `Main` pueden decidir si, y cuándo, integran la nueva versión en una nueva
versión de `Presenter`[^4].

[^4]: Esto es posible en la medida que dos versiones diferentes de `Presenter`
    puedan ser desplegadas y coexistir. Por ejemplo, si se pasa de la versión
    `2.0` de `Presenter` a la versión `2.1`, `Main` se puede actualizar
    independientemente de `View` en la medida que `Main` pueda depender de la
    versión `2.1` y `View` de la versión `2.0`; por eso es necesario que ambas
    versiones de `Presenter` puedan ser desplegadas y que puedan coexistir.

El diagrama también permite determinar que liberar una nueva versión de `Main`
no tiene ningún efecto en otro componente, porque ninguno depende de él.

Vean ahora el efecto de introducir un ciclo. El diagrama en la [Figura
2](#figura-2), a continuación, muestra una situación en la que `Entities` pasa a
depender de `Authorizer` —una clase `User` en `Entities` referencia a una clase
`Permission` en `Authorizer`, por ejemplo—.

<span id="figura-2"/>

![Un ciclo de dependencias](https://www.plantuml.com/plantuml/png/TL9DQy904BtFhnZmBFNKKn1Z4Y5G8PJY9NZOca63wwxCZXHR_E_Tx4JnqEuX-pvc7cyXYo26vNAoa0MvMfe3nlFklU1FWaelhYiyEsASFTIbsHtth9RrZ1ziN3WR9YUF6R9qYlmf2t7bdUZ6P3PxhVBLaxVqt17_vxxrZlxsRg3Vx6Ly1OHZxs8PSq8Rj-Hw9ZnxUnq8WFWzoI6-HdkrQzExBPg0Q-L5hCZUMkAa5gfkUlfAV0CtKAbsGcnsuZaafrQvOGeqMAesgkONENZklyVK7A0jZPXF4oW99RILarvwqhKAO8DPDesjrZYTpsEFU0-WkOCwWGJpkrR6hN6gGHsgKqm9fHfL54QGttDqf80Af-s4gTjg9Yp8TSFlyGi0)

*Figura 2: Un ciclo de dependencias.* Tomado de [^3]

<!-- cSpell:ignore Interactors -->

Ahora hay varios ciclos; por ejemplo, `Entities` depende de `Authorizer`, éste
de `Interactors`, éste de `Entities`, éste de `Authorizer` y así
indefinidamente. Una nueva versión del componente `Database` requiere que sea
compatible con `Entities`, pero con el ciclo, también debe ser compatible con
`Authorizer`, que a su vez debe ser compatible con `Interactors`. Esto hace que
`Database` sea mucho más difícil de cambiar. En los hechos, `Entities`,
`Authorizer` e `Interactors` pasaron a ser una gran ≪unidad de despliegue≫:
cuando algo cambie en cualquiera de ellos, es necesario liberar una nueva
versión de todos ellos.

Noten, además, que mientras antes era posible probar `Entities` de forma
independiente del resto de los componentes, ahora es necesario hacer un
[*stub*](https://martinfowler.com/articles/mocksArentStubs.html) de
`Authorizer` o incluirlo en la misma prueba, aumentando el acoplamiento del
entorno de testing.

### Cómo romper ciclos

Hay dos formas de romper estos ciclos:

1. Mediante el principio de inversión de dependencias, o
   [DIP](https://github.com/ucudal/PII_Guias/blob/main/DIP.md). Siguiendo con el
   ejemplo, `Entities` define una interfaz `IPermission`, que se implementa en
   la clase `Permission` de `Authorizer`. Esto cambia la dirección de la flecha
   que va de `Entities` a `Authorizer` —en rojo en el diagrama de la [Figura
   2](#figura-2)—, para que ahora vaya de `Authorizer` a `Entities`, rompiendo
   el ciclo.

2. Crear un nuevo componente `Permissions` que tenga la clase `Permission` y que
   tanto `Entities` como `Authorizer` dependan de él, rompiendo también el
   ciclo.
