# 4 Conceptos

## Disponibilidad o *availability*

La disponibilidad ‑o *availability* en inglés‑ es un atributo de calidad de una
arquitectura de software que define el grado en el cual un sistema, producto o
componente está operativo y accesible cuando se requiere su uso[^1].

[^1]: ISO/IEC 25010. (2011). ISO/IEC 25010:2011, Systems and software
    engineering‑Systems and software Quality Requirements and Evaluation
    (SQuaRE) ‑ System and software quality models.

Es la probabilidad de que un sistema esté en funcionamiento en cualquier momento
dado. Este atributo es relevante para sistemas, productos o componentes que
deben estar continuamente disponibles, como servicios de emergencia, sistemas
bancarios, plataformas de comercio electrónico, entre otros.

Bass y otros[^2] incluyen dentro del atributo de disponibilidad conceptos de prevención
de fallos y recuperación de los fallos, que en ISO/IEC 25010[^1] pueden estar
también relacionados con los atributos de [tolerancia a
fallos](./4_Atributos_de_calidad.md#tolerancia-a-fallos) y [capacidad de
recuperación](./4_Atributos_de_calidad.md#capacidad-de-recuperación)
respectivamente.

[^2]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4<sup>th</sup> edition. Addison-Wesley.

Algo similar sucede en el Azure Well-Architected Framework[^3] donde el pilar es
[fiabilidad](https://learn.microsoft.com/en-us/azure/well-architected/reliability/)
que incluye
[resiliencia](https://learn.microsoft.com/en-us/azure/well-architected/reliability/principles#design-for-resilience)
y
[recuperación](https://learn.microsoft.com/en-us/azure/well-architected/reliability/principles#design-for-recovery)
que están también relacionados con los atributos de [tolerancia a
fallos](./4_Atributos_de_calidad.md#tolerancia-a-fallos) y [capacidad de
recuperación](./4_Atributos_de_calidad.md#capacidad-de-recuperación)
respectivamente.

[^3]: Microsoft. (2023). Reliability design principles. Disponible
    [aquí](https://learn.microsoft.com/en-us/azure/well-architected/reliability/principles).

### Medición de la disponibilidad

La disponibilidad se mide generalmente como una proporción del tiempo en que el
sistema está operativo y accesible frente al tiempo total. Se expresa como un
porcentaje y se calcula utilizando la siguiente fórmula:

$\text{Disponibilidad} = \frac{\text{Tiempo de Operación}}{\text{Tiempo Total}}
\times 100$

Donde:

* $\text{Tiempo de Operación}$ o *uptime*: es el tiempo durante el cual el
  sistema está funcionando correctamente.
* $\text{Tiempo Total}$: es la suma del tiempo de operación y el tiempo de
  inactividad ‑o *downtime*‑, que incluye tanto el tiempo planificado para
  mantenimiento como el tiempo no planificado debido a fallos o interrupciones.

Por ejemplo:

Si un sistema estuvo operativo durante 696 horas en un mes ‑que tiene 720 horas‑
y tuvo 24 horas de inactividad no planificada, la disponibilidad se calcularía
de la siguiente manera:

$\text{Disponibilidad} = \frac{720 - 24}{720} \times 100 = \frac{696}{720}
\times 100 \approx 96.67\%$

La fórmula de disponibilidad también se puede expresar en términos de tiempo
medio entre fallos ‑o MTBF por sus siglas en inglés, que significa *mean time to
failure*‑ y tiempo medio de reparación ‑o MTTR por sus siglas en inglés, que
significa *mean time to repair*‑.

La disponibilidad se puede calcular utilizando MTBF y MTTR con la siguiente fórmula:

$\text{Disponibilidad} = \frac{\text{MTBF}}{\text{MTBF} + \text{MTTR}}$

Donde:

* $\text{MTTF}$: es el tiempo promedio que transcurre entre fallos sucesivos de
  un sistema. Representa la fiabilidad del sistema.
* $\text{MTTR}$: es el tiempo promedio que se tarda en reparar un fallo y
  restaurar el sistema a su funcionamiento normal. Representa la capacidad de
  recuperación del sistema.

Para entender cómo ambas fórmulas están relacionadas, considera lo siguiente:

* Tiempo total de operación y reparación:
  * El tiempo total de operación entre dos fallas es MTBF.
  * El tiempo total para reparar y volver a la operación es MTTR.

* Ciclo completo:
  * Un ciclo completo incluye el tiempo de operación o MTBF y el tiempo de
    reparación o MTTR.
  * Entonces, el tiempo total de un ciclo es $\text{MTBF} + \text{MTTR}$.

* Proporción del tiempo de operación:
  * La disponibilidad es la proporción del tiempo de operación en relación con el
  tiempo total.
  * Por lo tanto, se calcula como la fracción del tiempo de operación sobre el
  tiempo total del ciclo.

$\text{Disponibilidad} = \frac{\text{Tiempo de Operación}}{\text{Tiempo Total}}
= \frac{\text{MTBF}}{\text{MTBF} + \text{MTTR}}$

Por ejemplo:

Supongamos que un sistema tiene un MTBF de 1000 horas y un MTTR de 10 horas:

$\text{Disponibilidad} = \frac{1000}{1000 + 10} = \frac{1000}{1010} \approx
0.9901$

Esto significa que la disponibilidad del sistema es aproximadamente 99.01%.

### Importancia de MTBF y MTTR

* **MTBF**: Un mayor MTBF indica que el sistema es más fiable y tiene menos
  fallas en un período de tiempo determinado, lo que aumenta la disponibilidad.
* **MTTR**: Un menor MTTR indica que el sistema se repara más rápidamente cuando
  ocurre una falla, lo que también aumenta la disponibilidad.

<!-- ### Factores que Afectan la Disponibilidad

1. **Redundancia**: Implementación de componentes redundantes que pueden asumir
   el funcionamiento en caso de falla de un componente principal.
2. **Mantenimiento y Soporte**: Programación de mantenimientos regulares y
   soporte técnico eficaz para reducir el tiempo de inactividad.
3. **Monitoreo y Alertas**: Uso de sistemas de monitoreo para detectar y
   responder rápidamente a problemas.
4. **Sistemas de Recuperación**: Planes de recuperación ante desastres y copias
   de seguridad para restaurar el servicio rápidamente después de una
   interrupción. -->

### Objetivos de disponibilidad

Las organizaciones a menudo establecen objetivos de disponibilidad específicos,
conocidos como **acuerdos de nivel de servicio** o **SLA** por sus siglas en
inglés ‑*service level agreement*-, que pueden ser del 99.9%
‑conocido como "tres nueves"‑, 99.99% ‑"cuatro nueves"‑ o incluso más altos,
dependiendo de la criticidad del sistema.

* **99.9% o tres nueves**: Aproximadamente 8.76 horas de inactividad al año.
* **99.99% o cuatro nueves**: Aproximadamente 52.56 minutos de inactividad al año.
* **99.999% o cinco nueves**: Aproximadamente 5.26 minutos de inactividad al año.

La disponibilidad es un aspecto crucial de la arquitectura de un producto que
requiere alta confiabilidad y accesibilidad constante.

### Tácticas para la disponibilidad

Vean más detalles sobre estas tácticas para la disponibilidad
[aquí](/2_Tecnicas_y_herramientas/2_5_1_Tacticas_disponibilidad.md).

<table>
  <tr>
    <td rowspan="26">Tácticas de disponibilidad</td>
    <td rowspan="9" colspan="2">Detectar fallas</td>
    <td>Monitoreo</td>
  </tr>
  <tr>
    <td>Ping/echo</td>
  </tr>
  <tr>
    <td>Heartbeat</td>
  </tr>
  <tr>
    <td>Timestamp</td>
  </tr>
  <tr>
    <td>Monitoreo de condiciones</td>
  </tr>
  <tr>
    <td>Chequeo de salud</td>
  </tr>
  <tr>
    <td>Voto: replicación, redundancia funcional, redundancia analítica</td>
  </tr>
  <tr>
    <td>Detección de excepciones</td>
  </tr>
  <tr>
    <td>Auto-diagnóstico</td>
  </tr>
  <tr>
    <td rowspan="12">Recuperarse de las fallas</td>
    <td rowspan="8">Preparación y reparación</td>
    <td>Repuesto redundante</td>
  </tr>
  <tr>
    <td>Rollback</td>
  </tr>
  <tr>
    <td>Manejo de excepciones</td>
  </tr>
  <tr>
    <td>Actualización de software</td>
  </tr>
  <tr>
    <td>Re-intentos</td>
  </tr>
  <tr>
    <td>Ignorar el comportamiento fallido</td>
  </tr>
  <tr>
    <td>Degradación elegante</td>
  </tr>
  <tr>
    <td>Re-configuración</td>
  </tr>
  <tr>
      <td rowspan="4">Re-introducción</td>
      <td>Sombra</td>
  </tr>
  <tr>
    <td>Re-sincronización del estado</td>
  </tr>
  <tr>
    <td>Escalamiento del reinicio</td>
  </tr>
  <tr>
      <td>Reenvío sin pausa</td>
  </tr>
  <tr>
    <td rowspan="5" colspan="2">Prevenir fallas</td>
      <td>Remoción del servicio o rejuvenecimiento de software o reinicio terapéutico</td>
  </tr>
  <tr>
      <td>Transacciones</td>
  </tr>
  <tr>
      <td>Modelo predictivo</td>
  </tr>
  <tr>
      <td>Prevención de excepciones</td>
  </tr>
  <tr>
      <td>Aumentar el conjunto de competencia</td>
  </tr>
</table>

### Patrones para disponibilidad

Vean [Cloud design patterns that support
reliability](https://learn.microsoft.com/en-us/azure/well-architected/reliability/design-patterns)
en Azure Well-Architected Framework.

Vean [Tactics and Patterns for Software Robustness](https://insights.sei.cmu.edu/blog/tactics-and-patterns-for-software-robustness/) en Carnegie Mellon
University, Software Engineering Institute's Insights Blog.
