# 4 Conceptos

## Teorema CAP

Las aplicaciones modernas a escala de Internet deben afrontar altas expectativas
de [disponibilidad](./4_Disponibilidad.md) y [rendimiento](./4_Rendimiento.md)
antes cargas de usuarios en crecimiento exponencial. Estas aplicaciones se
supone que se proporcionan alta disponibilidad a través de redundancia ‑por
ejemplo, replicación de datos‑; los datos se consideran altamente disponibles si
un consumidor determinado de los datos siempre puede acceder a alguna réplica.
La escala de estas aplicaciones está poniendo de manifiesto claramente el
equilibrio entre consistencia y disponibilidad[^1].

[^1]: Fox, A; Brewer, E. (1999). Harvest, Yield and Scalable Tolerant Systems.
    Proc. 7th Workshop Hot Topics in Operating Systems, IEEE CS. Disponible
    [aquí](https://s3.amazonaws.com/systemsandpapers/papers/FOX_Brewer_99-Harvest_Yield_and_Scalable_Tolerant_Systems.pdf).

En este contexto, la consistencia fuerte significa consistencia
[ACID](./4_Acoplamiento.md) de copia única; la alta disponibilidad se
proporciona a través de la redundancia; la resiliencia a la partición significa
que el sistema en su totalidad puede sobrevivir a una partición entre réplicas
de datos[^1][^3].

[^3]: Vogels, W. (2009). Eventually Consistent. Communications of the ACM,
    January 2009, 52(1). Disponible
    [aquí](https://dl.acm.org/doi/pdf/10.1145/1435417.1435432).

Una partición ocurre cuando un conjunto de réplicas no puede acceder a otro
conjunto de réplicas ‑lo que implica que los datos redundantes en las réplicas
no pueden ser sincronizados‑, pero ambos conjuntos son accesibles por un grupo
de clientes.

CAP es un [acrónimo](https://dle.rae.es/acrónimo) que establece compromisos
entre estas tres propiedades: **c**onsistencia fuerte, alta disponibilidad
‑***a**vailability* en inglés‑, y resistencia a la **p**artición de la red. El
principio CAP fuerte establece que entre consistencia fuerte, alta
disponibilidad y resiliencia a la partición sólo es posible cumplir a la vez dos
como máximo, nunca los tres. Para demostrar el principio ‑de ahí que algunos lo
llamen teorema CAP‑ es posible considerar todas las combinaciones posibles de
forma exhaustiva[^1]:

* CA sin P: Las bases de datos que proporcionan semántica transaccional
  distribuida solo pueden hacerlo en ausencia de una partición de red que separe
  la réplicas.

* CP sin A: En caso de una partición, las transacciones posteriores a una base
  de datos ACID pueden bloquearse hasta que la partición se recupere, para
  evitar el riesgo de introducir conflictos de sincronización ‑y por lo tanto
  inconsistencia‑.

* AP sin C: El almacenamiento en caché web HTTP proporciona resiliencia de
  partición cliente-servidor al replicar documentos, pero una partición
  cliente-servidor impide la verificación de la frescura de una réplica vencida.
  En general, cualquier problema de base de datos distribuida puede resolverse
  con un almacenamiento en caché basado en la expiración para obtener AP, o
  réplicas y votación mayoritaria para obtener PC ‑la minoría no está
  disponible‑.

La noción de “dos de tres” en el teorema CAP ha sido criticada por simplificar
en exceso la relación entre consistencia, disponibilidad y tolerancia a
particiones. En realidad, las tensiones entre estas propiedades son más
complejas y matizadas. Si bien CAP señala que no se puede garantizar al mismo
tiempo consistencia y disponibilidad perfectas durante una partición, estas
situaciones son poco comunes. Los arquitectos deben seguir eligiendo entre
consistencia y disponibilidad cuando ocurren particiones, pero tienen mucha
flexibilidad en la forma de gestionar y recuperarse de ellas. El enfoque actual
se centra en maximizar las combinaciones más adecuadas para cada aplicación
específica, incorporando tanto estrategias para operar durante una partición
como para restaurar el sistema después de superarla. Esta perspectiva amplía el
entendimiento del teorema CAP, superando las limitaciones que tradicionalmente
se le atribuían[^2].

[^2]: Brewer, E. (2012). CAP Twelve Years Later: How "Rules" Have Changed. IEEE
    Computer, vol. 45, no. 2, pp. 23-29, Feb. 2012. Disponible
    [aquí](https://ieeexplore-ieee-org.proxy.timbo.org.uy/document/6133253) vía
    Timbó.

### CAP, ACID, BASE

En la práctica la tolerancia a particiones de la red en un sistema distribuido
no suele ser negociable: las fallas y las divisiones de la red son inevitables
‑y suponer lo contrario es caer en las [falacias de la computación
distribuida](./4_Falacias_computacion_distribuida.md)‑.

Por lo tanto, los arquitectos deben encontrar un equilibrio entre la
disponibilidad y la consistencia, según sus prioridades. Los sistemas que
priorizan la disponibilidad sobre la consistencia suelen utilizar modelos de
consistencia eventual, comunes en el paradigma [BASE](./4_BASE.md), mientras que
los sistemas que requieren una consistencia sólida se adhieren a los principios
[ACID](./4_ACID.md).
