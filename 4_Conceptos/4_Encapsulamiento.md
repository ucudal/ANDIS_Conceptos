# 4 Conceptos

## Encapsulamiento

Mientras la [abstracción](/4_Conceptos/4_Abstraccion.md) ayuda a manejar la
complejidad proveyendo modelos que permiten ignorar los detalles de
implementación, el encapsulamiento es lo que impide que puedas siquiera mirar
los detalles de la implementación, aunque quisieras[^1].

[^1]: McConnell, S. (2004). Code Complete, 2<sup>nd</sup> edition. Microsoft
    Press. Disponible en biblioteca
    [aquí](https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=52312).

Para que la abstracción funcione, las implementaciones deben estar encapsuladas;
si la implementación está encapsulada, ningún componente podrá depender de los
detalles de la implementación. El encapsulamiento garantiza que los componentes
pueden ser implementados y vueltos a implementar independientemente de los
demás; esto está relacionado con el principio de escondimiento de información
mencionado por David Parnas[^2].

[^2]: Liskov, B. (1987). Keynote address - data abstraction and hierarchy. In
    Addendum to the proceedings on Object-oriented programming systems,
    languages and applications (Addendum), OOPSLA '87. Association for Computing
    Machinery, New York, NY, USA, 17–34. Disponible
    [aquí](https://dl.acm.org/doi/pdf/10.1145/62139.62141).
