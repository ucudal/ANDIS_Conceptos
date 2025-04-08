# 2 Técnicas y herramientas

## 2.12 Anti-patrones de diseño

> Un anti-patrón es como un patrón, excepto que, en lugar de una solución,
> ofrece algo que superficialmente parece una solución, pero no lo es.
>
> Andrew Koenig

Los anti-patrones son soluciones negativas que presentan más problemas de los
que resuelven. Entender los anti-patrones ayuda a identificar y prevenir los
problemas generados. Este listado parcial de anti-patrones está basado en [^1].

[^1]: Brown, W. J., Malveau, R. C., McCormick, H. W., & Mowbray, T. J. (1998).
      AntiPatterns: Refactoring Software, Architectures, and Projects in Crisis.
      Wiley.

### The Blob

Aparece en línea [aquí](http://antipatterns.com/briefing/sld024.htm).

Ocurre cuando una sola clase o módulo acumula demasiadas responsabilidades y se
vuelve desproporcionadamente grande. Esta clase central maneja múltiples
funcionalidades que deberían estar distribuidas entre varias clases más pequeñas
y especializadas.

Consecuencias:

* Dificulta el mantenimiento y la comprensión del código

* Dificulta la reutilización

* Tiene alto acoplamiento

* Posible impacto en el desempeño debido a la carga en una sola clase

### Lava Flow

Aparece en línea [aquí](http://antipatterns.com/lavaflow.htm).

Sucede cuando código experimental pasa a producción y permanece en la base del
código porque los desarrolladores tienen miedo de eliminarlo. Con el tiempo,
este código obsoleto se acumula como lava solidificada, haciendo que el sistema
sea más complejo y difícil de entender.

Consecuencias:

* Aumenta innecesariamente el tamaño de la base de código

* Genera confusión en los desarrolladores

* Dificulta el mantenimiento

* Posibles efectos secundarios inesperados al intentar re-factorizar

### Golden Hammer

Refiere a la tendencia de aplicar una solución favorita, sea una tecnología, un
patrón o una herramienta, a todos los problemas incluso cuando no es la más
adecuada: ≪si tu única herramienta es un martillo, todo tiene forma de clavo≫.

Consecuencias:

* Deriva en soluciones ineficientes o innecesariamente complejas

* Aumenta el costo y tiempo de desarrollo

* Limita la innovación y adaptabilidad del proyecto

### Spaghetti Code

Aparece en línea [aquí](http://antipatterns.com/briefing/sld019.htm).

Describe código con una estructura de control pobre o inexistente. Caracterizado
por un flujo de control enredado y confuso, frecuentemente con excesivo uso de
[`goto`](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/jump-statements#the-goto-statement),
anidamiento excesivo, o lógica de ramificación compleja.

Consecuencias:

* Aumenta extremadamente la dificultad de entender y mantener el código

* Aumenta la probabilidad de introducir errores al hacer cambios

* Aumenta el costo y tiempo de desarrollo

### Cut-and-Paste Programming

Ocurre cuando los desarrolladores copian y pegan bloques de código, en lugar de
crear abstracciones reutilizables. Esto conduce a la duplicación de código a lo
largo de la base de código.

Consecuencias:

* Propagación de errores cuando se descubre un problema en el código duplicado

* Aumenta innecesariamente el tamaño de la base de código

* Dificulta mantener la consistencia cuando se realizan cambios

### Monster Commit

Consiste en realizar *commits* enormes que contienen múltiples cambios no
relacionados, a menudo abarcando diversos archivos y funcionalidades. Estos
*commits* masivos son difíciles de revisar y complican el seguimiento de los
cambios.

Consecuencias:

* Revisiones de código ineficaces

* Dificulta la identificación de la causa de regresiones

* Problemas al fusionar —hacer *merge*— cambios

* Incapacidad para revertir cambios específicos sin afectar otras
  funcionalidades

### Tester Driven Development

> [!IMPORTANT]
> No confundir con [Test Driven
> Development](https://martinfowler.com/bliki/TestDrivenDevelopment.html).

También conocido como **Bug Driven Development**, ocurre cuando el desarrollo es
reactivo a los informes de errores de los testers, en lugar de seguir un enfoque
proactivo y metodológico. El código se desarrolla sin una planificación
adecuada, y los testers esencialmente dictan la dirección del desarrollo a
través de sus informes de errores.

Consecuencias:

* Ciclos continuos de corrección de errores

* Diseño inconsistente e incoherente

* Baja calidad del código

* Dificultad para predecir plazos y recursos necesarios
