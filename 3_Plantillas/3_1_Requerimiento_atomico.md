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
            Ver debajo[^2]
        </td>
        <td td style="color:#0969DA">
            <b># Evento/Caso de uso</b>
        </td>
        <td>
            Ver debajo[^3]
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Descripción</b>
        </td>
        <td colspan="5">
            Una frase con la intención del requerimiento
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
            <b>Criterio de ajuste</b>
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
        <td td style="color:#0969DA">
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

[^1] Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.

[^2] Tipos de requerimiento:

- Requerimiento funcional
- Requerimiento no funcional
- Restricción o *constraint* del proyecto
- Restricción o *constraint* de diseño
- Impulsor o *driver* del proyecto
- Cuestiones o *issues* del proyecto

[^3] Lista de identificadores de eventos o casos de uso que necesitan este requerimiento
