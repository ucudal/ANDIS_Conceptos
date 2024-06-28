# 1 Entregable del proyecto

## 1.1 Requisitos

### 1.1.4 Requerimientos no funcionales

En esta cuarta parte deben definir todos los diferentes tipos de requerimientos
no funcionales que apliquen a su proyecto. Para ello, deben usar la [plantilla
de requerimiento atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) en cada
requerimiento.

Tengan en cuenta que no todos los requerimientos no funcionales mencionados aquí
necesariamente aplican, así que deben ser prudentes y analizar cuáles sí son
necesarios, así como cuáles no.

## Requerimientos de apariencia

<!-- SECCIÓN: Requerimientos de apariencia -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

No todos los proyectos tratan de un producto que necesita una interfaz de
usuario, pero en el caso de que su producto a desarrollar sí la necesite,
detallar los requerimientos asociados a la apariencia del sistema, por ejemplo:
guías de UX/UI a utilizar —quizá brindadas por el cliente—, marca corporativa de
la organización cliente, qué colores utilizar, etcétera.

## Requerimientos de usabilidad y humanidad

<!-- SECCIÓN: Requerimientos de facilidad de uso -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

Similarmente a los requerimientos de apariencia, en caso de que el producto a
desarrollar necesite de algún tipo de interacción con los usuarios finales,
detallar los requerimientos del cliente en cuanto a la facilidad de uso del
sistema por parte de estos usuarios finales. Tengan en cuenta que esta facilidad
es derivada de la habilidad de los previstos usuarios finales y la complejidad
del producto y sus funcionalidades. Algunas características a tener en cuenta
pueden ser:

<!-- TODO Agregar ejemplos de cada tipo de requisito incluyendo además criterio
de aceptación -->

* Eficiencia de uso: Qué tan rápido o con qué precisión el usuario puede usar el
  producto.
* Facilidad de memorización: Qué tanto se espera que el usuario casual memorice
  en cuanto a usar el producto.
* Tasa de errores: Qué tantos errores sería aceptable que el usuario cometa.
  Para algunos productos, es crucial que el usuario cometa muy pocos errores, o
  en ocasiones, ninguno.
* Satisfacción general al usar el producto: Para productos que tienen cierta
  competencia, es esencial que los usuarios se sientan muy satisfechos al usar
  el producto. De ser el caso, es valioso registrar esto como un requerimiento.
* Retroalimentación: Qué tanta retroalimentación el usuario necesita para
  sentirse confiado en cuanto a que el producto está haciendo precisa y
  correctamente lo que se espera de él. Productos de seguridad o tareas críticas
  suelen necesitar un alto nivel de retroalimentación.

<!-- SECCIÓN: Requerimientos de aprendizaje -->
Siguiendo el punto anterior, también detallar las expectativas del cliente en
cuanto a qué tanto esfuerzo deberán emplear los usuarios finales para poder
utilizar el sistema de una forma productiva. Algunos sistemas deben ser muy
fáciles de utilizar y por ende intuitivos, otros se pueden permitir determinada
curva de aprendizaje debido a la complejidad del problema. La idea aquí es
cuantificar la cantidad de tiempo o esfuerzo que los usuarios finales necesitan
para aprender a usar el sistema y que esta cuantificación sea aceptable para el
cliente. Esta clarificación puede incluir un plan de capacitación para los
usuarios, e incluso un manual de usuario, por ejemplo: "Los usuarios deberán ser
capaces de usar el sistema tras una semana de capacitación" o, "Los usuarios
deberán ser capaces de utilizar el sistema tras leer el manual de usuario".

<!-- SECCIÓN: Requerimientos de personalización e internacionalización -->
En caso de que sea establecido por el cliente como una necesidad, especificar
los requerimientos asociados a las preferencias de los usuarios. Estos
requerimientos indican cómo el sistema puede ser modificado o configurado por
los usuarios para tener en cuenta sus preferencias y selección de lenguaje
utilizado por el sistema. En otras culturas, se usan diferentes sistemas de
unidades —sistema métrico, anglosajón, etcétera—, unidades monetarias, idiomas,
etcétera.

<!-- SECCIÓN: Requerimientos de accesibilidad -->
Especificar los requerimientos asociados a la accesibilidad del sistema.
Dependiendo del problema y el producto, este tipo de requerimientos puede ser
más necesario.

<!-- SECCIÓN: Requerimientos de protección crítica -->
En caso de que usar el producto desarrollado signifique un posible riesgo de
daño percibido a personas o propiedad dentro del entorno de uso, detallar los
requerimientos que cuantifican este daño. Estos pueden estar relacionados a
estándares de seguridad o protección.

