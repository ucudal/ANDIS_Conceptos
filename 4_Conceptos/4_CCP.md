# 4 Conceptos

## CCP o *Common Closure Principle*

El principio de cierre común, o CCP por sus siglas en inglés, es el equivalente
al principio [SRP](https://github.com/ucudal/PII_Guias/blob/main/SRP.md) para
componentes, y dice[^1][^2]:

> Agrupa en componentes aquellas clases —y otros tipos de datos— que cambian por
> las mismas razones y al mismo tiempo. Separa en componentes diferentes
> aquellas clases que cambian en momentos diferentes y por razones diferentes.

[^1]: Martin, R. C. (1997). Granularity. The C++ Report. Recuperado de Object
    Mentor [aquí](http://www.objectmentor.com/resources/articles/granularity.pdf).

[^2]: Martin, R. C. (2018). Clean architecture: A craftsman’s guide to software
    structure and design. Pearson.

Dicho de otra forma, un componente no debería tener múltiples razones para
cambiar —por eso el CCP es equivalente al SRP para componentes—.

Cuando dos o más clases están relacionados de forma tal que cuando hay cambios
en una también hay cambios en las demás, que sean parte del mismo componente
facilita el proceso de liberación y despliegue, y reduce el riesgo de versiones
inconsistentes entre artefactos que evolucionan en conjunto.

> [!TIP]
> Mira especialmente el [diagrama de tensión](./4_CRP.md#diagrama-de-tensión)
> para los principios relacionados con cohesión: [REP](./4_REP.md), CCP y
> [CRP](./4_CRP.md).
