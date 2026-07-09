# 4 Conceptos

## SDP o *Stable Dependencies Principle*

El concepto de estabilidad fue introducido por Robert C. Martin en el principio
de dependencias estables o SDP por sus siglas en inglés[^1][^2].

[^1]: Martin, R. C. (1997). Stability. The C++ Report. Recuperado de Object
    Mentor [aquí](https://objectmentor.com/resources/articles/stability.pdf).

[^2]: Martin, R. C. (2018). Clean architecture: A craftsman’s guide to software
    structure and design. Pearson.

El principio dice:

> Las dependencias entre componentes en un diseño deben dirigirse en el sentido
> de la estabilidad de los componentes. Un componente solo debe depender de
> componentes que sean más estables que él[^3].

[^3]: En esta definición, ≪componente≫ significa ≪unidad de despliegue≫, por
    ejemplo, una DLL, un JAR, etc.; comparar con esta otra definición de
    [componente](./4_Componente.md).

Para entender el principio, necesitamos definir algunos conceptos primero:

* **Componente inestable**. Es un componente que se puede cambiar fácilmente, o
  que no hay razones para impedir cambios, por lo que es esperable que cambie
  con frecuencia; esto sucede cuando ningún otro componente depende de él: si lo
  cambiamos, ningún otro componente se verá afectado.

* **Componente estable**. Es un componente que es difícil de cambiar, o que hay
  razones para que el componente no cambie, por lo que se espera que cambia
  poco; esto sucede cuando varios componentes dependen de él: si lo cambiamos,
  se verán afectados esos otros componentes.

Con estas definiciones, podemos parafrasear el principio diciendo que cuando un
componente es inestable puede depender de otro que sea más estable, pero no al
revés. De lo contrario, cambios en un componente inestable podrían obligar a
modificar componentes que deberían permanecer estables.

Analicemos el principio con un ejemplo. En el siguiente diagrama de la [Figura
1](#figura-1), el componente `X` es un componente estable. Los componentes `A`,
`B` y `C` dependen de `X`, por lo que `X` tiene tres razones para no cambiar,
decimos que `X` es ≪responsable≫ por `A`, `B` y `C`. Por otro lado, `X` no
depende de ningún otro componente que pueda obligarlo a cambiar, decimos que es
≪independiente≫.

<span id="figura-1"/>

![Un componente estable](https://www.plantuml.com/plantuml/png/TP2n3i8W48Ptdk9Izzh9gMaAn4vEng4hQOanKguvw62Cxow2RHYKuVBVztDtkMkTL-INoJ1ME_ymkc4GtXdHmpFAb2vsb4XM4rGR5MguNobP1WakfAoR5Mdhjp_Qw2daMI-03grF5RkgEXnvbta2QTJqpptThFxjlLYAzVwx1Hjmcj5-PXUy0EM0vqX4978a8v8vwYFg6OUoR9eWn2haAbYhxHZkzmO0)

*Figura 1: Un componente estable.* Adaptado de [^2]

Vean ahora este otro diagrama de la [Figura 2](#figura-2),  a continuación. El
componente `Y` es un componente muy inestable. Como ningún otro componente
depende de `Y`, decimos que es ≪irresponsable≫. Pero `Y` depende de los
componentes `D`, `E` y `F`, por lo que `Y` tiene tres posibles orígenes externos
de cambios: cambios en cualquiera de estos componentes podrían hacer que `Y`
cambie. Decimos que `Y` es ≪dependiente≫.

<span id="figura-2"/>

![Un componente estable](https://www.plantuml.com/plantuml/png/TP0n3u8m48Nt_eeBxiZaH0WKON8o3ZWsS356k99h6OpnlrifaYPgXykxxxrhSysDLModeHSYDVRUOoR0dQFM5XwpzEr4NQcPa25PgLJjxSBUwZN3YHMPKJ6INJFOu-3wu2w0MfFr4viasLL57NXISuVypprS2NzxJ-5hkbss4AqUHatljwDp1Cf04wBzZ8eGLJEItwbID137MURYYv0VKGgH8tNk_ru0)

*Figura 2: Un componente estable.* Adaptado de [^2]

Una forma de medir la estabilidad de un componente es contar las referencias que
entran y que salen del componente:

* **Fan-in** o [**acoplamiento aferente**](./4_Acoplamiento.md): dependencias
  entrantes. Es el número de clases —y otros tipos de datos- fuera del
  componente que dependen de clases dentro del componente.

* **Fan-out** o [**acoplamiento eferente**](./4_Acoplamiento.md): dependencias
  salientes. Es el número de clases —y otros tipos de datos— dentro del
  componente que dependen de clases fuera del componente.

* **Instability**: $I = \frac{\text{Fan-out}}{\text{Fan-in} + \text{Fan-out}}$[^4].
  Varía entre 0 y 1. La inestabilidad es mínima -$I = 0$-, es decir, el
  componente tiene muchos motivos para no cambiar, cuando otros componentes
  dependen de él -$Fan-in > 0$-, pero él no depende de ningún otro -$Fan-out =
  0$-; en ese caso componente es independiente. La inestabilidad es máxima —$I =
  1$—, es decir, el componente no tiene razones para que no pueda cambiar,
  cuando ningún otro componente depende de él -$Fan-in = 0$-, pero él depende de
  otros componentes -$Fan-out > 0$-; en este caso el componente es irresponsable
  y dependiente.

[^4]: La fórmula de $I$ no está definida para $Fan-in = 0$ y $F$an-out = 0$
    —división por cero—. A efectos prácticos, suele considerarse un componente
    “aislado” o “trivial”; es un caso de borde que normalmente se ignora o se
    trata aparte.

El principio de dependencias estables dice que la métrica $I$ de un componente
debe ser mayor que la de los componentes de los que depende; dicho de otra
forma, la métrica $I$ decrece en la dirección de la dependencia.

<span id="figura-3"/>

![Configuración ideal de una aplicación con tres componentes](https://www.plantuml.com/plantuml/png/XP0z3u9038Rt-nKDxdWkJaZW32GaJiR1mUM4nXYF7Yd7O8p_tHCK6JHsQDxswKVQf7MQNLSR8QBMNGt60hnjhNLmw-KGTbIjBHCoo36hT7avyO2CPTYnfhRHZEJ66ZHO-tWo2o2tv8QEcPJBBCqdJ5cka7_HpPdmExkBmKVprnMYj7LZwRaxA0ZzcKU31ofMYm1q2-aVhgOy-r3PqxqGAOHX77kbta8aI9N_v0C0)

*Figura 3: Configuración ideal de una aplicación con tres componentes.* Adaptado
de [^2]

El diagrama anterior muestra una situación ideal: los componentes inestables
dependen de un componente estable. Ahora bien, supongan que un nuevo componente
`Flexible` ha sido diseñado para ser fácil de modificar, es decir, para que sea
inestable. Por alguna razón, en el componente `Estable` se agrega una referencia
a `Flexible`. Esto viola el principio de dependencias estables porque
necesariamente la métrica de inestabilidad de `Flexible` es mayor que la de
`Estable` que es cero; como consecuencia, `Flexible` ya no sería tan fácil de
modificar.

<span id="figura-4"/>

![Violación al SDP](https://www.plantuml.com/plantuml/png/XT2z2i8m403WFKznsBtMnKcBhHWeE8c3e0xH7YAcbt99GH7VtTZuqq4nGxZBTvTmcLYds3ML5c9atKLZAi2lXJ4EhcqOqeRAgM52XkHzcglzwS21j65OiY9RAqPoxnhKMFcySnU0DEH2HvGamracEvORBf5_wVn8-Drk8koZ_dCAiJTLRUZnTgyWz6FkD6we60zwe2naVppl-koZIQkhhagDvwFdLgGG6SHnclgQ_1Mi85v7ZENsaVgA2LBfl_mE)

*Figura 4: Violación al SDP.* Adaptado de [^2]

Para resolver el problema, se utiliza el principio de inversión de dependencias.
Supongan que la dependencia de `Estable` a `Flexible` se genera por una
dependencia entre una clase `Consumer` en `Estable` y una clase `Provider` en
`Flexible`, tal como se muestra en el diagrama a continuación.

<span id="figura-5"/>

![Una clase Consumer en Estable usa Provider en Flexible](https://www.plantuml.com/plantuml/png/TP71IWCn48RlynJ3zgvxybINsgKBWWSH2u9wIBD33IOpooIhBT9tDpQbhA0vXCp_vvlCJ1On6KrZy03pcFQU6i2y7aGIVXsF9HovRqMP5EkpkZJsVQl5ygBug8RZO9GudU-Gfv3ZIIx4JZWLObRNLwkRRk8jHNlI_zmxn_ItTu2opozFNO3nNZw3spdUmflh2IaCQO-1meOq5iawjPu0h8H1-AVEQfK7il7qmhVNTOKcujEfTkjDZ5Yrmd4Cf4Tl3OSfstdQkG8t1Uv-m_Sg7_dT0hSPXZLUFC-K-jUcoG8iYFly6Ty0)

*Figura 5: Una clase `Consumer` en `Estable` usa `Provider` en `Flexible`.*
Adaptado de [^2]

El principio de inversión de dependencias dice que `Consumer` -que es concreta-
no puede depender de `Provider` que también es concreta; debe depender de una
abstracción. Definimos entonces una interfaz `IProvider` que tenga todos los
atributos y métodos que `Consumer` necesita en un nuevo componente
`Abstractions`. Luego la clase `Consumer` referencia esa interfaz y la clase
`Provider` la implementa.

<span id="figura-6"/>

![Aplicación del DIP y nuevo componente Abstractions](https://www.plantuml.com/plantuml/png/TL7DIyCm5B_dhtZK--p9KotxO8M2Xo8E5BoawNC6avVoakc6xdytNSfOnUKGydvV_9BCVP0STjO8KVXmC5WAYElHkG3VfsCQTzIj71Cov6TqATN7bXDb7CCJI_AzPAHmrg116-UBB83AKKYEcpo_Mo-g2sxfk4E-nZveml-veqXxSJlUGaXZt9VLUqrRyQux1BHzE815soBx12dDog0GojdUqT0pMyS7QGs-KdsVPo0zF8_TbP7UGxPov7SM-SHjn75YNhG-i5H1Hr5AYAANCK1JG7wJ2Y6h6tQViK1AgPi_CPN1lKubobIYcfQOs5U3UmEpiXoIwWQAdzaiecAErCMV_GK0)

*Figura 5: Aplicación del DIP y nuevo componente `Abstractions`.* Adaptado de
[^2]

Ahora, con ese cambio, tanto `Consumer` como `Flexible` dependen de
`Abstractions` que es estable —$I=0$—. Noten que luego de este cambio la
inestabilidad decrece desde `Flexible` —$I>0$— hacia `Abstractions` —$I=0$—,
cumpliendo el principio de dependencias estables.
