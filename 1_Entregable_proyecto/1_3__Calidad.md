# 1 Contenido

## 1.3 Calidad

Además de esta página te recomendamos leer sobre [conceptos de calidad de
software](/4_Conceptos/4_Calidad_de_software.md).

El propósito de esta sección en el documento del proyecto es documentar aspectos
relacionados con las pruebas, en particular, la estrategia de pruebas contenida
en el plan de pruebas y los casos de prueba y sus resultados.

El contenido de esta página está basado en [Disciplined Agile®
Delivery](https://www.pmi.org/disciplined-agile/process/introduction-to-dad)
—DAD— del [Project Management Institute](https://www.pmi.org), en particular en
la documentación sobre el [desarrollo de la estrategia de
pruebas](https://dabrowser.pmi.org/#item:272).

### Estrategia de pruebas

Definir una estrategia de pruebas implica tomar decisiones relacionadas,
entre otros, con los siguientes temas:

* El nivel de detalle de las pruebas
* Los enfoques de prueba
* Cómo se van a probar los requerimientos no-funcionales
* Los ambientes de prueba
* Los tipos de pruebas
* Las fuentes de datos de pruebas
* La estrategia de automatización —o no— de las pruebas
* Cómo se informan y gestionan los defectos encontrados

La estrategia de pruebas se define en la etapa de inicio del proyecto y se
documenta en el plan de pruebas usando [esta
plantilla](/3_Plantillas/3_8_Plan_de_pruebas.md), o en la herramienta de
automatización de pruebas [Azure Test
Plans](https://learn.microsoft.com/en-us/azure/devops/test/?view=azure-devops)
disponible como parte de la suscripción a [Azure Devops
Services](https://azure.microsoft.com/es-es/products/devops) a la que tienen
acceso con la cuenta de estudiante @correo.ucu.edu.uy; pueden utilizar otra
herramienta si lo acuerdan con su tutor[^1].

### Plan de pruebas

El plan de pruebas especifica cómo va a ser probada la aplicación y es el
resultado de la [estrategia de pruebas](#estrategia-de-pruebas) definida.

Debe incluir al menos los elementos obligatorios de la [plantilla de plan de
pruebas](/3_Plantillas/3_8_Plan_de_pruebas.md); si fuera necesario puede incluir
otros elementos opcionales de esa plantilla.

El plan de pruebas es parte de la primera entrega del proyecto.

### Enfoques de pruebas

Para cada elemento a probar —funcionalidades, interfaces con otros productos o
servicios, integración con otros productos o servicios— es necesario elegir uno
o más [enfoques de pruebas](/4_Conceptos/4_Enfoques_de_pruebas.md).

### Tipos de pruebas

Para cada combinación de elemento a probar y enfoque de pruebas es necesario
elegir uno o más [tipos de pruebas](/4_Conceptos/4_Tipos_de_pruebas.md).

### Datos de prueba

Cada caso de prueba requiere un conjunto de datos de prueba, aunque el mismo
conjunto de pruebas puede ser usado en varios casos de prueba. El conjunto de
datos de prueba puede ser generado automáticamente o puede ser creado a partir
de datos existentes anonimizados.

Los datos de prueba deberían estar bajo control de configuración, al igual que
los casos de prueba.

### Casos de prueba

Los casos de prueba describen cómo se realizan las pruebas, con qué datos, en
qué situación inicial de la aplicación, y cuál es el resultado correcto
esperado.

Para documentar los casos de prueba puedes usar [esta
plantilla](/3_Plantillas/3_4_Casos_de_prueba_de_usuario_final.md), o puedes usar
la herramienta [Azure Test
Plans](https://learn.microsoft.com/en-us/azure/devops/test/?view=azure-devops)
antes mencionada. Los casos de prueba se van generando luego de definida la
estrategia de pruebas en la etapa de inicio a medida que van creando [casos de
uso](/4_Conceptos/4_Caso_de_uso_del_producto.md), requerimientos funcionales y
no-funcionales, código, etc. a probar.

Los casos de prueba deben estar bajo control de configuración, al igual que los
datos de prueba.

### Resultados de las pruebas

El resultado de la ejecución de los casos de prueba debe ser registrado cada vez
que se ejecuta, tanto si fue exitoso como si no lo fue; en este último caso,
además, es necesario registrar el defecto en una herramienta de tiques para que
sea correctamente priorizado y gestionado.

### Automatización de las pruebas

Las pruebas pueden estar automatizadas, para poder repetirlas a lo largo del
proyecto. Los casos de prueba automatizados deben estar bajo control de
configuración.

Pueden usar la herramienta de automatización de pruebas [Azure Test
Plans](https://learn.microsoft.com/en-us/azure/devops/test/?view=azure-devops)
disponible como parte de la suscripción a [Azure Devops
Services](https://azure.microsoft.com/es-es/products/devops) a la que tienen
acceso con la cuenta de estudiante @correo.ucu.edu.uy.

[^1]: Ten en cuenta la seguridad y privacidad de la información que almacenes en
    estos repositorios; si tienes un acuerdo de confidencialidad con el cliente,
    deberías usar las herramientas recomendadas. También deberás considerar que
    otras herramientas pueden tener costos asociados o limitar la cantidad de
    usuarios o de archivos en las versiones gratuitas.