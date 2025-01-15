# 4 Conceptos

## Historia de usuario

Una historia de usuario describe una funcionalidad que será de valor para un
usuario o comprador de un sistema o software. Las historias de usuario se
componen de tres aspectos[^1]:

* Una descripción escrita de la historia utilizada para la planificación y como
recordatorio.

* Conversaciones sobre la historia que sirven para desarrollar los detalles de
la historia.

* Pruebas que transmiten y documentan detalles y que pueden usarse para
  determinar cuándo una historia está completa.

Las historias de usuario son una descripción informal y en lenguaje natural de
las características de un sistema de software. Están escritas desde la
perspectiva del usuario final.

Las historias de usuario se utilizan para crear estimaciones de tiempo[^2]. Las
historias de usuario solo deben proporcionar suficientes detalles para hacer una
estimación de riesgo razonablemente bajo de cuánto tiempo llevará implementar la
historia. Cuando llegue el momento de implementar la historia, los
desarrolladores acudirán al cliente y recibirán una descripción detallada de los
requerimientos cara a cara.

La estimación temprana es una diferencia clave entre las historias y otras
prácticas de requerimientos. La estimación brinda a las perspectivas técnica y
de negocio la oportunidad de interactuar, lo que crea valor desde el principio,
cuando una idea tiene el mayor potencial. Cuando el equipo conoce el costo de
las funciones, puede dividirlas, combinarlas o ampliarlas[^2].

Cada historia tendrá una estimación de 1, 2 o 3 semanas en el "tiempo de
desarrollo ideal". Este tiempo de desarrollo ideal es el tiempo que llevaría
implementar la historia en código si no hubiera distracciones ni otras tareas y
supieras exactamente qué hacer. Más de 3 semanas significa que debes desglosar
más la historia. Menos de 1 semana y estás en un nivel demasiado detallado,
combina algunas historias. Aproximadamente 80 historias de usuarios más o menos
20 es un número perfecto para crear un plan de lanzamiento durante la
planificación del lanzamiento[^2].

Algunos sugieren que las historias de usuario tengan cierto formato[^3]:

> Como [<span style="color:#0969DA">*persona*</span>],
> quiero [<span style="color:#0969DA">característica o funcionalidad</span>]
> de modo que [<span style="color:#0969DA">razón</span>]

*Persona* —ver [definición](https://www.merriam-webster.com/dictionary/persona)—
representa el rol o el usuario.

> [!TIP]
> Contesta las siguientes preguntas sobre la *persona*:
>
> * ¿Quién es este usuario?
> * ¿Qué lo motiva?
> * ¿Ejemplo de este usuario?

Lo que el usuario quiere hacer en la historia es lo que asumes que es su
objetivo e implica una característica o funcionalidad en el software. La razón
—también llamada a veces recompensa— es algo que se puede probar —demostrar—
para determinar que el usuario ha alcanzado su objetivo.

> [!TIP]
> Contesta estas preguntas sobre la recompensa:
>
> * ¿Por qué quieren hacer esto?
> * ¿Cuál es el beneficio?
> * ¿Cómo sabemos que está funcionando?

La granularidad de una historia está en algún lugar entre un [caso de uso de
producto](/4_Conceptos/4_Caso_de_uso_del_producto.md) y un [requerimiento
atómico](/3_Plantillas/3_1_Requerimiento_atomico.md)[^4].

El siguiente ejemplo de historia de usuario está tomado de [^4]:

El primer paso de un caso de uso de negocio para un banco dice lo siguiente:

> El banco quiere evitar que los clientes sobregiren inesperadamente sus
> cuentas bancarias. La sanción por sobregiros no concertados, si bien es
> rentable, está provocando disputas con los clientes que afirman que necesitan
> una mejor forma de controlar sus cuentas.

Una primera historia de usuario para esto sería así:

> Como titular de una cuenta bancaria, quiero consultar mi saldo en línea.

La pregunta que nos está faltando hacer sería ¿por qué el titular quiere
consultar el saldo?

La historia de usuario revisada luce así:

> Como titular de una cuenta bancaria, quiero consultar mi saldo en línea para
> poder acceder a mi saldo diario las 24 horas del día.

Pero esa no es la verdadera razón: el titular está tratando de evitar un
sobregiro; teniendo eso en cuenta, una nueva versión de la historia de usuario
podría ser así:

> Como titular de una cuenta bancaria, quiero que me informen si se prevé que mi
> saldo mensual llegue a cero o menos para poder organizar un sobregiro.

Esta historia de usuario se puede escribir usando la plantilla de [requerimiento
atómico](/3_Plantillas/3_1_Requerimiento_atomico.md):

<table>
    <tr>
        <td td style="color:#0969DA">
            <b># Historia de usuario</b>
        </td>
        <td>
            6.1
        </td>
        <td style="color:#0969DA">
            <b>Tipo del requerimiento</b>
        </td>
        <td>
            Historia de usuario
        </td>
        <td td style="color:#0969DA">
            <b># Evento/Caso de uso del negocio</b>
        </td>
        <td>
            6</span>
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Descripción</b>
        </td>
        <td colspan="5">
            Como titular de una cuenta bancaria, quiero que me informen si se
            prevé que mi saldo mensual llegue a cero o menos.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Justificación</b>
        </td>
        <td colspan="5">
            Para poder organizar un sobregiro.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Fuente</b>
        </td>
        <td colspan="5">
            Discusión del BUC 6 con representantes del negocio y los
            desarrolladores.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Criterio de ajuste</b>
        </td>
        <td colspan="5">
            Balance a fin de mes proyectado = balance el primer día del mes +
            salario del mes - suma de los débitos del mes. Si el balance al
            fin de mes es menor o igual a cero enviar una alerta al titular de
            la cuenta.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Satisfacción del cliente</b>
        </td>
        <td colspan="2">
            3
        </td>
        <td td style="color:#0969DA">
            <b>Insatisfacción del cliente</b>
        </td>
        <td colspan="2">
            5
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Prioridad</b>
        </td>
        <td colspan="5">
            1
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Dependencias</b>
        </td>
        <td colspan="2">
            Ninguna
        </td>
        <td td style="color:#0969DA">
            <b>Conflictos</b>
        </td>
        <td colspan="2">
            Ninguno.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Material de soporte</b>
        </td>
        <td colspan="5">
            Reglas de sobregiro provistas por los representantes del negocio.
        </td>
    </tr>
    <tr>
        <td td style="color:#0969DA">
            <b>Historia</b>
        </td>
        <td colspan="5">
            Versión inicial.
        </td>
    </tr>
</table>

Las historias de usuario pueden ser agrupadas en épicas —*epics*—, o dicho de
otro modo, las épicas de descomponen en historias de usuario. Pueden tener el
mismo formato que las historias de usuario aunque con una granularidad mucho
menor, o dicho de otro modo, con un alcanza mucho mayor.

[^1]: Cohn, M. (2004). User Stories Applied: For Agile Software Development.
Addison-Wesley Professional.
[^2]: Beck, K. & Andres, C. (2004). Extreme Programming Explained: Embrace
    Change, 2<sup>nd</sup> Edition. Addison-Wesley.
[^3]: Cowan, A. (2014). Your Best Agile User Story.
    https://www.alexandercowan.com/best-agile-user-story/
[^4]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
