# 3 Plantillas

## 3.17 Eventos del negocio

Esta es la plantilla para mostrar la lista de [eventos del
negocio](/4_Conceptos/4_Evento_del_negocio.md) con los respectivos datos de
entrada y de salida. Agreguen tantas filas como eventos del negocio haya en su
proyecto.

<table>
    <tr>
        <td style="color:#0969DA">
            <b>Nombre del evento</b>
        </td>
        <td style="color:#0969DA">
            <b>Entradas y salidas</b>
        </td>
    </tr>
    <tr>
        <td style="vertical-align: top;">
            Evento #1
        </td>
        <td>
            Entrada #1 del evento #1 [in]
            <br>
            Entrada #2 del evento #1 [in]
            <br>
            ...
            <br>
            Salida #1 del evento #1 [out]
            <br>
            Salida #2 del evento #1 [out]
            <br>
            ...
        </td>
    </tr>
    <tr>
        <td style="vertical-align: top;">
            Evento #2
        </td>
        <td>
            Entrada #1 del evento #2 [in]
            <br>
            Entrada #2 del evento #2 [in]
            <br>
            ...
            <br>
            Salida #1 del evento #2 [out]
            <br>
            Salida #2 del evento #2 [out]
            <br>
            ...
        </td>
    </tr>
    <tr>
        <td style="vertical-align: top;">...</td>
        <td>...</td>
    </tr>
</table>

Un ejemplo de eventos del negocio, correspondiente al siguiente diagrama de
contexto de la [Figura 1](#figura-1), aparece luego, en la [Tabla 1](#tabla-1):

<span id="figura-1"/>

![Ejemplo de diagrama de contexto](/diagrams/Context_Diagram_Example.svg)

*Figura 1: Ejemplo de un diagrama de contexto.*

*Tabla 1: Ejemplo de eventos del negocio.*

<a id="tabla-1"/>

<table>
    <tr>
        <td style="color:#0969DA">
            <b>Nombre del evento</b>
        </td>
        <td style="color:#0969DA">
            <b>Entradas y salidas</b>
        </td>
    </tr>
    <tr>
        <td style="vertical-align: top">
            Anunciante contrata publicidad
        </td>
        <td>
            Pagos [in]
            <br>
            Slots de publicidad [out]
        </td>
    </tr>
    <tr>
        <td>
            Usuario ingresa a la comunidad
        </td>
        <td>
            Perfil para registro [in]
        </td>
    </tr>
    <tr>
        <td>
            Usuario consume contenido
        </td>
        <td>
            Contenido [out]
        </td>
    </tr>
    <tr>
        <td style="vertical-align: top">
            Creador de contenido publica contenido
        </td>
        <td>
            Contenido [in]
            <br>
            Compensación [out]
        </td>
    </tr>
</table>
