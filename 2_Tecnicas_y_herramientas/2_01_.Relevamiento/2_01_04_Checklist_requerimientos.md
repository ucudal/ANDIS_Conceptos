# 2 Técnicas y herramientas

## 2.1 Relevamiento

### 2.1.4 Checklist requerimientos

La siguiente lista de verificación ‑basada en [^1] y [^2]‑ incluye una serie de
ítems que pueden ser usados para comprobar los requerimientos.

[^1]: ISO/IEC/IEEE. (2018). ISO/IEC/IEEE 29148:2018 Systems and software
   engineering‑Life cycle processes‑Requirements engineering. Parcialmente
   disponible
   [aquí](https://www.iso.org/obp/ui/en/#iso:std:iso-iec-ieee:29148:ed-2:v1:en).

[^2]: NASA. (2019). System Engineering Handbook‑Appendix C: How to Write a Good
    Requirement. Disponible
    [aquí](https://www.nasa.gov/reference/system-engineering-handbook-appendix/#hds-sidebar-nav-3).

1. **Necesario**: Todo requerimiento representa una necesidad fundamental ‑en el
   sentido de que si falta provocará una deficiencia‑ que no puede ser sustituida
   por otras capacidades o funcionalidades.

2. **No ambiguo**: Debe tener una única interpretación. Que el requerimiento sea
   claro, conciso y fácil de entender contribuye a lograr que no sea ambiguo.
   Ten en cuenta las siguientes causas de ambigüedad en los requerimientos[^3]:

   * Uso incorrecto de [homónimos](https://www.rae.es/dpd/homónimo): en
     particular en idioma español hay palabras que se pronuncian como otras que
     tienen un significado muy distante; por ejemplo, "vaca" es un animal y
     "baca" es un porta equipaje en el techo de un auto; o "aya" que es una
     niñera y "haya" es un árbol.

   * Uso incorrecto de signos ortográficos: especialmente una coma fuera de
     lugar puede cambiar completamente el sentido de una oración; por ejemplo
     "solicito programador inútil, presentarse sin referencias" versus "solicito
     programador, inútil presentarse sin referencias".

   * Lenguaje impreciso o vago: términos como "rápido", "eficiente" o "amigable"
     sin definiciones específicas pueden ser interpretados de diferente forma
     por diferentes interesados.

   * Uso de sinónimos: el idioma tiene diferentes términos para referirse al
     mismo concepto; también hay veces en los que algunos términos se utilizan
     como sinónimos [cuando no lo son](https://www.rae.es/dpd/sinónimo).

   * Uso de polisémicos: el idioma tiene términos que pueden tener diferentes
     significados.

   * Omisión de información: detalles importantes que no se incluyen en la
     documentación.

   * Suposiciones: asunciones implícitas —es decir— que no se incluyen como
     parte del requerimiento.

   * Falta de contexto: puede dificultar la compresión pero también empeorar
     algunos de los problemas anteriores.

[^3]: Varios de estos problemas están listados y explicados
    [aquí](https://www.rae.es/libro-estilo-justicia/problemas-de-significado-y-sentido);
    aunque el artículo está escrito en el contexto legal, varios de sus
    conceptos son aplicables.

3. **Completo**: Debe contener toda la información necesaria para su
   entendimiento y cumplimiento. Contribuye a alcanzar este punto el uso de la
   plantilla de [requerimiento
   atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) cuando se completan
   todos los componentes de forma correcta.

4. **Consistente**: Debe estar alineado con otros requerimientos y no debe
   contradecirse a sí mismo. Además debe usar el mismo vocabulario que los
   [interesados](/4_Conceptos/4_Interesado.md).

5. **Correcto**: Debe estar libre de errores ortográficos o gramaticales y los
   supuestos deben estar confirmados.

6. **Factible**: Debe ser posible de cumplir técnicamente y dentro de los
   límites de la tecnología; se ajusta a las restricciones ‑por ejemplo de
   costo, de calendario, legales, de regulaciones, etc.‑ con un riesgo
   aceptable.

7. **Verificable**: Debe ser posible demostrar que el requerimiento ha sido
   cumplido mediante pruebas, inspecciones u otros métodos. El componente
   **criterio de ajuste** de la plantilla de [requerimiento
   atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) está relacionado con
   este punto.

8. **Rastreable**: Debe ser posible rastrear su origen y su relación con otros
    requerimientos o partes del sistema. El componente **material de soporte**
   de la plantilla de [requerimiento
   atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) está relacionado con
   este punto.

9. **Aislado**: Debe representar un solo hecho o idea, no combinar múltiples
   necesidades en una sola frase.

10. **Clasificable por prioridad**: Debe poder ser ordenado en términos de
   importancia o prioridad relativa. El componente **prioridad** de la plantilla
   de [requerimiento atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) está
   relacionado con este punto.

11. **Modificable**: Debe estar escrito de tal manera que permita cambios en su
   formulación sin perder su coherencia y claridad.

#### SMART

A veces se suele simplificar la lista de verificación anterior y usar un
subconjunto de los ítems que se recuerdan con
[mnemotecnia](https://dle.rae.es/mnemotecnia) gracias al
[acrónimo](https://dle.rae.es/acrónimo) *SMART* —inteligente en inglés—. El
acrónimo significa que el requerimiento debe ser:

* ***Specific* o específico**. Claro y preciso, evitando la ambigüedad.
  Corresponde con **no-ambiguo** —ítem 2— de la lista de verificación.

* ***Measurable* o medible**. Posible de cuantificar o de evaluar el
  cumplimiento. Corresponde con **verificable** —ítem 7— de la lista de
  verificación.

* ***Achievable* o alcanzable**. Realista y posible de lograr, considerando los
  recursos y limitaciones. Corresponde con **factible** —ítem 6— de la lista de
  verificación.

* ***Relevant* o relevante**. Alineado con los objetivos generales y ser
  importante para la organización o el individuo. Corresponde con **necesario**
  —ítem 1— de la lista de verificación.

* ***Time-bound* o con límite de tiempo**. Debe tener una fecha límite o un
  período de tiempo definido para su cumplimiento. No hay una correspondencia
  exacta con ningún ítem de la lista de verificación —y esta es una de las
  razones por la cual preferimos usar la lista y no el acrónimo—, aunque el
  hecho de que el requerimiento sea **completo** —ítem 3—, **consistente** —ítem
  4— y **correcto** —ítem 5— definitivamente ayuda a que se pueda implementar a
  tiempo, al evitar el trabajo derivado de requerimientos incompletos,
  inconsistentes o incorrectos.
