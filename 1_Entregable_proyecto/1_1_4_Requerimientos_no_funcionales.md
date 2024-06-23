# 1 Contenido

## 1.1 Requisitos

<!-- TAG: Must have -->
### 1.1.4 Requerimientos no funcionales

En esta cuarta y última parte del análisis de requisitos deben definir todos los
diferentes tipos de requerimientos no funcionales que apliquen a su proyecto.
Para ello, deben usar la [plantilla de requerimiento
atómico](/3_Plantillas/3_1_Requerimiento_atomico.md) en cada requerimiento.

Tengan en cuenta que no todos los requerimientos no funcionales mencionados aquí
necesariamente aplican, así que deben ser prudentes y analizar cuáles sí que son
necesarios, así como cuáles no.

<!-- TAG: Might have -->
## Requerimientos de apariencia

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de apariencia -->
Detallar los requerimientos asociados a la apariencia del sistema, por ejemplo:
guías de UX/UI a utilizar —quizá brindadas por el cliente—, marca corporativa de
la organización cliente, qué colores utilizar, etcétera. Si el sistema no cuenta
con ninguna interfaz gráfica de usuario, indicarlo.

<!-- TAG: Might have -->
## Requerimientos de usabilidad y humanidad

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de facilidad de uso -->
Detallar los requerimientos del cliente en cuanto a la facilidad de uso del
sistema por parte de los usuarios finales. Ten en cuenta que esta facilidad es
derivada de: la habilidad de los previstos usuarios finales y la complejidad del
producto y sus funcionalidades. Algunas características a tener en cuenta pueden
ser:

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

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de personalización e internacionalización -->
Especificar los requerimientos asociados a las preferencias de los usuarios.
Estos requerimientos indican cómo el sistema puede ser modificado o configurado
por los usuarios para tener en cuenta sus preferencias y selección de lenguaje
utilizado por el sistema. En otras culturas, se usan diferentes sistemas de
unidades —sistema métrico, anglosajón, etcétera—, unidades monetarias, idiomas,
etcétera. En caso de que el cliente no esté interesado en definir este tipo de
requerimientos, indicarlo.

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de aprendizaje -->
Detallar las expectativas del cliente en cuanto a qué tanto esfuerzo deberán
emplear los usuarios finales para poder utilizar el sistema de una forma
productiva. Algunos sistemas deben ser muy fáciles de utilizar y por ende
intuitivos, otros se pueden permitir determinada curva de aprendizaje debido a
la complejidad del problema. La idea aquí es cuantificar la cantidad de tiempo o
esfuerzo que los usuarios finales necesitan para aprender a usar el sistema y
que esta cuantificación sea aceptable para el cliente. Esta clarificación puede
incluir un plan de capacitación para los usuarios, e incluso un manual de
usuario, por ejemplo: "Los usuarios deberán ser capaces de usar el sistema tras
una semana de capacitación" o, "Los usuarios deberán ser capaces de utilizar el
sistema tras leer el manual de usuario".

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de accesibilidad -->
Especificar los requerimientos asociados a la accesibilidad del sistema.
Dependiendo del problema y el producto, este tipo de requerimientos puede ser
más necesario.

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de protección crítica -->
Detallar los requerimientos que cuantifican el riesgo de daño percibido a
personas, propiedad y entorno. Estos pueden estar relacionados a estándares de
seguridad o protección.

<!-- TAG: Must have -->
## Requerimientos de *performance*

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de velocidad y latencia -->
Detallar la cantidad de tiempo disponible para el producto al realizar
diferentes tareas. Un ejemplo de latencia: "El sistema deberá responder a
cualquier interacción en un tiempo menor a dos segundos". Un ejemplo de
velocidad: "El sistema deberá refrescar el estado de cuenta cada 5 minutos".

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de precisión -->
Especificar los requerimientos asociados a la precisión de los resultados
mostrados por el producto, por ejemplo: "El sistema deberá mostrar las unidades
monetarias con una precisión de tres decimales".

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de confiabilidad y disponibilidad -->
<!-- TODO Mencionar MTBF, MTTF y SLA, agregarlos bajo la carpeta de Conceptos y
referenciarlos -->
Definir los requerimientos de confiabilidad y disponibilidad del sistema, esto
es: ¿qué tanto tiempo deberá estar disponible el sistema? ¿en qué momentos del
día o qué días ha de estarlo? ¿qué porcentaje de tiempo de actividad deberá
cumplir? ¿qué tasa de fallos del sistema es aceptable?

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de robustez -->
Indicar los requerimientos de robustez del sistema, esto es, la capacidad del
sistema de continuar funcionando de forma aceptable bajo condiciones anormales.
Por ejemplo: "El sistema deberá seguir proveyendo la funcionalidad X al no tener
conexión a Internet".

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de capacidad -->
Especificar la cantidad de volumen de datos o usuarios que el sistema deberá
soportar. ¿Qué tantos usuarios en simultáneo deberá soportar el sistema? ¿este
número cambia para determinado momento del día?

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de escalabilidad -->
Detallar aquellos requerimientos relacionados a la escalabilidad del sistema.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de longevidad -->
Especificar los requerimientos que definen la longevidad del producto, esto es,
la cantidad de tiempo que estará operativo.

