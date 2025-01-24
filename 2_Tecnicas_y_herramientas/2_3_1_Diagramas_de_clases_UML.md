# 2 Técnicas y herramientas

## 2.3 Modelos de estructura

### Diagramas de clases UML

Los diagramas de clases UML capturan la estructura estática de un sistema,
mostrando las clases, sus atributos y métodos, y las relaciones entre ellas. Es,
probablemente, el más importante de los diagramas.

Aunque lo llamamos diagramas de clases, y en este documento incluimos ejemplos
de estos diagramas generalmente con clases, en realidad pueden aparecer otros
[clasificadores](/4_Conceptos/4_Clasificador.md) además de las clases.

Este documento está basado en UML 2.5.1[^1].

Los diagramas de clases tienen principalmente:

* Clases, que se representan mediante un rectángulo, opcionalmente dividido en
  secciones mediante líneas horizontales. El rectángulo contiene siempre el
  nombre de la clase. Modelan generalmente clases de objetos, y mediante
  estereotipos pueden modelar también interfaces, tipos de datos, clases
  plantilla, o meta-clases; como dijimos antes, además de clases puede aparecer
  cualquiera de los otros clasificadores, y también estereotipos de esos otros
  clasificadores. En caso de que aparezcan secciones, típicamente en la sección
  debajo del nombre de la clase van los atributos, y en la sección debajo de los
  atributos van los métodos.

* Asociaciones, que se representan mediante una línea que une dos o más clases
  relacionadas, y se utilizan para modelar un conjunto de vínculos entre
  instancias de esas clases; típicamente representan la responsabilidad de una
  clase de conocer a otra.

* Agregaciones, que son una forma especial de asociación que especifica una
  relación "es parte de" entre el todo y cada una de sus partes, y se
  representan con un diamante hueco del lado del todo. La instancia con sus
  instancias agregadas se trata generalmente como una unidad en varias
  operaciones.

* Composiciones, que son una forma de agregación con una relación de pertenencia
  muy fuerte y un ciclo de vida coincidente entre las partes y el todo, y se
  representan con un diamante relleno del lado del compuesto.

* Generalizaciones, que define una relación de generalización-especialización
  entre dos clasificadores —entre dos clases, esta relación es la herencia—, y
  que se representa con una línea terminada en un triángulo de lado del elemento
  más general —la clase base en el caso de la herencia—.

* Dependencias, que modelan una relación entre dos elementos, en la cual un
  cambio en uno de ellos —el elemento independiente— afectará al otro —el
  elemento dependiente—, que se representan con una flecha punteada apuntando al
  elemento independiente.

> [!NOTE]
> Es importante destacar que aunque dibujemos las asociaciones, agregaciones y
> composiciones entre clases, la relación es entre instancias de esas clases.

La notación para modelar los atributos y las operaciones en las clases es la
siguiente[^2]:

``` code
Atributo ::= Nombre [ ":" Tipo ] [ "=" Valor inicial ]
Operación ::= Nombre "(" [ Lista argumentos ] ")" [ ":" Tipo ]
Lista argumentos ::= Argumento | Argumento "," Lista argumentos
Argumento ::= Nombre [ ":" Tipo ] [ "=" Valor por defecto ]
```

Es posible indicar la visibilidad de clases, atributos, operaciones y relaciones
de la siguiente manera:

* Privado, agregar el símbolo `-` antes del nombre del elemento; sólo otros
  elementos en el mismo contenedor pueden ver y usar los elementos privados.

* Protegido, agregar el símbolo `#` antes del nombre del elemento; sólo los
  elementos en el mismo contenedor o en un descendiente del contenedor pueden
  ver y usar los elementos protegidos.

* Público, agregar el símbolo `+` antes del nombre del elemento; cualquier
  elemento que pueda ver el contenedor también puede ver y usar los elementos
  públicos.

* Paquete, agregar el símbolo `~` antes del nombre del elemento; sólo los
elementos dentro del mismo paquete que el contenedor pueden ver y usar los
elementos del paquete.

