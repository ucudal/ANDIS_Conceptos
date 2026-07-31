# 4 Conceptos

## Eficiencia energética

La energía usada por las computadoras hasta hace un tiempo no era una
preocupación arquitectónica: el costo de la energía no era relevante y la
disponibilidad era ilimitada. Hoy en día hay dispositivos de
[IoT](https://www.ibm.com/think/topics/internet-of-things) cuyas baterías tienen
que durar años, teléfonos móviles o dispositivos *wearables* que preferimos
cargar cada varios días, y centros de cómputo que consumen tanta energía como
ciudades enteras. El consumo de energía pasó a ser un tema a considerar y la
eficiencia energética uno más de los atributos de calidad que la arquitectura de
software debe satisfacer.

<!-- Por IoT se puede mencionar LoRaWAN, NB-IoT o Sigfox -->

La eficiencia energética es un atributo de la calidad de una arquitectura de
software que define la capacidad de un sistema o componente para cumplir con sus
funciones utilizando la menor cantidad posible de energía, dentro de
restricciones de tiempo, costo y calidad dados[^1].

[^1]: Bass, L.; Clements, P.; Kazman, R. (2022). Software Architecture in
    Practice, 4th edition. Addison-Wesley.

El modelo de calidad de la norma ISO/IEC 25010[^2] no define un atributo de
calidad específico para la eficiencia energética; sin embargo, el atributo de
[eficiencia de
desempeño](https://github.com/ucudal/ANDIS_Conceptos/blob/main/4_Conceptos/4_Atributo_de_calidad.md#eficiencia-de-desempe%C3%B1o)
incluye la sub‑característica [utilización de
recursos](https://github.com/ucudal/ANDIS_Conceptos/blob/main/4_Conceptos/4_Atributo_de_calidad.md#utilizaci%C3%B3n-de-recursos),
que contempla potencia y energía entre esos recursos.

[^2]: ISO/IEC 25010. (2023). ISO/IEC 25010:2023, Systems and software
    engineering‑Systems and software Quality Requirements and Evaluation
    (SQuaRE) ‑ System and software quality models.

En la práctica, mejorar la eficiencia energética implica tomar decisiones
arquitectónicas sobre cómo se usan los recursos de cómputo —CPU, memoria,
almacenamiento, red, etc.— en el tiempo y en el espacio[^3].

[^3]: En el tiempo, porque la energía no cuesta lo mismo en todos los momentos
    —suele ser más barata cuando hay menos consumo, típicamente en la noche—; y
    en el espacio, porque no cuesta lo mismo —o no tiene el mismo impacto en la
    sostenibilidad— en todos lados —según sea mayor el componente de fuentes
    renovables en la energía—.

En el caso de la computación en la nube, el atributo de eficiencia energética de
[^1] está relacionado con la sustentabilidad, tanto en AWS como en Azure.
Mientras que en el primero es uno de los pilares del AWS Well-Architected
Framework[^4], en el segundo es un tema transversal a los diferentes *workloads*
mencionados en Azure Well-Architected Framework[^5]. En este contexto, además,
la eficiencia energética también está vinculada con el pilar de optimización de
costos en el Well-Architected Framework[^6].

[^4]: Amazon. (2026). Sustainability. Disponible
    [aquí](https://docs.aws.amazon.com/wellarchitected/latest/framework/sustainability.html).
[^5]: Microsoft. (2026). Sustainable workloads on Azure. Disponible
    [aquí](https://learn.microsoft.com/en-us/azure/well-architected/sustainability/overview).
[^6]: Microsoft. (2023). Cost optimization design principles. Disponible
    [aquí](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/principles).

Muchas recomendaciones para optimizar costos en [^6], tales como
dimensionamiento adecuado, apagado de entornos ociosos, auto-escalado, uso de
servicios administrados eficientes, etc., pueden verse como tácticas de
eficiencia energética, aunque no todo ahorro de costo implica necesariamente
menor consumo de energía: por ejemplo, elegir una región más barata pero donde
la energía provenga de fuentes menos sustentables. Sin embargo, no todo ahorro
de costo implica necesariamente un menor consumo de energía: por ejemplo, elegir
una región más barata pero donde la energía provenga de fuentes fósiles.

### Algunos elementos relacionados con la eficiencia energética

* **Consumo energético por unidad de procesamiento**. Es la cantidad de energía
  requerida por un sistema o componente para procesar una solicitud[^7]. Puede
  expresarse en [Joules](https://en.wikipedia.org/wiki/Joule) o
  [kWh](https://en.wikipedia.org/wiki/Kilowatt-hour) por unidad de
  procesamiento.

* **Consumo energético por unidad de tiempo**. Es la potencia promedio consumida
  por un sistema o componente durante un período de tiempo, en distintos modos
  de operación: pico, valle, standby, etc. Se mide en
  [Watts](https://en.wikipedia.org/wiki/Watt).

* **Huella de carbono asociada**. Es la estimación de las emisiones de gases de
  efecto invernadero asociadas al uso de la infraestructura en la que se ejecuta
  el sistema o componente por unidad de procesamiento o de tiempo. Típicamente
  se expresa en CO₂e o CO₂ equivalente.

* **Utilización de recursos y energía**. Es la relación entre cuánto recurso de
  cómputo —procesador, memoria, disco, red, etc.— se utiliza con
  respecto a cuánto se tiene disponible; y cómo esa utilización se traduce en
  consumo energético. Arquitecturas que mantienen recursos infrautilizados
  tienden a ser ineficientes en cuanto a la energía.

[^7]: En este contexto una solicitud es un mensaje o una invocación que da
    inicio a una unidad de trabajo, una transacción, el entrenamiento de un
    modelo, etc.

### Tácticas para eficiencia energética

El catalizador del escenario de eficiencia energética es el deseo de conservar o
gestionar la energía y a la vez proveer —eventualmente parte de— la
funcionalidad requerida. El escenario es satisfactorio si las respuestas
relacionadas con la energía se alcanzan dentro de restricciones de tiempo, costo
y calidad dados.

La eficiencia energética es esencialmente la utilización efectiva de recursos y
las tácticas se agrupan en monitoreo de recursos, asignación de recursos y
adaptación de recursos:

* Medición

* Clasificación estática

* Clasificación dinámica

* Reducción del uso

* Descubrimiento

* Calendarización de recursos

* Reducción de la demanda de recursos

> [!TIP]
> Vean más información sobre las tácticas para eficiencia energética
> [aquí](/2_Tecnicas_y_herramientas/2_05_.Tacticas_arquitectura/2_05_07_Tacticas_eficiencia_energetica.md).

### Patrones para la eficiencia energética

> [!TIP]
> Vean [Cloud design patterns that support cost
> optimization](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/design-patterns)
> y
> [Sustainability](https://learn.microsoft.com/en-us/azure/well-architected/sustainability/overview)
> en Azure Well Architected Framework.
