# 3 Plantillas

## 3.4 Casos de prueba de usuario final

Esta es la plantilla para documentar los casos de prueba. El producto a probar
es la aplicación desplegada en un ambiente de prueba. Aunque la redacción puede
implicar una [prueba de aceptación de usuario
final](/4_Conceptos/4_Tipos_de_pruebas.md), esta plantilla también puede ser
utilizada también para escribir el guión de otros tipos de pruebas.

Los casos de prueba están agrupados en esta plantilla por módulos. En este
contexto un módulo puede ser un [caso de uso del
producto](/4_Conceptos/4_Caso_de_uso_del_producto.md) o una
[épica](/4_Conceptos/4_Epica.md).

En lugar de esta plantilla pueden utilizar la herramienta de automatización de
pruebas [Azure Test
Plans](https://learn.microsoft.com/en-us/azure/devops/test/?view=azure-devops)
disponible como parte de la suscripción a [Azure Devops
Services](https://azure.microsoft.com/es-es/products/devops) a la que tienen
acceso con la cuenta de estudiante @correo.ucu.edu.uy

<!-- TODO: Revisar si es aplicable a todos los tipos de pruebas y adaptarlo para que
lo sea. -->

<table>
    <tr>
        <td style="color:#0969DA">
            <b>Módulo</b>
        </td>
        <td colspan=3>
            Nombre del módulo
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA">
            <b>Estado inicial</b>
        </td>
        <td colspan=3>
            Describir en qué estado debe estar la aplicación antes de iniciar
            este caso de prueba ‑por ejemplo, si hay que importar o cargar
            ciertos datos; o navegar hacia cierta pantalla, página o ventana de
            la aplicación‑; y si es necesario o no volver a ese estado al final
            de cada uno de los casos a continuación.
        </td>
    </tr>
    <tr>
        <td style="color:#0969DA">
            <b>Número</b>
        </td>
        <td td style="color:#0969DA">
            <b>Descripción</b>
        </td>
        <td td style="color:#0969DA">
            <b>Procedimiento</b>
        </td>
        <td td style="color:#0969DA">
            <b>Resultados esperados</b>
        </td>
    </tr>
    <tr>
        <td style="text-align: center">
            #1
        </td>
        <td width="30%">
            Descripción del caso de prueba #1
        </td>
        <td width="30%">
            Pasos que el usuario debe realizar durante la prueba del caso #1.
        </td>
        <td width="30%">
            Resultado esperado en cada uno de los pasos del caso #1.
        </td>
    </tr>
    <tr>
        <td style="text-align: center">
            #2
        </td>
        <td>
            Descripción del caso de prueba #2
        </td>
        <td>
            Pasos que el usuario debe realizar durante la prueba del caso #2.
        </td>
        <td>
            Resultado esperado en cada uno de los pasos del caso #2.
        </td>
    </tr>
    <tr>
        <td style="text-align: center">
            ...
        </td>
        <td>
            ...
        </td>
        <td>
            ...
        </td>
        <td>
            ...
        </td>
    </tr>
</table>
