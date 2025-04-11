# 4 Conceptos

## Rendimiento o *performance*

El rendimiento ‑o *performance* en inglés‑ es un atributo de la calidad de una
arquitectura de software que define la capacidad de un sistema o componente para
cumplir con sus funciones dentro de los límites de tiempo aceptables[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Las operaciones en las computadoras llevan tiempo. Los cálculos en el procesador
llevan tiempo del orden de varios nanosegundos, el acceso al disco ‑ya sea de
estado sólido o mecánico‑ lleva tiempo del orden de varios milisegundos, y
el acceso a la red lleva tiempo que va desde cientos de microsegundos dentro del
mismo centro de datos hasta más de 100 milisegundos para mensajes a centros de
cómputo en la nube.

El modelo de calidad de la norma ISO/IEC 25010[^2] no define un atributo de
calidad para el rendimiento con la definición que aquí se usa, sino para
[eficiencia de desempeño](./4_Atributo_de_calidad.md#eficiencia-de-desempeño),
que a su vez incluye una sub-característica [comportamiento
temporal](./4_Atributo_de_calidad.md#comportamiento-temporal) que es más
cercana a lo que aquí llamamos **rendimiento**. La eficiencia del desempeño
incluye además de las cuestiones relacionadas con el tiempo, otras relacionadas
con el consumo de recursos y la capacidad de éstos, en las sub-características
[utilización de recursos](./4_Atributo_de_calidad.md#utilización-de-recursos) y
[capacidad](./4_Atributo_de_calidad.md#capacidad) respectivamente.

[^2]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering‑Systems and software Quality Requirements and Evaluation
    (SQuaRE) ‑ System and software quality models.

En el Azure Well-Architected Framework[^3] el pilar es [rendimiento
eficiente](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/)
o *performance efficiency* en inglés, que al igual que [^2] incluye aspectos de
[comportamiento temporal](./4_Atributo_de_calidad.md#comportamiento-temporal)
pero también de [utilización de
recursos](./4_Atributo_de_calidad.md#utilización-de-recursos) y
[capacidad](./4_Atributo_de_calidad.md#capacidad).

[^3]: Microsoft. (2023). Performance efficiency design principles. Disponible
    [aquí](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/principles).

### Algunos componentes del rendimiento

* **Tiempo de respuesta**. Es el tiempo que tarda el sistema o componente en
   responder a una solicitud[^4] desde el momento en que se inicia la acción
   hasta que se recibe una respuesta.

* ***Throughput***. Es la cantidad de trabajo que un sistema o componente puede
   realizar en un período de tiempo dado, por ejemplo, el número de
   transacciones por segundo realizadas por un servicio, solicitudes por segundo
   procesadas por un servidor, bytes por segundo transmitidos por un canal, etc.

* **Utilización de recursos**. Es la cantidad de recursos de procesador,
   memoria, disco, red, etc. que se utilizan para realizar tareas específicas;
   usualmente se expresan como un porcentaje del total disponible de ese
   recurso.

* **Capacidad de escalabilidad**. Es la capacidad del sistema o componente para
   mantener su rendimiento a medida que se incrementa la carga de trabajo o el
   número de usuarios.

* **Latencia**. Es el tiempo de espera para comenzar el procesamiento de una
   solicitud; es parte del tiempo de respuesta y excluye el tiempo de
   procesamiento de la solicitud.

[^4]: En este contexto una solicitud es un mensaje o una invocación.

### Tácticas para el rendimiento

En cualquier momento durante el período posterior a la llegada de una solicitud,
pero antes de que se complete la respuesta del sistema, el sistema está
trabajando para responder a esa solicitud o el procesamiento está bloqueado por
alguna razón. Esto da lugar a los dos factores básicos que contribuyen al tiempo
de respuesta y al uso de recursos: el tiempo de procesamiento ‑cuando el sistema
está trabajando para responder y consumiendo recursos de forma activa‑ y el
tiempo de bloqueo ‑cuando el sistema no puede responder‑.

* Tiempo de procesamiento y uso de los recursos

* Tiempo de bloqueo y contención de recursos

* Contención de los recursos

* Disponibilidad de recursos

* Dependencia de otras operaciones

> [!TIP]
> Vean más información sobre las tácticas para rendimiento
> [aquí](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_02_Tacticas_rendimiento.md).

### Patrones para el rendimiento y la eficiencia

> [!TIP]
> Vean [Cloud design patterns that support performance
> efficiency](https://learn.microsoft.com/en-us/azure/well-architected/performance-efficiency/design-patterns)
> en Azure Well Architected Framework.

> [!TIP]
> Vean además el método
> [PASA](/2_Tecnicas_y_herramientas/2_10_.Evaluacion_arquitectura/2_10_4_PASA.md)
> de evaluación del rendimiento de la arquitectura de software.
