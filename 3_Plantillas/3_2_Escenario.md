# 3 Plantillas

## 3.2 Escenarios

Esta es la plantilla para el escenario de un caso de uso del negocio o de un
caso de uso del producto. Las entradas
de la plantilla están marcadas <span style="color:#0969DA;font-weight: bold;">así</span>
y el texto a completar en el color normal. Tomado de [^1].

Los escenarios muestran la funcionalidad de un caso de uso dividiéndolo en una
serie de pasos fácilmente reconocibles, escritos en lenguaje natural para que
sean accesibles para todos los interesados.

<style>
 td {
   vertical-align: top;
 }
 </style>
<table>
    <tr>
        <td td style="color:#0969DA">
            <b>Nombre del caso de uso del {negocio|producto}</b>
        </td>
        <td>
            Un nombre significativo para el caso de uso.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Desencadenante —<i>trigger</i>—</b>
        </td>
        <td>
            El mecanismo por el cual se inicia el caso de uso. Habitualmente
            consiste en datos o un evento que llega desde fuera del area de
            trabajo. También puede ser cada cierto tiempo o después de cierto
            tiempo de ocurrido otro evento.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Precondiciones</b>
        </td>
        <td>
            Estado en el que tiene que estar el
            <a href="/4_Conceptos/4_Trabajo_y_area_de_trabajo.md">trabajo</a>
            al inicio del caso de uso. Habitualmente implica que otros casos de
            uso debieron ocurrir antes para que este caso de uso tenga sentido.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Partes interesadas</b>
        </td>
        <td>
            Las personas que tienen interés en el resultado del caso de uso —que
            serán afectadas por la forma en que se haga el trabajo y por los
            datos que produzca—.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Actores</b>
        </td>
        <td>
            Las personas o sistemas que hacen el trabajo en el caso de uso.
            Habitualmente uno de los actores desencadena el caso de uso y los
            demás participan en él.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Pasos del caso normal</b>
        </td>
        <td>
            Una secuencia paso a paso, en lenguaje natural, sin sesgo
            tecnológico, de lo que ocurre en el caso de uso cuando transcurre
            sin inconvenientes. La secuencia de pasos se numera de 1 en
            adelante.
            </br>
            Para el caso normal, las alternativas y las excepciones es posible
            usar <a href="/2_Tecnicas_y_herramientas/2_4_1_Diagramas_de_actividades_UML.md">
            diagramas de actividades</a> o un <a href="/2_Tecnicas_y_herramientas/2_4_4_Diagramas_BMPN.md">
            diagrama BPMN</a>.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Alternativas</b>
        </td>
        <td>
            Aparecen cuando el usuario tiene intencionalmente la posibilidad de
            elegir diferentes acciones en uno de los pasos del caso normal.
            Cada alternativa se numera de 1 en adelante, anteponiendo la letra
            <code>A</code> y el número del paso del caso normal donde aparece la
            alternativa.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Excepciones</b>
        </td>
        <td>
            Desvíos indeseados pero inevitables del caso normal. Cada excepción
            se numera de 1 en adelante, anteponiendo la letra <code>E</code> y
            el número de paso del caso normal donde puede ocurrir la excepción.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Resultado</b>
        </td>
        <td>
            La situación deseada cuando el caso de uso termina de forma exitosa.
        </td>
    </tr>
</table>

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