En la lista anterior, usamos "contenedor" y "elemento" de la siguiente forma:

* En atributos y operaciones, el contenedor es la clase y los elementos son
  atributos y operaciones.

* El clases, el contenedor es el paquete en el que se declara la clase, los
  elementos son otras clases que puedan estas relacionadas con ella.

* En las relaciones, el contenedor es la clase de origen de la relación, los
  elementos son las clases de destino.

La [Figura 1](#figura-1), a continuación, muestra una clase solamente con el
nombre, y otra clase con las secciones para los atributos y las operaciones.

<a id="figura-1"/>

![Diagrama con dos clases, una de ella con atributos y
operaciones](/diagrams/Class_Diagram_Classes.svg)

*Figura 1: Un diagrama de clases con dos clases, una de ellas con atributos y operaciones.*

<a id="figura-2"/>

![Diagrama con un estereotipo de
interfaz](/diagrams/Class_Diagram_Interfaces.svg)

*Figura 2: Un diagrama de clases con una interfaz; noten el estereotipo
`≪interface≫` utilizado para indicar que el símbolo representa una interfaz, y
no una clase.*

Las asociaciones, agregaciones y composiciones pueden tener un nombre; en caso
de que el nombre de la relación tenga una semántica diferente según la dirección
en que se lea, se pueden agregar los símbolos ⏵ o ⏴ para indicar en qué
dirección tiene sentido el nombre indicado.

Para modelar información adicional en una asociación, agregación o composición
—es decir, agregar otra información además del nombre y la multiplicidad—, se
usa una clase de asociación.

En la [Figura 3](#figura-3), a continuación, la clase `Persona` tiene una
relación `Trabaja para` con la clase `Empresa`, para modelar que una persona
trabaja para una empresa. Noten que cuando `Persona` y `Empresa` cambian de
lugar, es necesario agregar el símbolo `⏴` para indicar que la relación `Trabaja
para` se lee de derecha a izquierda, es decir, al revés de lo habitual —de lo
contrario modelaríamos que la empresa trabaja para la persona, lo cual no sería
correcto.— En el último ejemplo de esa figura, se puede ver cómo modelamos
información adicional de la asociación `Trabaja para`, mediante la clase de
asociación `Trabajo`; de esta forma, podemos decir qué cargo ocupa y qué salario
tiene una persona que trabaja para una empresa.

<a id="figura-3"/>

![Diagrama de clases mostrando asociaciones entre clases y una clase
de asociación](/diagrams/Class_Diagram_Associations.svg)

*Figura 3: Un diagrama de clases mostrando asociaciones entre clases y una clase
de asociación.*

Las asociaciones, agregaciones y composiciones pueden tener una sola dirección
—una clase conoce a la otra, pero no al revés— o ambas direcciones; en caso de
que tenga dirección, se representa con una flecha apuntando en la dirección de
la relación, y en caso de que tenga ambas direcciones, no se coloca ninguna
flecha.

En la [Figura 4](#figura-4), a continuación, la clase `Camión` tiene un
asociación `Arrastra` con la clase `Zorra`, para modelar que un camión arrastra
una zorra; noten que como la asociación está dirigida desde `Camión` hacia
`Zorra`, el camión conoce la zorra que arrastra, pero la zorra no conoce el
camión que la arrastra.

<a id="figura-4"/>

![Diagrama de clases con una asociación
dirigida](/diagrams/Class_Diagram_Directed_Association.svg)

*Figura 4: Un diagrama de clases mostrando una asociación dirigida.*

Las asociaciones, agregaciones y composiciones pueden tener o no multiplicidad,
es decir, el rango válido de instancias que pueden estar relacionadas.

En la [Figura 5](#figura-5), a continuación, podemos ver varios ejemplos de
multiplicidad en asociaciones:

* La clase `Persona` tiene la asociación `Trabaja para` la clase `Empresa` que
  ya hemos visto. En este ejemplo agregamos el rol de las clases en la
  asociación: la clase `Persona` tiene el rol de `Empleado`, mientras que la
  clase `Empresa` tiene el rol de `Empleador`. Los roles muchas veces son
  evidentes a partir del contexto. Cuando no lo sean, es necesario agregarlos.
  También en necesario agregar los roles cuando una clase está relacionada
  consigo misma —una relación recursiva—.

  La multiplicidad `0..1` modela la cantidad de empresas para las que puede
  trabajar una persona: ninguna —la persona es un desempleado o es una persona
  que no puede o no quiere trabajar—, o una —este modelo no contempla que una
  persona pueda trabajar para más de una empresa—. La multiplicidad `1..*`
  modela la cantidad de personas que trabajan para una empresa: al menos una, o
  muchas. Noten que la multiplicidad para una instancia de una clase con otra,
  se especifica al final de la asociación de la una, es decir, junto a la otra.

* La clase `Camión` tiene la asociación `Arrastra` a la clase `Zorra`; a
  diferencia del ejemplo anterior en la figura 4, esta asociación no es
  dirigida. La multiplicidad `1` indica que una zorra es arrastrada por
  exactamente un camión. La multiplicidad `0..1` modela que un camión puede no
  arrastrar ninguna zorra, o a lo sumo arrastra una zorra.

* La clase `Vehículo` tiene la asociación `Rueda sobre` la clase `Rueda`. La
  multiplicidad `1..4,6,10,14` indica que un vehículo rueda sobre 1, 2, 3 4, 6,
  10 o 14 ruedas solamente, los demás valores no son válidos. La multiplicidad
  `1` indica que una rueda está asociada con solamente un vehículo —los
  vehículos no comparten las ruedas—.

* La clase `Jefe` tiene la asociación `Manda` la clase `Empleado`. En este caso
  la multiplicidad `*` no especifica un límite inferior. Tampoco hay
  multiplicidad indicada del lado del jefe: aunque en este caso se asume `1`, es
  recomendable indicarlo para evitar la ambigüedad, porque podría faltar porque
  nos olvidamos de ponerlo o porque es uno.

<a id="figura-5"/>

![Diagrama de clases con
multiplicidades](/diagrams/Class_Diagram_Multiplicity.svg)

*Figura 5: Un diagrama de clases con varios ejemplos de multiplicidad en las
asociaciones.*

En la [Figura 6](#figura-6), a continuación, vemos ejemplos de agregaciones:

* La clase `Curso` tiene una agregación con la clase `Alumno`, es decir, un
  alumno es parte de un curso. Todo lo que vimos antes sobre el nombre, la
  dirección, la multiplicidad y los roles de las asociaciones se aplica también
  a las agregaciones.

* La clase `Polígono` tiene una agregación `Está formado por` la clase `Punto`.
  La multiplicidad `3..*` indica que por lo menos un polígono tiene tres puntos,
  pero puede tener más. La restricción `{ordenados}` indica que los puntos del
  polígono están ordenados, que el orden es importante en esa agregación[^3].

<a id="figura-6"/>

![Diagrama de clases con agregaciones](/diagrams/Class_Diagram_Agregations.svg)

*Figura 6: Un diagrama de clases con ejemplos de agregaciones.*

En la [Figura 7](#figura-7), a continuación, vemos ejemplos de composiciones:

* La clase `Ventana` está compuesta de dos instancias de `Slider` —con el rol de
  `Scrollbar`—, una de `Barra` —con el rol de Título— y una de `Panel` —con el
  rol de `Cuerpo`—.

* La clase `Factura` está compuesta por una instancia de `Cabezal` y varias
  instancias de `Línea`.

<a id="figura-7"/>

![Diagrama de clases con
composiciones](/diagrams/Class_Diagram_Compositions.svg)

*Figura 7: Un diagrama de clases con ejemplos de composiciones.*

En la composición, se aplican las siguientes reglas:

* La multiplicidad del compuesto no puede ser mayor que uno; no es compartido.
  En el ejemplo anterior, la multiplicidad de la composición del lado de
  `Factura` es siempre 1: una instancia de `Línea` que compone una factura no
  puede ser parte de otra factura.

* Se puede agregar partes; pero una vez agregadas son eliminadas con el todo. En
  el ejemplo anterior, se puede agregar instancias de `Línea` a `Factura`; pero
  si se elimina una instancia de `Factura`, se eliminan todas las instancias de
  `Línea` que la componen.

* Se puede remover partes; pero antes de que se elimine el todo.

En la [Figura 8](#figura-8), a continuación, vemos varios ejemplos de
generalización y especialización:

* La clase `Figura` es una generalización de las clases `Adimensional`,
  `Unidimensional` y `Bidimensional`; o dicho de otra forma, las clases
  `Adimensional`, `Unidimensional` y `Bidimensional` heredan o son sucesoras de
  `Figura` y la clase `Figura` es la clase base de las otras. Se cumple siempre
  la afirmación de que una figura adimensional es un tipo de figura. Las clases
  sucesoras comparten los atributos y las operaciones de la clase base, y
  agregan sus propios atributos y operaciones.

* La clase `Punto` hereda de `Adimensional`.

* Las clases `Arco`, `Línea` y `Spline` heredan de `Unidimensional`.

* Las clases `Círculo` y `Polígono` heredan de `Bidimensional`.

<a id="figura-8"/>

![Diagrama de clases con
generalizaciones y
especializaciones](/diagrams/Class_Diagram_Generalization.svg)

*Figura 8: Un diagrama de clases con ejemplos de generalización y
especialización.*

Para modelar una clase abstracta o una interfaz se utilizan los estereotipos
`≪abstract≫` e `≪interface≫` debajo del nombre de la clase abstracta o de la
interfaz, respectivamente.

Las siguientes reglas aplican a las relaciones de generalización y
especialización:

* Las clases abstractas están diseñadas sólo para ser heredadas.

* Las clases abstractas nunca tienen instancias.

* Las clases concretas son diseñadas para tener instancias.

* Una clase abstracta no puede ser subclase de una clase concreta.

En la herencia simple, una clase puede tener una superclase. En la herencia
múltiple, en cambio, una clase puede tener varias superclases.

Una clase puede no tener ninguna superclase y es el origen de la jerarquía.

Habitualmente los lenguajes de programación tienen una sola jerarquía, es decir,
hay sólo una clase sin superclase.

En la [Figura 9](#figura-9), a continuación, vemos un ejemplo de herencia múltiple: la clase
`Vehículo anfibio` hereda tanto de `Vehículo acuático` como de `Vehículo
terrestre`.

<a id="figura-9"/>

![Diagrama de clases con herencia
múltiple](/diagrams/Class_Diagram_Multiple_Inheritance.svg)

*Figura 9: Un diagrama de clases con ejemplo de herencia múltiple.*

Tengan en cuenta que algunos lenguajes de programación no soportan herencia
múltiple. Una alternativa es usar composición y delegación, como se muestra en
la [Figura 10](#figura-10), a continuación:

<a id="figura-10"/>

![Diagrama de clases herencia múltiple versus composición y
delegación](/diagrams/Class_Diagram_Composition_Multiple_Inheritance.svg)

*Figura 10: Un diagrama de clases con ejemplo de herencia múltiple versus
composición y delegación*

La clase `Murciélago` hereda simultáneamente de las clases `Volador` y de
`Mamífero`, por lo tanto tiene las operaciones `Volar()` e `Mamar()` —un
murciélago es efectivamente un mamífero volador—. En la alternativa con
composición, la clase `Murciélago` hereda directamente de animal, y está
compuesto por una instancia de `Volador` y otra de `Mamífero`; cuando un objeto
de la clase `Murciélago` recibe el mensaje `Volar`, lo delega —envía a su vez un
mensaje— a la instancia de `Volador` que lo compone; algo similar ocurre cuando
recibe un mensaje `Mamar`, en este caso lo delega a la instancia de `Mamífero`
que lo compone. La alternativa de usar composición y delegación puede no ser
perfecta, pero en muchos casos es útil.

En la [Figura 11](#figura-11), a continuación, vemos ejemplos de dependencias.
Como vimos antes, los diagramas de clases pueden incluir cualquier
[clasificador](/4_Conceptos/4_Clasificador.md), por lo que en este caso
ejemplificaremos las dependencias relacionando entre paquetes y no clases como
en ejemplos anteriores. Los paquetes se representan con un rectángulo con el
nombre del paquete, y otro rectángulo más pequeño en la esquina superior
izquierda —como si fuera una solapa— con el estereotipo `≪package≫`. El ejemplo
es el clásico patrón de arquitectura MVC[^4], compuestos por los paquetes
`Modelo`, `Vista` y `Controlador`. En este patrón, las clases en el paquete
`Model` son las clases del dominio y representan el estado de la aplicación; las
clases en el paquete `Vista` muestran datos del modelo y se actualizan cuando
los datos del modelo cambian; las acciones del usuario son enviadas a alguna
clases en el paquete `Controlador`, que bien actualiza el modelo o envía las
acciones del usuario a la vista si corresponde.

<a id="figura-11"/>

![Diagrama de clases mostrando paquetes del patrón de arquitectura
MVC](/diagrams/MVC.svg)

*Figura 11: Diagrama de clases mostrando paquetes del patrón de arquitectura
MVC.*

Existen estereotipos para las dependencias más comunes:

* `≪use≫`, se utiliza cuando la clase dependiente tiene atributos, parámetros, o
variables locales que son instancias de la clase independiente.

* `≪create≫`, se utiliza cuando la clase dependiente crea instancias de la clase
  independiente.

* `≪call≫`, se utiliza cuando una operación en la clase dependiente invoca otra
  operación en la clase independiente.

En la [Figura 12](#figura-12), a continuación, vemos ejemplos de elementos
derivados. Un elemento es derivado cuando se puede calcular a partir de otro
elemento, pero se muestra por claridad o se incluye por razones de diseño,
aunque no agregue información semántica. Para indicar que un elemento es
derivado se agrega `/` antes del nombre del elemento.

En la clase `Persona`, el atributo `Edad` es derivado, porque se puede calcular
a partir del atributo `Fecha de nacimiento`. La restricción `Edad=Hoy-Fecha de
nacimiento` explica cómo se hace el cálculo del atributo derivado.

La relación `Trabaja para` entre las clases `Persona` y `Empresa` es derivada,
porque se puede calcular a partir de las relaciones entre `Empresa` y
`División`, entre `División` y `Departamento` y `Departamento` y `Persona`: el
departamento en el que trabaja la persona pertenece a una división, que a su vez
pertenece a una empresa; la persona trabaja en esa empresa.

La relación `Ocupa` entre las clases `Departamento` y `Edificio` también es
derivada, a partir de las relaciones entre `Edificio` y `Oficina`, y entre
`Oficina` y `Departamento`: la oficina que ocupa el departamento pertenece a un
edificio, el departamento ocupa ese edificio.

<a id="figura-12"/>

![Diagrama de clases con elementos
derivados](../diagrams/Class_Diagram_Derived.svg)

*Figura 12: Diagrama de clases con elementos derivados.*

Puedes ver más ejemplos de [diagramas de clases en UML
Diagrams](https://www.uml-diagrams.org/class-diagrams-overview.html).

[^1]: OMG. (2017). OMG® Unified Modeling Language®. Disponible
    [aquí](https://www.omg.org/spec/UML/2.5.1/PDF).
[^2]: Esta notación está expresada usando [Backus-Naur
    Form](https://foldoc.org/Backus-Naur+Form).
[^3]: Aunque mostramos la restricción con un ejemplo de agregación, las
    restricciones aplican también a las asociaciones y composiciones.
[^4]: La versión de MVC que utilizamos aquí como ejemplo es la original de
    Smalltalk-80 documentada por Trygve Reenskaug, inventor of MVC; pueden ver
    los documentos
    [aquí](https://folk.universitetetioslo.no/trygver/themes/mvc/mvc-index.html)
