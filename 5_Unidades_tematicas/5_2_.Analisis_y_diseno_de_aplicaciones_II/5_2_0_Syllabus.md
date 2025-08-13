<img alt="UCU" src="https://www.ucu.edu.uy/plantillas/images/logo_ucu.svg"
width="150"/>

# Universidad Católica del Uruguay

## Facultad de Ingeniería y Tecnologías

### Análisis y diseño de aplicaciones II

# Syllabus

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold">
      Curso
    </td>
    <td>
      Análisis y diseño de aplicaciones II
    </td>
  </tr>
  <tr>
    <td style="color:#0969DA;font-weight:bold"  >
      Carrera
    </td>
    <td>
      Ingeniería en Informática, Licenciatura en Informática, Analista en Informática
    </td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold">
      Resumen
    </td>
  </tr>
  <tr>
    <td>
      En cursos anteriores has visto cómo relevar y especificar requerimientos
      funcionales de aplicaciones informáticas y cómo crear diseños que cumplan
      con esos requerimientos. Pero las aplicaciones también tienen
      requerimientos no-funcionales de escalabilidad, desempeño, confiabilidad,
      y muchos más; ahora verás cómo diseñar aplicaciones para cumplir con estos
      nuevos requerimientos.
    </td>
  </tr>

</table>
<!-- markdownlint-enable MD033 -->

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold" colspan=2>
      Objetivos
    </td>
  </tr>
  <tr>
    <td colspan=2>
      La intención de este curso es que puedas relevar requerimientos
      no—funcionales de aplicaciones empresariales y diseñar la infraestructura
      y el software apropiados para satisfacer esos requerimientos.
    </td>
  </tr>
  <tr>
    <td style="color:#0969DA;font-weight:bold">
      Competencias
    </td>
    <td style="color:#0969DA;font-weight:bold">
      Resultados del aprendizaje
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Aplica principios y patrones de diseño y arquitectura de software e
      infraestructura en el modelado y diseño de sistemas informáticos
      demostrando la comprensión de las decisiones alternativas involucradas en
      las opciones de diseño.
    </td>
    <td rowspan=2>
      1. Aplica estilos y patrones de arquitectura al diseño de una solución
      informática para satisfacer requerimientos no-funcionales; y explica a una
      audiencia de pares cómo el diseño resultante satisface esos requerimientos.
    </td>
  </tr>
  <tr>
    <td>
      Comunica efectivamente con diversas audiencias información técnica
      consistente con la audiencia y el propósito, en una variedad de contextos profesionales.
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Analiza problemas complejos del mundo real, para identificar y definir
      requisitos informáticos, y los resuelve aplicando enfoques y principios
      computacionales relevantes y otras disciplinas en el proceso de resolución.
    </td>
    <td>
      2. Evalúa opciones de integración de aplicaciones y demuestra como esas
      opciones afectan las pruebas dentro del desarrollo de un sistema
      informático.
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td rowspan=3>
      Diseña, implementa y evalúa soluciones informáticas aplicando el proceso
      de diseño de ingeniería que satisfacen requerimientos en el contexto de la
      disciplina, analizando el impacto local y global de la informática en
      individuos, organizaciones, y la sociedad.
    </td>
      <tr style="vertical-align:top">
    <td>
      3. Evalúa opciones de implementación de una solución informática
      utilizando arquitecturas de microservicios desplegadas en contenedores
      versus arquitecturas tradicionales en máquinas virtuales o físicas, y
      explica las consecuencias a una audiencia de partes interesadas.
    </td>
  </tr>
    <td>
      4. Diseña la arquitectura del software y de la infraestructura de una
      solución informática considerando tanto recursos en nubes privadas o
      públicas e híbridas, y servicios de infraestructura o de plataforma; y
      documentarla utilizando una notación apropiada.
    </td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold" colspan=5>
      Temario
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td style="color:#0969DA;font-weight:bold;width:22.5%" rowspan=2>
      Unidad
    </td>
    <td style="color:#0969DA;font-weight:bold;width:45%;text-align:center" colspan=2>
      Contenidos
    </td>
    <td style="color:#0969DA;font-weight:bold;width:10%" rowspan=2>
      Horas estimadas
    </td>
    <td style="color:#0969DA;font-weight:bold;width:22.5%" rowspan=2>
      Estrategia de enseñanza
    </td>
  </tr>
  <tr>
    <td style="color:#0969DA;font-weight:bold;width:22.5%">
      Primarios
    </td>
    <td style="color:#0969DA;font-weight:bold;width:22.5%">
      Secundarios
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td><a id="ut1"></a>1. Impulsores o <i>drivers</i> de la arquitectura</td>
    <td>
      <p>Atributos de calidad</p>
      <p>Requerimientos arquitectónicamente significativos</p>
      <p>Disponibilidad, rendimiento, protección, seguridad, facilidad de
      modificación, facilidad de despliegue</p>
    </td>
    <td>Modelos de calidad de software</td>
    <td>12 en clase, 30 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupo</td>
  </tr>
  </tr><tr style="vertical-align:top">
    <td>2. Tácticas de arquitectura</td>
    <td>
      Tácticas para disponibilidad, rendimiento, protección, seguridad,
      facilidad de modificación, facilidad de despliegue
    </td>
    <td>N/A</td>
    <td>12 en clase, 30 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupo</td>
  <tr style="vertical-align:top">
    <td>3. Soluciones arquitectónicas</td>
    <td>
      <p>Componentes</p>
      <p>Interfaces</p>
      <p>Interacción</p>
    </td>
    <td>
      <p>Virtualización</p>
      <p>Microservicios</p>
      <p>Computación distribuida, propiedades ACID, propiedades BASE, teorema
      de Brewer, consistencia fuerte, consistencia eventual</p>
    </td>
    <td>14 en clase, 35 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupo</td>
  </tr>
  <tr style="vertical-align:top">
    <td>4. Patrones de arquitectura</td>
    <td>Patrones para disponibilidad, rendimiento, protección, seguridad,
      facilidad de modificación, facilidad de despliegue</td>
    <td>CQRS, Compensating Transaction, Event Sourcing, Choreography</td>
    <td>14 en clase, 35 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupo</td>
  </tr>
  <tr style="vertical-align:top">
    <td>5. Estilos de arquitectura</td>
    <td>Layered, Pipes and Filters, Microkernel, Service-Based, Event-Driven,
    Service-Oriented, Microservices
    </td>
    <td>Space-Based, Orchestration-Driven</td>
    <td>14 en clase, 35 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupos</td>
  </tr>
  <tr style="vertical-align:top">
    <td>6. Proceso de arquitectura</td>
    <td>Diseño dirigido por atributos</td>
    <td>Modelo C4, Ciclo de identificación de componentes</td>
    <td>6 en clase, 15 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupos</td>
  </tr>
  <tr style="vertical-align:top">
    <td>7. Evaluación de la arquitectura</td>
    <td>ATAM</td>
    <td>ALMA, PASA</td>
    <td>6 en clase, 15 en casa</td>
    <td>Lecturas previas, clase invertida, ejercicios prácticos de aplicación,
    trabajo en grupos</td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold" colspan=4>
      Plan de evaluación
    </td>
  </tr>
  <tr style="color:#0969DA;font-weight:bold;vertical-align:top">
    <td style="width:25%">
      Propuesta de evaluación
    </td>
    <td style="width:25%">
      Evidencia
    </td>
    <td style="width:25%">
      Temporalidad
    </td>
    <td style="width:25%">
      Peso en la calificación
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Tareas de aplicación individuales o en equipo
    </td>
    <td>
      Resultados de aprendizaje 1 a 4
    </td>
    <td>
      Durante cada unidad temática
    </td>
    <td>
      15%
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Controles de lectura individuales
    </td>
    <td>
      Resultados de aprendizaje 1 a 4
    </td>
    <td>
      Al inicio de cada unidad temática
    </td>
    <td>
      18%
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Controles de lectura en equipos
    </td>
    <td>
      Resultados de aprendizaje 1 a 4
    </td>
    <td>
      Al inicio de cada unidad temática
    </td>
    <td>
      12%
    </td>
  </tr>
    <tr style="vertical-align:top">
    <td>
      Evaluación entre pares
    </td>
    <td>
      Resultados de aprendizaje 1 a 4
    </td>
    <td>
      Semana 16
    </td>
    <td>
      3%
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Pruebas parciales escritas
    </td>
    <td>
      Resultado de aprendizaje 1 a 4
    </td>
    <td>
      Semana 7, 12 y 16
    </td>
    <td>
      42%
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Actitud académica<span id="back_ref_1"><a href="#ref_1"><sup>[1]</sup></a></span>
    </td>
    <td>
      Ciertos dominios de algunas de las competencias generales
    </td>
    <td>
      A lo largo del curso
    </td>
    <td>
      10%
    </td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold" colspan=2>
      Modalidad de la retroalimentación
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Tareas de aplicación individuales o en equipo
    </td>
    <td>
      Comentarios de retroalimentación escritos o rúbrica de evaluación
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Pruebas parciales escritas
    </td>
    <td>
      Retroalimentación escrita en la prueba
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Controles de lectura individuales
    </td>
    <td>
      Respuesta correcta y puntos diferidos hasta el cierre del cuestionario
      control de lectura en equipo
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Controles de lectura en equipo
    </td>
    <td>
      Respuesta correcta durante el intento en modo adaptativo y puntos al
      cerrar el cuestionario
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Evaluación entre pares
    </td>
    <td>
      Rúbrica de evaluación<span id="back_ref_2"><a href="#ref_2"><sup>[2]</sup></a></span>
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      Actitud académica
    </td>
    <td>
      Lista de cotejo<span id="back_ref_3"><a href="#ref_3"><sup>[3]</sup></a></span>
    </td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

