# 4 Conceptos

## CRP o *Common Reuse Principle*

El principio de reutilización común, o CRP por sus siglas en inglés, dice [^1][^2]:

[^1]: Martin, R. C. (1997). Granularity. The C++ Report. Recuperado de Object
    Mentor [aquí](http://objectmentor.com/resources/articles/granularity.pdf).

[^2]: Martin, R. C. (2018). Clean architecture: A craftsman’s guide to software
    structure and design. Pearson.

> No forzar a los usuarios de un componente a depender de cosas que no
> necesitan[^2]. Las clases —y otros tipos de datos— en un componente se
> reutilizan juntos. Cuando se reutiliza una clase en un componente, se
> reutilizan todas[^1][^3].

[^3]: En la definición original en [^1] se usa ≪paquete≫ en lugar de
    ≪componente≫; en este y otros principios de Martin usamos ≪componente≫ como
    unidad de liberación, que en este contexto es equivalente a ≪paquete≫.

Dicho de otra forma, cuando se decide usar una clase —u otro tipo de dato—
liberada como parte de un componente en una aplicación, se termina incorporando
todas las clases de ese componente, ya sea que las use o no; y cambios en clases
de ese componente, aunque no se usen, implican una nueva liberación de ese
componente, lo que a su vez puede llevar a que el desarrollador deba evaluar si
actualiza a la nueva versión del componente o no.

<!-- cspell:ignore iteradores -->
Por lo tanto, un componente debería incluir clases que se reutilicen juntas —por
ejemplo, clases como `Order`, `OrderItem` y `OrderRepository` típicamente se
utilizan al mismo tiempo, por lo que deberían ser parte del mismo componente—.
Es esperable que las clases en un componente tengan muchas dependencias entre
ellas —siguiendo con el ejemplo `Order` está compuesta de `OrderItem` y está
contenida y es gestionada por `OrderRepository`—.

El principio también da a entender qué clases no deberían ser parte del mismo
componente: las que no se reutilicen simultáneamente.

De alguna manera, el CRP es equivalente al
[ISP](https://github.com/ucudal/PII_Guias/blob/main/ISP.md), pero para
componentes; ambos dicen algo así como "no dependas de cosas que no uses".

### Diagrama de tensión

Los principios [REP](./4_REP.md), [CCP](./4_CCP.md) y este CRP entran en
tensión, porque las decisiones de diseño para maximizar uno de ellos no van a
lograr maximizar los otros dos. Esto ocurre porque mientras REP y CCP tienden a
hacer los componentes más grandes —con más clases—, CRP tiende a hacerlos más
pequeños —con menos clases—:

* REP tiende a agrandar los componentes, porque lleva a incluir dentro del mismo
  artefacto todas las clases que forman parte de una ≪unidad de reutilización≫
  razonable.

* CCP también tiende a agrandar componentes, porque si dos grupos de clases
  cambian siempre juntas, es natural “fusionar” sus componentes para cerrar esos
  cambios en un solo lugar.

* CRP tiende a achicar los componentes, porque promueve la separación de las
  clases para que las dependencias sean más finas y específicas.

Dicho de otra forma, REP y CCP agrupan clases para que se reutilicen juntas
—REP— y cambien juntas —CCP—, mientras que CRP las separa para no forzar
dependencias innecesarias.

Esto se puede ilustrar en el diagrama en la [Figura 1](#figura-1), a
continuación:

<span id="figura-1"/>

![Diagrama de tensión para los principios de
cohesión](/diagrams/Tension_Diagram.svg)

*Figura 1: Diagrama de tensión para los principios de cohesión.*

Siguiendo este diagrama, cuando el foco está en REP y CRP, habrá muchos
componentes impactados cuando se hagan cambios simples; por el contrario, cuando
el foco está en CCP y REP, se tiende a tener pocos componentes grandes, lo que
puede causar muchas liberaciones innecesarias.

* Foco en REP y CRP: lleva a que cada clase reutilizable tenga su propio
  componente —según REP— y que ninguna clase dentro de un componente dependa de
  nada que no use —según CRP—, lo que fuerza a dividir componentes
  o separar clases en componentes diferentes. Esto resulta en muchos componentes
  pequeños y muy puros en términos de dependencias. Pero cuando hay un cambio en
  una funcionalidad del negocio simple, ese cambio puede estar repartido en
  clases en múltiples componentes, lo que implica liberar y volver a desplegar
  eventualmente varios componentes —se viola CCP—. Dicho de otra forma, la
  obsesión por reutilizar bien y evitar dependencias innecesarias terminó
  sacrificando la facilidad de desarrollo porque aumenta el costo de hacer
  cambios.

* Foco en CCP y REP: tiende a agrupar todas las clases que parecen cambiar
  juntas dentro de un mismo componente —según CCP— y ese componente termina
  siendo un componente grande que se volvió la unidad típica que todos usan tal
  cual viene —según REP—. El resultado son pocos componentes, pero grandes, que
  cierran bien los motivos de cambio y que se reutilizan como módulos "gordos".
  El problema es que esos componentes "gordos" terminan teniendo clases que
  otros componentes ni siquiera utilizan —se viola CRP—. Dicho de otra forma,
  termina habiendo demasiadas versiones nuevas de componentes, con poco impacto
  real para muchos consumidores, simplemente porque el grano de versionado es
  demasiado grueso.

La posición en el diagrama debe atender las preocupaciones actuales de los
desarrolladores, sabiendo que pueden cambiar con el tiempo. Por ejemplo, al
inicio de un proyecto, el CCP importa más que el REP, porque la capacidad de
desarrollar es más prioritaria que la de reutilizar.