## Requerimientos de performance

<!-- SECCIÓN: Requerimientos de velocidad y latencia -->
<!-- TAG: Requerido -->
<img
  alt="REQUERIDO"
  src="https://img.shields.io/badge/REQUERIDO-FF4D4D"
/>

Detallar la cantidad de tiempo disponible para el producto al realizar
diferentes tareas en términos de latencia y velocidad. Un ejemplo de latencia:
"El sistema deberá responder a cualquier interacción en un tiempo menor a dos
segundos". Un ejemplo de velocidad: "El sistema deberá refrescar el estado de
cuenta cada 5 minutos".

<!-- SECCIÓN: Requerimientos de precisión -->
Especificar los requerimientos asociados a la precisión de los resultados
producidos por el producto, por ejemplo: "El sistema deberá mostrar las unidades
monetarias con una precisión de tres decimales" o, "El sistema deberá calcular
los grados de temperatura con una precisión de ± 1°C respecto al valor real".

<!-- SECCIÓN: Requerimientos de confiabilidad y disponibilidad -->
<!-- TODO Mencionar MTBF, MTTF y SLA, agregarlos bajo la carpeta de Conceptos y
referenciarlos -->
Definir los requerimientos de confiabilidad y disponibilidad del sistema, esto
es: ¿qué tanto tiempo deberá estar disponible el sistema? ¿en qué momentos del
día o qué días ha de estarlo? ¿qué porcentaje de tiempo de actividad deberá
cumplir? ¿qué tasa de fallos del sistema es aceptable?

<!-- SECCIÓN: Requerimientos de robustez -->
Indicar los requerimientos de robustez del sistema, esto es: la capacidad del
sistema de continuar funcionando de forma aceptable bajo condiciones anormales.
Por ejemplo: "El sistema deberá seguir proveyendo la funcionalidad X al no tener
conexión a Internet".

<!-- SECCIÓN: Requerimientos de capacidad -->
Especificar la cantidad de volumen de datos o usuarios que el sistema deberá
soportar. ¿Qué tantos usuarios en simultáneo deberá soportar el sistema? ¿este
número cambia para determinado momento del día?

<!-- SECCIÓN: Requerimientos de escalabilidad -->
Detallar aquellos requerimientos relacionados a la escalabilidad del sistema.

<!-- SECCIÓN: Requerimientos de longevidad -->
Especificar los requerimientos que definen la longevidad del producto, esto es,
la cantidad de tiempo que estará operativo.

## Requerimientos operacionales y de entorno

<!-- SECCIÓN: Requerimientos de entorno físico -->
<!-- TAG: Requerido -->
<img
  alt="REQUERIDO"
  src="https://img.shields.io/badge/REQUERIDO-FF4D4D"
/>

Detallar los requerimientos del entorno físico en el cual el sistema operará. En
algunos productos, las diferentes condiciones especiales bajo las que operará el
sistema generan requerimientos que se deben tener en cuenta.

<!-- SECCIÓN: Requerimientos de interfaz con sistemas adyacentes -->
Definir los requerimientos que establecen las interacciones necesarias entre el
sistema y otras aplicaciones o software. Tener en cuenta el versionado del
software con el cual el sistema va a interactuar, por ejemplo: "El sistema
deberá poder utilizar datos de la aplicación X en su versión 4.0".

<!-- SECCIÓN: Requerimientos del sistema -->
Definir todos los requerimientos de sistema necesarios para soportar la
aplicación. Esto puede incluir plataformas de sistemas operativos, de redes,
configuraciones, memoria, periféricos y software adicional necesario.

<!-- SECCIÓN: Requerimientos de distribución -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

En caso de que distribuir el producto esté dentro del alcance del proyecto,
indicar los requerimientos necesarios para que el sistema sea distribuido o
vendido como producto. Indicar también las tareas necesarias para que sea
instalado, en caso de ser pertinente. Por ejemplo: "La aplicación debe ser
distribuida en la App Store y Google Play Store en Uruguay" o, "La aplicación
debe ser descargable desde el sitio web de la organización".

<!-- SECCIÓN: Requerimientos del ciclo de *releases* -->
En caso de establecer con el cliente un ciclo de releases durante un determinado
período, indicarlo aquí como un requerimiento.

## Requerimientos de mantenimiento y soporte

<!-- SECCIÓN: Requerimientos de mantenimiento -->
<!-- TAG: Requerido -->
<img
  alt="REQUERIDO"
  src="https://img.shields.io/badge/REQUERIDO-FF4D4D"