<!-- TAG: Must have -->
## Requerimientos operacionales y de entorno

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de entorno físico -->
Detallar los requerimientos del entorno físico en el cual el sistema operará. En
algunos productos, las diferentes condiciones especiales bajo las que operará el
sistema generan requerimientos que se deben tener en cuenta.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de interfaz con sistemas adyacentes -->
Definir los requerimientos que establecen las interacciones necesarias entre el
sistema y otras aplicaciones o software. Tener en cuenta el versionado del
software con el cual el sistema va a interactuar, por ejemplo: "El sistema
deberá poder utilizar datos de la aplicación X en su versión 4.0".

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de distribución -->
Indicar los requerimientos necesarios para que el sistema sea distribuido o
vendido como producto. Indicar también las tareas necesarias para que sea
instalado, en caso de ser pertinente. Por ejemplo: "La aplicación debe ser
distribuida en la App Store y Google Play Store en Uruguay" o, "La aplicación
debe ser descargable desde el sitio web de la organización".

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos del ciclo de *releases* -->
En caso de establecer con el cliente un ciclo de releases durante un determinado
período, indicarlo aquí como un requerimiento.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos del sistema -->
Definir todos los requerimientos de sistema necesarios para soportar la
aplicación. Esto puede incluir plataformas de sistemas operativos, de redes,
configuraciones, memoria, periféricos y software adicional necesario.

<!-- TAG: Must have -->
## Requerimientos de mantenimiento y soporte

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de mantenimiento -->
Especificar aquellos requerimientos relacionados al mantenimiento del sistema
por parte de los usuarios finales, administradores e incluso otros futuros
desarrolladores. Por ejemplo: "El código debe ser escrito en inglés para que sea
legible internacionalmente" o, "Un administrador de la aplicación debe ser capaz
de agregar un recurso X en menos de 15 minutos para que sea visible por los
usuarios" o, "Se debe entregar junto al producto un documento con notas de
arquitectura del sistema que explique cómo está estructurado".

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de soporte -->
En caso de que el sistema incluya soporte o ayuda en línea de alguna forma
específica —un chatbot, por ejemplo—, detallarlo aquí mediante requerimientos.
En caso contrario, indicarlo.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de adaptabilidad -->
Especificar los entornos o plataformas que el sistema deberá soportar, por
ejemplo: "El sistema deberá ser capaz de correr en Android y iOS".

<!-- TAG: Might have -->
<!-- SECCIÓN: Manual de usuario -->
Describir el propósito y contenido del manual de usuario: extensión, nivel de
detalle, índices, glosarios, etcétera. Si hay restricciones de formatos o de
impresión, indicarlo.

En caso de que no haya manual de usuario, indicarlo.

<!-- TAG: Must have -->
<!-- SECCIÓN: Guías de instalación y configuración -->
En una solución completa se debe incluir documentos con las instrucciones de
instalación y configuración. Establecer aquí los requerimientos para esos
documentos.

<!-- TAG: Must have -->
## Requerimientos de seguridad

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de acceso -->
Detallar quiénes tienen acceso a las diferentes partes del producto (tanto en
términos de funcionalidades como en términos de datos) y bajo qué
circunstancias.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de integridad -->
Especificar la integridad requerida por la base de datos, archivos del sistema y
el sistema en sí mismo. Por ejemplo: "El sistema deberá prevenir el ingreso de
datos incorrectos" o, "El sistema deberá protegerse a sí mismo del uso
malintencionado".

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de privacidad -->
Describir aquellos requerimientos que definen qué debe hacer o con qué debe
cumplir el sistema para asegurar la privacidad de los datos compartidos por los
usuarios. Por ejemplo: "El sistema debe notificar a los usuarios sobre el uso
de sus datos personales" o, "El sistema debe notificar sobre cambios en la
política de privacidad de los datos".

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos de auditoría -->
Especificar lo que el sistema debe de hacer (usualmente, mantener información
persistida) para permitir controles de auditoría. Por ejemplo: "El sistema debe
mantener datos sobre X para que sean auditados periódicamente".

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de inmunidad -->
Mencionar qué es lo que tiene que hacer el sistema para protegerse de
infecciones de software como viruses, gusanos, *malware*, *spyware*, etcétera.

<!-- TAG: Might have -->
## Requerimientos culturales

<!-- TAG: Might have -->
<!-- SECCIÓN: Requerimientos culturales -->
Especificar los requerimientos de carácter sociológico que afectan la
aceptabilidad del sistema. Estos son de particular interés al desarrollar un
sistema para el mercado extranjero. Por ejemplo: "El sistema deberá ser capaz de
distinguir entre el enumerado de calles utilizado en Italia e Inglaterra", o,
"El sistema deberá contemplar los feriados de la Unión Europea".

<!-- TAG: Must have -->
## Requerimientos legales

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de cumplimiento normativo -->
Detallar los requerimientos asociados a normas y regulaciones que el proyecto y
cada uno de ustedes como desarrolladores del sistema deberán cumplir.

<!-- TAG: Must have -->
<!-- SECCIÓN: Requerimientos de estándares aplicables -->
Detallar los estándares con los cuales el producto deberá cumplir, si los hay.
Por ejemplo, legales (FDA, UCC), de comunicaciones, de compatibilidad con
plataformas, calidad y seguridad (UL, ISO, CMM).
