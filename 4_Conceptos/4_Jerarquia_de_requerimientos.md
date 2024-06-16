# 4. Conceptos

## Jerarquía de requerimientos

El [contexto del
trabajo](/4_Conceptos/4_Trabajo_y_area_de_trabajo.md) es la
declaración de requisitos de más alto nivel; se descompone en el siguiente
nivel, los [eventos del negocio](/4_Conceptos/4_Evento_del_negocio.md). El nivel
debajo de los eventos del negocio comprende los [casos de uso del
producto](/4_Conceptos/4_Caso_de_uso_del_producto.md), cada uno de los cuales se
descompone en una serie de pasos de casos de uso del producto. El nivel más bajo
incluye los [requerimientos
atómicos](/3_Plantillas/3_1_Requerimiento_atomico.md), cada uno de los cuales se
puede rastrear siguiendo esta jerarquía. Los diagramas de actividad y las
historias de usuarios también se utilizan para agrupar requerimientos atómicos.
Las características son una agrupación que suelen utilizar las partes
interesadas en el marketing o la planificación de versiones de productos. Tomado
de [^1].

```mermaid
classDiagram
    class Contexto_del_trabajo
    class Evento_del_negocio
    class Caso_de_uso_del_producto
    class Historia_de_usuario
    class Paso_del_caso_de_uso
    class Característica
    class Requerimiento_atómico
    Contexto_del_trabajo --> "*" Evento_del_negocio
    Evento_del_negocio --> "*" Caso_de_uso_del_producto
    Caso_de_uso_del_producto --> "*" Paso_del_caso_de_uso
    Paso_del_caso_de_uso --> "*" Requerimiento_atómico
    Caso_de_uso_del_producto --> "*" Historia_de_usuario
    Historia_de_usuario --> "*" Requerimiento_atómico
    Característica --> "*"Requerimiento_atómico
```

Figura tomada de [^1].

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
