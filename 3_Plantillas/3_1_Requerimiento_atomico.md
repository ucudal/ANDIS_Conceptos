# 3 Plantillas

## 3.1 Requerimiento atómico

Esta es la plantilla para un requerimiento funcional o no funcional. Las entradas
de la plantilla están marcadas <span style="color:#0969DA;font-weight: bold;">así</span>
y el texto a completar en el color normal. Tomado de [^1].

<table>
    <tr>
        <td td style="color:#0969DA">
            <b># Requerimiento</b>
        </td>
        <td>
            Identificador único del requerimiento
        </td>
        <td style="color:#0969DA">
            <b>Tipo del requerimiento</b>
        </td>
        <td>
            Vean debajo <span id="back_ref_1"><a href="#ref_1">↓</a></span>
        </td>
        <td td style="color:#0969DA">
            <b># Evento/Caso de uso</b>
        </td>
        <td>
            Vean debajo <span id="back_ref_2"><a href="#ref_2">↓</a></span>
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Descripción</b>
        </td>
        <td colspan="5">
            Una frase con la intención del requerimiento. Para ser consistente,
            hacerlo de la siguiente manera: "El sistema <strong>deberá <i>verbo</i></strong>...".
            Es importante siempre usar la palabra <strong>deberá</strong> y no
            otras como podrá, debería, debe, etcétera.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Justificación</b>
        </td>
        <td colspan="5">
            La razón para incluir este requerimiento
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Autor</b>
        </td>
        <td colspan="5">
            La persona que escribió este requerimiento
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Criterio de ajuste</b>
            <!-- @abadiejosse, definir si lo llamamos así o criterio de aceptación
            que es más común -->
        </td>
        <td colspan="5">
            Una medida del requerimiento de forma tal que sea posible probar que
            la solución cumple con él.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Satisfacción del cliente</b>
        </td>
        <td colspan="2">
            En qué grado la parte interesada es feliz si el requerimiento se implementa
            satisfactoriamente. La escala va de 1 —no le importa— a 5 —extremadamente
            satisfecho—.
        </td>
        <td td style="color:#0969DA">
            <b>Insatisfacción del cliente</b>
        </td>
        <td colspan="2">
            En qué medida la parte interesada es infeliz si el requerimiento no
            es parte del producto final. La escala va de 1 —no le importa— a 5
            —extremadamente disgustado—.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Prioridad</b>
        </td>
        <td colspan="5">
            Una calificación del valor de este requerimiento para los usuarios
            finales. Vean debajo <span id="back_ref_3"><a href="#ref_3">↓</a>
            </span>
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Dependencias</b>
        </td>
        <td colspan="2">
            La lista de requerimientos que tienen cierta dependencia de este
            requerimiento.
        </td>
        <td td style="color:#0969DA">
            <b>Conflictos</b>
        </td>
        <td colspan="2">
            Otros requerimientos que no podrían implementarse si se implementa
            este requerimiento.
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA">
            <b>Material de soporte</b>
        </td>
        <td colspan="5">
            Vínculos o referencias a documentos que ilustran y explican este
            requerimiento.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Historia</b>
        </td>
        <td colspan="5">
            Control de cambios.
        </td>
    </tr>
</table>

Vean además la [checklist de requerimientos](/2_Tecnicas_y_herramientas/2_1_4_Checklist_requerimientos.md).

-----
<span id="ref_1">Tipos de requerimiento</span>:

* Requerimiento funcional
* Requerimiento no funcional
* Restricción o *constraint* del proyecto
* Restricción o *constraint* de diseño
* Impulsor o *driver* del proyecto
* Cuestiones o *issues* del proyecto <a href="#back_ref_1" title="Volver...">↩︎</a>

<span id="ref_2">#Evento/Caso de uso</span>:

* Lista de identificadores de eventos o casos de uso que necesitan
este requerimiento.<a href="#back_ref_2" title="Volver...">↩︎</a>

<span id="ref_3">Prioridad</span>:

* ***Must have* —imprescindibles—**: Requerimientos críticos que el proyecto
  debe cumplir para ser considerado exitoso. Sin ellos el proyecto no cumplirá
  su propósito.

* ***Should have* —importantes—**: Requerimientos que son importantes pero no
  críticos. Su ausencia no detendrá el proyecto, pero puede afectar la calidad o
  eficiencia del resultado final.

* ***Nice to have* —deseables—**: Estos son los requerimientos que sería
  beneficioso tener, pero que no son esenciales. Mejoran la experiencia o la
  funcionalidad, pero no afectan la viabilidad del proyecto.
  <a href="#back_ref_3" title="Volver...">↩︎</a>

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
