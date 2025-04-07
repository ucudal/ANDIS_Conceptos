# 4 Conceptos

## Abstracción

La abstracción es una de las formas fundamentales que tenemos las personas de
hacer frente la complejidad. La abstracción es la eliminación de lo irrelevante
y la amplificación de lo esencial[^1].

[^1]: Booch, G. (2007). Object-oriented analysis and design with applications,
    3<sup>rd</sup> ed. Addison-Wesley Professional. Disponible en biblioteca
    [aquí](https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=86026).

La abstracción es la habilidad de tratar con un concepto mientras ignoras de
forma segura algunos de sus detalles —manejando diferentes detalles a diferentes
niveles—. Cada vez que usas un agregado, estás trabajando con una abstracción:
si te refieres a una cosa como ≪casa≫ en lugar de una combinación de ladrillos,
cemento, metal y vidrio, estás haciendo una abstracción[^2].

[^2]: McConnell, S. (2004). Code Complete, 2<sup>nd</sup> edition. Microsoft
    Press. Disponible en biblioteca
    [aquí](https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=52312).

La abstracción es una técnica de ingeniería indispensable asociada a la
resolución de problemas en el desarrollo de software. Se refiere tanto al
proceso como al resultado de la generalización, donde se reduce la información
sobre un concepto, problema o fenómeno observable para centrarse en el ≪panorama
general≫. A través de la abstracción —según Gerard Voland— vemos el problema y
sus posibles soluciones desde un nivel superior de comprensión conceptual. Como
resultado, podemos estar mejor preparados para reconocer posibles relaciones
entre diferentes aspectos del problema y, de ese modo, generar soluciones de
diseño más creativas. El propósito de la abstracción —escribió Edsger Dijkstra—
no es ser vago o difuso, sino crear un nuevo nivel semántico en el cual ser
absolutamente preciso[^3].

[^3]: IEEE Computer Society. (2024). SWEBOK: Guide to the Software Engineering
    Body of Knowledge v4.0. IEEE. Disponible
    [aquí](https://ieeecs-media.computer.org/media/education/swebok/swebok-v4.pdf).

A propósito de los niveles mencionados por Voland y por Dijkstra, durante el
proceso de abstracción nos concentramos en un nivel a la vez, confiando en que
podemos conectar los conceptos que abstraemos tanto con conceptos en los niveles
superiores —que serían todavía más abstractos— como en los inferiores —que
serían más concretos—. Esto da lugar a una jerarquía en secuencia de
abstracciones —cada abstracción tiene un solo sucesor y un solo precedente— o a
una estructura tipo árbol —cada abstracción tiene múltiples sucesores y
eventualmente más de un precedente aunque nunca habrá ciclos—. Los elementos
abstractos no necesariamente corresponden con construcciones concretos en la
realidad o en el domino del problema[^3].

La primera forma de abstracción en programación fue el procedimiento: un
procedimiento realiza una tarea —si la tarea es obtener un resultado la
llamaremos función en lugar de procedimiento— que otras partes de un programa
pueden invocar para que se realice la tarea. Para usar un procedimiento el
programador solo se preocupa de lo que el procedimiento hace y no de cómo lo
hace. Cualquier implementación que haga lo que la función debe hacer sirve, si
lo implementa de forma correcta y eficiente[^4].

[^4]: Liskov, B. (1987). Keynote address - data abstraction and hierarchy. In
    Addendum to the proceedings on Object-oriented programming systems,
    languages and applications (Addendum), OOPSLA '87. Association for Computing
    Machinery, New York, NY, USA, 17–34. Disponible
    [aquí](https://dl.acm.org/doi/pdf/10.1145/62139.62141).

El beneficio de la abstracción mediante los procedimientos se extendió a los
datos a través de las abstracciones de datos o tipos abstractos de datos. En los
tipos abstractos de datos la representación —cómo los datos se representan en
memoria u otros medios de almacenamiento— se [encapsula](./4_Encapsulamiento.md)
a través de operaciones que permiten manipular los datos, impidiendo a los
programas que accedan directamente a la representación. De esa forma es posible
cambiar la representación sin afectar a los programas que usan los datos[^4].

A veces es conveniente considerar múltiples abstracciones al mismo nivel pero
desde diferentes puntos de vista, para poder tener diferentes perspectivas en
mente: por ejemplo un [diagrama de
clases](/2_Tecnicas_y_herramientas/2_03_01_Diagramas_de_clases_UML.md), un
[diagrama de
actividades](/2_Tecnicas_y_herramientas/2_04_01_Diagramas_de_actividades_UML.md) y
un [diagrama de
secuencia](/2_Tecnicas_y_herramientas/2_04_03_Diagramas_de_secuencia_UML.md) de la
misma pieza de software pueden estar todos en el mismo nivel de abstracción,
complementándose unos a otros para ayudar a entender el problema y su
solución[^3].