Rúbrica para evaluación entre pares:

<!-- markdownlint-disable MD033 -->
<table>
  <tr>
    <td style="color:#0969DA;font-weight:bold">
      Recursos principales
    </td>
  </tr>
  <tr style="vertical-align:top">
    <td>
      <p>Bass, L., Clements, P., & Kazman, R. (2022). Software architecture in
      practice, 4<sup>th</sup> edition. Addison-Wesley.</p>
      <p>Richards, M., & Ford, N. (2020). Fundamentals of software architecture:
      An engineering approach. O'Reilly Media. Disponible en
      <a href=https://catalogo.ucu.edu.uy/cgi-bin/koha/opac-detail.pl?biblionumber=122029>biblioteca</a>.</p>
      <p><a href="./5_2_1_Impulsores_de_la_arquitectura.md#lecturas">Lecturas de
      la unidad temática 1</a></p>
      <!-- spell-checker:ignore Tacticas -->
      <p><a href="./5_2_2_Tacticas_de_arquitectura.md#lecturas">Lecturas de la
      unidad temática 2</a></p>
      <!-- spell-checker:ignore arquitectonicas -->
      <p><a href="./5_2_3_Soluciones_arquitectonicas.md#lecturas">Lecturas de la
      unidad temática 3</a></p>
      <p><a href="./5_2_4_Patrones_de_arquitectura.md#lecturas">Lecturas de la
      unidad temática 4</a></p>
      <p><a href="./5_2_5_Estilos_de_arquitectura.md#lecturas">Lecturas de la
      unidad temática 5</a></p>
      <p><a href="./5_2_6_Proceso_de_arquitectura.md#lecturas">Lecturas de la
      unidad temática 6</a></p>
      <!-- spell-checker:ignore Evaluacion -->
      <p><a href="./5_2_7_Evaluacion_de_la_arquitectura.md#lecturas">Lecturas de
      la unidad temática 7</a></p>
    </td>
  </tr>
