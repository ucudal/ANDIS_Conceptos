
# 2 Técnicas y herramientas

## 2.9 Evaluación de la arquitectura

### 2.9.1 *Lightweight ATAM* -o ATAM ligero—

> [!TIP]
> Ver también [ATAM](./2_9_1_ATAM.md).

La concepción tradicional de evaluar la arquitectura una vez que está
"terminada" resulta inadecuada para las metodologías actuales de desarrollo de
software. Hoy en día, las organizaciones predominantemente implementan enfoques
ágiles o iterativos, donde no existe una fase arquitectónica única y delimitada.
En su lugar, la arquitectura y el desarrollo se construyen simultáneamente
mediante ciclos continuos.

Este enfoque ágil concibe la arquitectura como una entidad en evolución
continua, abordándose mediante incrementos pequeños y enfocándose en mitigar los
riesgos más críticos. Esto se materializa desarrollando prototipos, pruebas de
concepto, o productos mínimos viables.

Para adaptarse a este enfoque de desarrollo, se ha diseñado una versión
modificada del ATAM: *Lightweight ATAM* —o ATAM ligero—. Esta variante mantiene
la estructura metodológica original, pero reduce su alcance y duración. A
diferencia del ATAM completo, que involucra varias fases con grupos de
interesados internos y externos, el *Lightweight ATAM* comprende una única fase
de análisis que puede ejecutarse en aproximadamente medio día.

Este documento está basado en [^1].

[^1]: Cervantes, H.; Kazman, R. (2024). Designing Software Architectures,
    2<sup>nd</sup> Edition. Addison-Wesley.

La flexibilidad de *Lightweight ATAM* permite su implementación con recursos
internos del proyecto, reconociendo que aunque una revisión externa aporta mayor
objetividad, puede resultar prohibitiva. Representa así un punto medio
equilibrado entre un análisis exhaustivo costoso y la ausencia total de
evaluación sistemática.

| Paso | Tiempo | Notas|
| ---- | :----: | ---- |
| 1. Presentar directrices de negocio | ½ hora | Se espera que los participantes comprendan el sistema, sus objetivos comerciales y sus prioridades. Se destinan quince minutos a una breve revisión para garantizar que todos tengan estos conceptos presentes y que no haya sorpresas |
| 2. Presentar la arquitectura | ½ hora | Se espera que todos los participantes estén familiarizados con el sistema, por lo que se presenta una breve descripción general de la arquitectura y se trazan 1 o 2 escenarios a través de las vistas de arquitectura documentadas |
| 3. Identificar los enfoques arquitectónicos | ¼ hora | El arquitecto identifica los enfoques arquitectónicos para las preocupaciones específicas sobre los atributos de calidad. Esto puede hacerse como parte del paso 2. |
| 4. Generar el árbol de utilidad de atributos de calidad | ½ hora |  Es posible que ya existan escenarios; si es así, utilízalos. Es posible que ya exista un árbol de utilidades; si es así, el equipo lo revisa y lo actualiza, si es necesario |
| 5. Analizar los enfoques arquitectónicos | 2 horas | Este paso —mapear los escenarios de alto rango en la arquitectura— consume la mayor parte del tiempo y se puede expandir o contraer según sea necesario |
| 6. Presentar los resultados | ½ hora | Al final de la evaluación, el equipo revisa los riesgos y las compensaciones existentes y recientemente descubiertos y analiza las prioridades |
| Total | 4 horas| |

Una evaluación de medio día de este tipo presenta una dedicación de esfuerzo
comparable a otras actividades habituales de aseguramiento de calidad en
proyectos de desarrollo, tales como revisiones de código o inspecciones. Esta
similitud facilita la integración de una sesión de *Lightweight ATAM* dentro de
un *sprint*, especialmente en aquellas iteraciones donde se generan, cuestionan
o ajustan decisiones inherentes a la arquitectura.
