# 2 Técnicas y herramientas

## 2.5 Tácticas de arquitectura

### 2.5.7 Tácticas para la eficiencia energética

El objetivo de las tácticas de [eficiencia
 energética](/4_Conceptos/4_Eficiencia_energetica.md) es conservar o gestionar
la energía y a la vez proveer —eventualmente parte de— la funcionalidad
requerida, dentro de restricciones de tiempo, costo y otros atributos de
calidad.

La siguiente tabla —tomada de[^1]— resume las tácticas disponibles, que están
explicadas más abajo. Por ≪recurso≫ entendemos un dispositivo computacional[^2] que
consume energía cuando provee su funcionalidad, en la misma forma que para las
[tácticas de rendimiento](./2_05_02_Tacticas_rendimiento.md).

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4th edition. Addison-Wesley.
[^2]: Procesador, memoria, disco, red, etc.

<table border="1">
  <tr>
    <td rowspan="7">Tácticas de eficiencia energética</td>
    <td rowspan="3">Monitorizar recursos</td>
    <td>
      <a href="#medición">Medición</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#clasificación-estática">Clasificación estática</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#clasificación-dinámica">Clasificación dinámica</a>
    </td>
  </tr>
  <tr>
    <td rowspan="3">Asignar recursos</td>
    <td>
      <a href="#reducir-el-uso">Reducir el uso</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#descubrimiento">Descubrimiento</a>
    </td>
  </tr>
  <tr>
    <td>
      <a href="#calendarizar-recursos">Calendarizar recursos</a>
    </td>
  </tr>
  <tr>
    <td>Reducir la demanda de recursos</td>
    <td>
      <p><a href="#gestionar-la-llegada-de-eventos">Gestionar la llegada de eventos</a></p>
      <p><a href="#limitar-la-respuesta-a-eventos">Limitar la respuesta a eventos</a></p>
      <p><a href="#priorizar-los-eventos">Priorizar los eventos</a></p>
      <p><a href="#reducir-la-sobrecarga-computacional">Reducir la sobrecarga computacional</a></p>
      <p><a href="#limitar-los-tiempos-de-ejecución">Limitar los tiempos de ejecución</a></p>
      <p><a href="#incrementar-la-eficiencia-en-el-uso-de-recursos">Incrementar
      la eficiencia en el uso de recursos</a></p>
    </td>
  </tr>
</table>

#### Medición

Esta táctica consiste en medir de forma sistemática el consumo de recursos
y —cuando es posible— de energía. En muchos contextos se usan métricas de
utilización de recursos[^2] y de facturación de servicios nube como
aproximaciones del consumo energético.

> [!TIP]
> Aunque la preocupación es el costo y no la eficiencia energética, son
> aplicables los principios [Monitor and optimize over
> time](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/principles#monitor-and-optimize-over-time)
> en Azure Well‑Architected Framework.

#### Clasificación estática

Cuando la [medición](#medición) no está disponible, la clasificación estática
asocia a cada tipo de recurso[^2] un modelo de consumo energético basado en
especificaciones de hardware, documentación del proveedor o _benchmarks_, para
estimar de forma aproximada cuánta energía consumirá un sistema o componente que
use esos recursos.

#### Clasificación dinámica

La clasificación dinámica construye modelos que estiman el consumo energético a
partir de datos medidos en tiempo de ejecución —como utilización de los
recursos[^2], operaciones de entrada y salida, tráfico de red, etc.—. A
diferencia de la [clasificación estática](#clasificación-estática), la
estimación se ajusta con el tiempo a medida que se dispone de más datos
observados.

> [!TIP]
> Vean [Architecture strategies for designing a monitoring
> system](https://learn.microsoft.com/en-us/azure/well-architected/operational-excellence/observability)
> en Azure Well-Architected Framework.

#### Reducir el uso

Consiste en disminuir la cantidad de recursos[^2] activos, o el tiempo durante
el cual permanecen activos, afectando eventualmente el nivel de servicio, pero
sin llegar a niveles inaceptables.

> [!TIP]
>
> Aunque la preocupación es el costo y no la eficiencia energética, son
> aplicables los principios  [Optimize component
costs](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/optimize-component-costs)
y [Optimize environment
costs](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/optimize-environment-costs)
en Azure Well‑Architected Framework.

#### Descubrimiento

Está explicado [aquí](./2_05_05_Tacticas_facilidad_de_modificacion.md#descubrimiento).

Las consultas al –o resultados del— *discovery service* incluyen información
sobre consumo de energía.

#### Calendarizar recursos

Está explicada [aquí](./2_05_02_Tacticas_rendimiento.md#calendarizar-recursos).

Es criterio para asignar recursos busca minimizar el consumo de energía.

> [!TIP]
>
> Aunque la preocupación es el costo y no la eficiencia energética, son
> aplicables las recomendaciones para [optimizar
> ambientes](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/optimize-environment-costs)
> y [optimizar el
> escalado](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/optimize-scaling-costs)
> en Azure Well‑Architected Framework.

#### Gestionar la llegada de eventos

Está explicada [aquí](./2_05_02_Tacticas_rendimiento.md#gestionar-la-llegada-de-eventos).

#### Limitar la respuesta a eventos

Está explicada
[aquí](./2_05_02_Tacticas_rendimiento.md#limitar-la-respuesta-a-eventos).

#### Priorizar los eventos

Está explicada [aquí](./2_05_02_Tacticas_rendimiento.md#priorizar-los-eventos).

#### Reducir la sobrecarga computacional

Está explicada
[aquí](./2_05_02_Tacticas_rendimiento.md#reducir-la-sobrecarga-computacional).

#### Limitar los tiempos de ejecución

Está explicada
[aquí](./2_05_02_Tacticas_rendimiento.md#limitar-los-tiempos-de-ejecución).

#### Incrementar la eficiencia en el uso de recursos

Está explicada
[aquí](./2_05_02_Tacticas_rendimiento.md#incrementar-la-eficiencia-en-el-uso-de-recursos).