</table>
<!-- markdownlint-enable MD033 -->

----

<!-- markdownlint-disable MD033 -->
<span id="ref_1">
1. El componente de actitud académica se evalúa mediante la
manifestación de las competencias generales del grado UCU a lo largo del curso:

* Aprender a aprender: Aprende el proceso de aprender ‑meta-cognición‑. Cree
  en la capacidad de aprender para crecer ‑mentalidad de crecimiento‑. Persevera
  y supera desafíos para alcanzar un objetivo Reflexiona sobre la experiencia
  para mejorar su aprendizaje. Cultiva y administra la inteligencia emocional
  para comprenderse a sí mismo y a los demás. Se adapta al cambio y muestra
  resiliencia.

* Pensamiento crítico y resolución de problemas. Resuelve ingeniosamente
  problemas complejos y significativos de la vida real. Toma decisiones y da
  pasos concretos para enfrentar dificultades. Diseña, gestiona y evalúa
  iniciativas, programas o proyectos. Adquiere, procesa, interpreta y analiza
  información para tomar decisiones. Emplea procesos de indagación para resolver
  problemas. Hace conexiones y transfiere aprendizajes de una situación a otra.

* Colaboración. Se involucra en equipos y establece relaciones positivas.
  Aprende de, y contribuye al aprendizaje de otros. Co-construye conocimiento,
  significado y contenidos. Asume y gestiona varios roles en un equipo. Asume y
  gestiona el conflicto. Se relaciona con una variedad de comunidades y grupos.
  Respeta y comprende perspectivas y enfoques diversos

