# 4 Conceptos

## Facilidad de modificación o *modifiability*

La facilidad de modificación —o *modifiability* en inglés— es un atributo de
calidad de la arquitectura de software que baja el costo y el riesgo de hacer
cambios[^1].

[^1]: Bass, L., Clements, P., Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

En ISO/IEC 25010 la facilidad de modificación es una sub-característica de la
[facilidad de
mantenimiento](./4_Atributos_de_calidad.md#facilidad-de-mantenimiento) y se
define como la capacidad de un sistema, producto o componente que permite que
sea modificado de forma efectiva y eficiente sin introducir defectos o degradar
su calidad[^2].

[^2]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering—Systems and software Quality Requirements and Evaluation
    (SQuaRE) — System and software quality models.

Este atributo es importante porque si en diversos contextos la única constante
es el cambio, en el software mucho más: introducción de nueva funcionalidad y
retiro de otras obsoletas, corrección de defectos, mejoras en la seguridad o en
el desempeño, actualización por nuevas tecnologías, protocolos o estándares,
reducción de la deuda técnica, entre otras razones.

Hay cuatro aspectos a considerar[^1]:

* Qué puede cambiar
* Cuál es la probabilidad de que ocurra un cambio
* Quién realiza el cambio
* Cuál es el costo del cambio

Algunas categorías de modificaciones tienen nombres propios[^1]:

* Escalabilidad
* Variabilidad
* Portabilidad
* Independencia de la ubicación

### Tácticas para la facilidad de modificación

<table>
  <tr>
    <td rowspan="15">
      Tácticas para la facilidad de modificación
    </td>
    <td rowspan="2">
      Aumentar la <a href="./4_Cohesion.md">cohesión</a>
    </td>
    <td>
      Separar módulos
    </td>
  </tr>
  <tr>
    <td>
      Redistribuir las responsabilidades
    </td>
  </tr>
  <tr>
    <td rowspan="4">
      Reducir el <a href="./4_Acoplamiento.md">acoplamiento</a>
    </td>
    <td>
      Encapsulación
    </td>
  </tr>
  <tr>
    <td>
      Usar un intermediario
    </td>
  </tr>
  <tr>
    <td>
      Abstraer servicios comunes
    </td>
  </tr>
  <tr>
    <td>
      Restringir las dependencias
    </td>
  </tr>
  <tr>
    <td rowspan="9">
      Diferir el <i>binding</i>
    </td>
    <td>
      Reemplazo de componentes
    </td>
  </tr>
  <tr>
    <td>
      Parametrización en tiempo de compilación
    </td>
  </tr>
  <tr>
    <td>
      Aspectos
    </td>
  </tr>
  <tr>
    <td>
      <i>Binding</i> en tiempo de configuración
    </td>
  </tr>
  <tr>
    <td>
      Archivos de recursos
    </td>
  </tr>
  <tr>
    <td>
      Descubrimiento
    </td>
  </tr>
  <tr>
    <td>
      Interpretación de parámetros
    </td>
  </tr>
  <tr>
    <td>
      Repositorios compartidos
    </td>
  </tr>
  <tr>
    <td>
      Polimorfismo
    </td>
  </tr>
</table>

### Patrones para la facilidad de modificación

* Patrón cliente-servidor
* Patrón plug-in —microkernel—
* Patrón capas
* Patrón editor-suscriptor

Bachmann, F., Bass, L. & Nord, R. (2007). Modifiability Tactics.
CMU/SEI-2007-TR-002 disponible
[aquí](https://insights.sei.cmu.edu/documents/778/2007_005_001_14858.pdf)

Kazman, R. (2022). Two Categories of Architecture Patterns for Deployability.
Carnegie Mellon University, Software Engineering Institute's Insights Blog.
Disponible
[aquí](https://insights.sei.cmu.edu/blog/two-categories-of-architecture-patterns-for-deployability/)
