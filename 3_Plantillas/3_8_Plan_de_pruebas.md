# 3 Plantillas

## 3.8 Plan de pruebas

Esta es la plantilla para el plan de pruebas. Las entradas obligatorias de la
plantilla están marcadas <span style="color:#0969DA;font-weight:
bold;">así</span> y las demás entradas y el texto a completar en el color
normal.

<table>
    <tr>
        <td style="color:#0969DA" valign="top">
            <b>Alcance</b>
        </td>
        <td>
            Describe qué es lo que se está probando del proyecto, por ejemplo,
            las funcionalidades de un producto, las interfaces con otros
            productos o servicios, o la integración con otros productos o
            servicios.
            <br>
            <br>
            A cada uno de los elementos que se van a probar nos referiremos como
            un componente de las pruebas.
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA" valign="top">
            <b>Estrategia</b>
        </td>
        <td>
            Describe en qué consisten las pruebas a realizar. Para cada <a
            href="/4_Conceptos/4_Epica.md">épica</a> —o grupo de
            funcionalidades—, especifica los
            <a href="/4_Conceptos/4_Enfoques_de_pruebas.md">enfoques</a> de las
            pruebas, los <a href="/4_Conceptos/4_Tipos_de_pruebas.md">tipos</a>
            de pruebas, y la automatización —o no— de las pruebas, que garantiza
            que estos grupos de funcionalidades sean probados adecuadamente.
            Especifica las principales actividades, técnicas y herramientas que
            se utilizan para probar lo que se haya incluido en el alcance.
            <br>
            <br>
            La estrategia se debe describir con suficiente detalle como para
            permitir la identificación de las principales tareas de prueba y la
            estimación del tiempo necesario para realizar cada una.
            <br>
            <br>
            De aquí se derivan luego los casos de prueba que se documentan en
            <a href=
            "/3_Plantillas/3_4_Casos_de_prueba_de_usuario_final.md">esta</a>
            plantilla, o que se cargan en la herramienta de automatización
            de pruebas <a
            href="https://learn.microsoft.com/en-us/azure/devops/test/?view=azure-devops">
            Azure Test Plans</a> disponible como parte de la suscripción a
            <a href=ref="https://azure.microsoft.com/es-es/products/devops">Azure
            Devops Services</a> a la que tienen acceso con la cuenta de
            estudiante@correo.ucu.edu.uy.
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA" valign="top">
            <b>Ambientes</b>
        </td>
        <td>
            Describe los ambientes que serán usados para las pruebas. Puede
            haber uno o más de un ambiente para diferentes estrategias de
            prueba.
        </td>
    </tr>
    <tr>
        <td valign="top">
            Calendario
        </td>
        <td>
            Define cuándo se completan los diferentes casos de pruebas.
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA" valign="top">
            <b>Reporte de problemas</b>
        </td>
        <td>
            Indica qué ocurre cuando se encuentran errores en alguna de las
            pruebas, por ejemplo, cómo y dónde se crean los tiques para que se
            corrijan esos errores, cómo se priorizan los tiques, etc.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Funcionalidades a probar</b>
        </td>
        <td>
            Identifica todas las funcionalidades del software que se van a
            probar. Es opcional en la medida de que sea redundante con lo
            indicado en la sección de alcance.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Funcionalidades fuera de alcance de las pruebas</b>
        </td>
        <td>
            Identifica todas las funcionalidades que no se van a probar y las
            razones para ello.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Roles y responsabilidades</b>
        </td>
        <td>
            Especifica los miembros del equipo o del cliente que participan en
            las pruebas y cuáles serán sus funciones. Identifica las personas
            responsables de gestionar, diseñar, preparar, ejecutar y resolver
            las actividades de prueba, así como los problemas relacionados.
            También identifica los responsables de proporcionar los ambientes de
            prueba.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Dependencias</b>
        </td>
        <td>
            Identifica limitaciones importantes en las pruebas, como la
            disponibilidad de elementos de prueba, disponibilidad de recursos de
            prueba y plazos.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Riesgos y suposiciones</b>
        </td>
        <td>
            Identifica los supuestos de alto riesgo del plan de pruebas y
            especifica planes de contingencia para cada uno.
        </td>
    </tr>
    <tr>
        <td valign="top">
            <b>Herramientas</b>
        </td>
        <td>
            Enumera las herramientas de automatización que va a utilizar y
            también la herramienta de tiques de errores.
        </td>
    </tr>
</table>