* Comunicación. Se comunica efectivamente en diferentes contextos tanto
  oralmente como en forma escrita, en español y en inglés. Hace preguntas
  efectivas para adquirir y profundizar en diversos tipos de conocimientos. Se
  comunica utilizando una variedad de medios. Selecciona herramientas digitales
  adecuadas, de acuerdo con su propósito e implicancias. Desarrolla la capacidad
  de escucha para entender todos los puntos de vista. Expresa opiniones y aboga
  por ideas fundado en evidencias.
</span><a href="#back_ref_1" title="Volver...">↩︎</a>

<span id="ref_3">
3. Lista de cotejo para evaluación de actitud académica. Cada ítem se evalúa en
   términos de <b>Hay evidencia suficiente</b>, <b>Evidencia insuficiente</b> y <b>Hay
   evidencia en contrario</b>.
<ul>
  <li>Aprender a aprender</li>
    <ul>
      <li>Meta-cognición: Identifica y explica el proceso que utiliza para
      aprender.</li>
      <li>Mentalidad de crecimiento: Demuestra confianza en su capacidad de
      aprender y crecer.</li>
      <li>Perseverancia: Supera obstáculos para alcanzar sus objetivos.</li>
      <li>Reflexión: Evalúa y adapta su aprendizaje a partir de la experiencia.</li>
      <li>Inteligencia emocional: Reconoce y regula sus emociones y muestra
      empatía hacia los demás.</li>
      <li>Adaptabilidad y resiliencia: Se adapta a nuevas circunstancias y
      persiste ante el cambio.</li>
    </ul>
  <li>Pensamiento crítico y resolución de problemas</li>
    <ul>
      <li>Resolución ingeniosa: Encuentra soluciones creativas para problemas
      complejos y significativos.</li>
      <li>Toma de decisiones: Analiza alternativas y toma decisiones bien fundamentadas.</li>
      <li>Gestión de proyectos: Diseña, implementa y evalúa proyectos o iniciativas.</li>
      <li>Análisis de información: Procesa y analiza información para la toma de
      decisiones.</li>
      <li>Indagación: Utiliza procesos de investigación para resolver problemas.</li>
      <li>Transferencia: Aplica aprendizajes de una situación a otra de manera efectiva.</li>
    </ul>
  <li>Colaboración</li>
    <ul>
      <li>Trabajo en equipo: Participa activamente y fomenta relaciones
      positivas en el equipo.</li>
      <li>Contribución mutua: Aprende de otros y aporta al aprendizaje colectivo.</li>
      <li>Co-construcción: Colabora para generar conocimiento o productos en conjunto.</li>
      <li>Gestión de roles: Desempeña diferentes roles dentro de un equipo de
      manera efectiva.</li>
      <li>Manejo de conflictos: Identifica, gestiona y resuelve conflictos de
      manera constructiva.</li>
      <li>Diversidad: Respeta y valora las perspectivas y enfoques diversos
      dentro del equipo.</li>
    </ul>
  <li>Comunicación</li>
    <ul>
      <li>Expresión oral y escrita: Se comunica de forma clara y efectiva en
      diversos contextos.</li>
      <li>Formulación de preguntas: Realiza preguntas para adquirir y
      profundizar conocimientos.</li>
      <li>Uso de medios: Utiliza una variedad de medios para comunicarse.</li>
      <li>Herramientas digitales: Selecciona herramientas tecnológicas según el
      propósito de la comunicación.</li>
      <li>Escucha activa: Comprende diferentes puntos de vista a través de la
      escucha atenta.</li>
      <li>Defensa de ideas: Expresa opiniones y aboga por ideas basadas en
      evidencia.<a href="#back_ref_3" title="Volver...">↩︎</a></li>
    </ul>
</ul>
</span>
<!-- markdownlint-enable MD033 -->