/>

Especificar aquellos requerimientos relacionados al mantenimiento del sistema
por parte de los usuarios finales, administradores e incluso otros futuros
desarrolladores. Por ejemplo: "El código debe ser escrito en inglés para que sea
legible internacionalmente" o, "Un administrador de la aplicación debe ser capaz
de agregar un recurso X en menos de 15 minutos para que sea visible por los
usuarios" o, "Se debe entregar junto al producto un documento con notas de
arquitectura del sistema que explique cómo está estructurado".

<!-- SECCIÓN: Requerimientos de adaptabilidad -->
Especificar los entornos o plataformas que el sistema deberá soportar, por
ejemplo: "El sistema deberá ser capaz de correr en Android y iOS".

<!-- SECCIÓN: Guías de instalación y configuración -->
En una solución completa se debe incluir documentos con las instrucciones de
instalación y configuración. Establecer aquí los requerimientos para esos
documentos.

<!-- SECCIÓN: Requerimientos de soporte -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

En caso de que el sistema incluya soporte o ayuda en línea de alguna forma
específica —un chatbot, por ejemplo—, detallarlo aquí mediante requerimientos.

<!-- SECCIÓN: Manual de usuario -->
En caso de que sea necesario desarrollar un manual de usuario, describir su
propósito y contenido, esto es: extensión, nivel de detalle, índices, glosarios,
etcétera. Si hay restricciones de formatos o de impresión, indicarlo.

## Requerimientos de seguridad

<!-- SECCIÓN: Requerimientos de acceso -->
<!-- TAG: Requerido -->
<img
  alt="REQUERIDO"
  src="https://img.shields.io/badge/REQUERIDO-FF4D4D"
/>

Detallar quiénes tienen acceso a las diferentes partes del producto (tanto en
términos de funcionalidades como en términos de datos) y bajo qué
circunstancias.

<!-- SECCIÓN: Requerimientos de integridad -->
Especificar la integridad requerida por la base de datos, archivos del sistema y
el sistema en sí mismo. Por ejemplo: "El sistema deberá prevenir el ingreso de
datos incorrectos" o, "El sistema deberá protegerse a sí mismo del uso
malintencionado".

<!-- SECCIÓN: Requerimientos de privacidad -->
Describir aquellos requerimientos que definen qué debe hacer o con qué debe
cumplir el sistema para asegurar la privacidad de los datos compartidos por los
usuarios. Por ejemplo: "El sistema debe notificar a los usuarios sobre el uso
de sus datos personales" o, "El sistema debe notificar sobre cambios en la
política de privacidad de los datos".

<!-- SECCIÓN: Requerimientos de inmunidad -->
Mencionar qué es lo que tiene que hacer el sistema para protegerse de
infecciones de software como virus, gusanos, *malware*, *spyware*, etcétera.

<!-- SECCIÓN: Requerimientos de auditoría -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

En caso de que el sistema deba soportar controles de auditoría, especificar lo
que el sistema debe de hacer (usualmente, mantener información persistida) para
permitirlos. Por ejemplo: "El sistema debe mantener datos sobre X para que sean
auditados periódicamente".

## Requerimientos culturales

<!-- SECCIÓN: Requerimientos culturales -->
<!-- TAG: Según proyecto -->
<img
  alt="SEGÚN PROYECTO"
  src="https://img.shields.io/badge/SEG%C3%9AN%20PROYECTO-FFD700"
/>

Opcionalmente, pueden existir requerimientos de carácter sociológico que afecten
la aceptabilidad del sistema. Estos son de particular interés al
desarrollar un sistema para el mercado extranjero. Por ejemplo: "El sistema
deberá ser capaz de distinguir entre el enumerado de calles utilizado en Italia
e Inglaterra", o, "El sistema deberá contemplar los feriados de la Unión
Europea".

## Requerimientos legales

<!-- SECCIÓN: Requerimientos de cumplimiento normativo -->
<!-- TAG: Requerido -->
<img
  alt="REQUERIDO"
  src="https://img.shields.io/badge/REQUERIDO-FF4D4D"
/>

Detallar los requerimientos asociados a normas y regulaciones que el proyecto y
cada uno de ustedes como desarrolladores del sistema deberán cumplir.

<!-- SECCIÓN: Requerimientos de estándares aplicables -->
Detallar los estándares con los cuales el producto deberá cumplir, si los hay.
Por ejemplo, legales (FDA, UCC), de comunicaciones, de compatibilidad con
plataformas, calidad y seguridad (UL, ISO, CMM).
