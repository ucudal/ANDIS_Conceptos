# 4 Conceptos

## REP o *Reuse/Release Equivalence Principle*

En las últimas décadas ha crecido la importancia y la adopción de herramientas
de gestión de paquetes, en la medida que también ha aumentado disponibilidad de
librerías reutilizables útiles y maduras; sobretodo una vez que se resolvieron
los problemas relacionados con la resolución de dependencias y la independencia
de plataformas.

El principio de equivalencia entre liberación y reutilización, o REP por sus
siglas en inglés, parece bastante obvio[^1][^2]:

[^1]: Martin, R. C. (1997). Granularity. The C++ Report. Recuperado de Object
    Mentor [aquí](http://objectmentor.com/resources/articles/granularity.pdf).

[^2]: Martin, R. C. (2018). Clean architecture: A craftsman’s guide to software
    structure and design. Pearson.

> La granularidad de la reutilización es la granularidad de la liberación. Sólo
> las clases —y otros tipos de datos— que sean liberados a través de un
> mecanismo de seguimiento pueden ser reutilizados efectivamente. Esta
> granularidad es el componente[^3].

[^3]: En la definición original en [^1] se usa ≪paquete≫ en lugar de
    ≪componente≫; en este y otros principios de Martin usamos ≪componente≫ como
    unidad de liberación, que en este contexto es equivalente a ≪paquete≫.

No es posible —o al menos no es razonable— hacer el seguimiento de las versiones
liberadas de clases individuales: suelen ser demasiadas; por eso, las clases son
liberadas en componentes.

Esto tiene varias consecuencias para los componentes reutilizables:

* Tienen que estar versionados con un identificador de versión[^4]. De esa
  forma, los componentes que dependen de otros —los que reutilizan—, lo hacen de
  versiones específicas, y el desarrollador tiene la libertad de actualizar o no
  los componentes de los que depende —un componente puede ser compatible con
  cierta versión de otro, pero no con las anteriores o las posteriores—.

* Tienen que ser liberados mediante un proceso de liberación. Los
  desarrolladores tienen que enterarse cuando hay una nueva versión disponible,
  para tomar la decisión de utilizar o no esa nueva versión.

* Deberían incluir un conjunto cohesivo de tipos de datos —clases, interfaces,
  etc.—. Tiene que tener sentido que estos tipos de datos sean liberados al
  mismo tiempo.

[^4]: Típicamente el identificador de versión es `mayor`.`minor`.`patch`, por
    ejemplo, `1.0.0`; también hay identificadores basados en fechas, por
    ejemplo, `2026.1`; o en nombres propios, como `Sequoia` o `Tahoe` en MacOS,
    aunque en este caso también se incluyen números, el primero es `15` y el
    segundo `26`.

Este principio es relativamente débil, porque es difícil de explicar por qué los
tipos liberados en un componente tienen que estar juntos en ese componente. Pero
también es fácil darse cuenta cuando se viola. Este principio se utiliza junto
con los principios [CCP](./4_CCP.md) y [CRP](./4_CRP.md).

> [!TIP]
> Mira especialmente el [diagrama de tensión](./4_CRP.md#diagrama-de-tensión)
> para los principios relacionados con cohesión: REP, [CCP](./4_CCP.md) y
> [CRP](./4_CRP.md).
