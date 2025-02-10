# Contribuyendo

## Introducción

Antes que nada, gracias por considerar contribuir con esta iniciativa. Son las
personas como tú las que hacen que sea una herramienta útil para estudiantes,
profesores y tutores.

Esta guía está basada [en esta](https://github.com/nayafia/contributing-template)
y [esta otra](https://github.com/valerybriz/contributing-template).

Al seguir estas guías estás comunicando que tú respetas el tiempo de las y los
que estamos involucrados en esta iniciativa. A cambio, ellas y ellos deberían de
forma recíproca resolver tus *issues*, revisar los cambios y ayudarte a finalizar
tus *pull requests*.

¡Mantén la mente abierta! Mejorar la documentación sugiriendo nuevas entradas o
reportar los errores que encuentres son ejemplos de contribuciones que ayudan a
mejorar esta iniciativa.

## Reglas de base

Esperamos que quienes quieran contribuir asuman las siguientes responsabilidades:

* Asegurar la compatibilidad entre plataformas para cada cambio aceptado:
Windows, Mac, Linux.
* Crea *issues* para cualquier cambio mayor y mejora que desearías hacer. Discute
las cosas de manera transparente y obtén los comentarios de la comunidad.
* No agregues nuevos archivos a menos de que sea completamente necesario.
* Mantén el versionamiento de las cosas que agregues tan cortos como sea posible.
* Sé amable con las y los recién llegados y apoya la diversidad de nuevas y nuevos

contribuidores de todo tipo de antecedente. Revisa el [código de conducta de la
comunidad Python](https://www.python.org/psf/codeofconduct/).

## Tu primera contribución

¿Aún no sabes como empezar a contribuir? Puedes empezar revisando los

*issues* con etiquetas `good first issue` ‑principiante‑ y `help wanted`

* Etiqueta `good first issue`: los *issues* con esta etiqueta deberían ser
triviales de resolver, por ejemplo, un error ortográfico, o un error de formato.
* Etiqueta `help wanted`: Estos son *issues* que pueden ser un poco más
complicados que los anteriores.

Ambas listas de issues están ordenadas por la cantidad de comentarios que
tienen. Aunque no es perfecto, la cantidad de comentarios es un proxy razonable
para saber el impacto que tendrá el cambio.

No seas tímido. Tus comentarios y aportes son siempre bienvenidos. Puedes
equivocarte, todos podemos equivocarnos, lo que no podemos hacer es dejar de
aprender de nuestros errores, o ser negligentes; pero por lo demás, te alentamos
a que pruebes.

<!--
TODO: Ver qué de esto es interesante para agregar, el de Django me gustó.
[source:
[Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#your-first-code-contribution)]
**Necesitas más inspiración?** [1] [Read the
Docs](http://docs.readthedocs.org/en/latest/contribute.html#contributing-to-development)
[2]
[Django](https://docs.djangoproject.com/en/dev/internals/contributing/new-contributors/#first-steps)
(baja en el scroll hasta "Guidelines" también)

### Puntos de Bonus: Agrega un enlace a recursos para personas que nunca han contribuido anteriormente

Aquí hay algunos tutoriales que puedes incluir: http://makeapullrequest.com/ y
http://www.firsttimersonly.com/

> Trabajando en tu primer Pull Request? Puedes aprender como en esta *free*
> series, [Cómo contribuir a un proyecto de Código abierto en
> GitHub](https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github).

[fuente:
[React](https://github.com/facebook/react/blob/master/CONTRIBUTING.md#pull-requests)]

Como nota, es bastante útil usar lenguaje amigable con las personas recién
llegadas en todo el documento. Aquí algunos ejemplos de [Active
Admin](https://github.com/activeadmin/activeadmin/blob/master/CONTRIBUTING.md):
 -->

[![PRs
Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com)

> [!TIP]
> ¿Estás por hacer tu primer *pull request*? Aprende cómo hacerlo en esta
> serie *gratuita* [How to Contribute to an Open Source Project on
> GitHub](https://kcd.im/pull-request)

En este punto, ¡ya estás preparada o preparado para hacer cambios! Siéntete
libre de pedir ayuda; todos fuimos principiantes una vez :smile_cat:

> [!IMPORTANT]
> Si un colaborador te pide que hagas un *rebase* al *pull request*, se refiere
> a que muchísimo código ha cambiado y deberías actualizar la rama para que sea
> más fácil unirla al resto del código.

## Empezando

Asumimos que si tienes acceso al repo puedes hacer todo lo que estás autorizado
a hacer según los permisos de tu rol.

La rama `main` está configurada con una regla de protección de requiere:

* Que haya un *pull request* para hacer un *merge*.
* Que haya al menos una aprobación del *pull request*.
* Que uno de los revisores sea *code owner*.

> [!TIP]
> Para obtener más información sobre las reglas de protección de
> las ramas mira [este link](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches#require-pull-request-reviews-before-merging).
>
> Para obtener más información sobre los *code owners* mira [este
> link](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
</br>

Para cualquier cosa que sea mayor a una o dos líneas para corregir:

1. Crea tu propio *fork* del código
2. Haz los cambios en tu *fork*
3. Cuando creas que los cambios ameritan ser incorporados en el repo:
    * Asegúrate de haber seguido el estilo de código del proyecto.
    * Envía un *pull request* solicitando que tus cambios sean incorporados.

<!--
TODO: Revisar estas fuentes
[fuente: [Requirejs](http://requirejs.org/docs/contributing.html)] **Necesitas más inspiración?** [1] [Active Admin](https://github.com/activeadmin/activeadmin/blob/master/CONTRIBUTING.md#1-where-do-i-go-from-here) [2] [Node.js](https://github.com/nodejs/node/blob/master/CONTRIBUTING.md#code-contributions) [3] [Ember.js](https://github.com/emberjs/ember.js/blob/master/CONTRIBUTING.md#pull-requests)
-->

## Cómo reportar un bug

Cuando completes un *issue* para
[reportar](https://github.com/ucudal/ANDIS_Conceptos/issues/new/choose) un
error, asegúrate de responder estas tres preguntas:

1. ¿En qué página estabas navegando? Incluye la URL que muestra el navegador
2. ¿Qué viste que consideras incorrecto?
3. ¿Qué esperabas ver que consideras correcto?

Preguntas generales sobre el contenido deben ser planteadas a través de los
canales de comunicación que proponen los profesores en los cursos o proyectos en
los que se consume este contenido.

<!--
TODO: Revisar estas fuentes

[fuente: [Go](https://github.com/golang/go/blob/master/CONTRIBUTING.md#filing-issues)] **Necesitas más inspiración?** [1] [Celery](https://github.com/celery/celery/blob/master/CONTRIBUTING.rst#other-bugs ) [2] [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#reporting-bugs) (incluye plantilla)
-->

## Cómo sugerir algo nuevo

En caso de que lo que quieras reportar no sea un error en un contenido existente
sino la sugerencia de agregar un nuevo contenido, puedes hacerlo también a través
de un *issue*.

> [!IMPORTANT]
> Cuando consideres que falta algo, probablemente no estés solo.
> [Busca](https://github.com/ucudal/ANDIS_Conceptos/issues?q=is%3Aissue+is%3Aopen)
> en la lista de *issues* si ya no existe uno similar al que estás considerando
> agregar; si no lo encuentras, [crea uno
> nuevo](https://github.com/ucudal/ANDIS_Conceptos/issues/new/choose).

Al crear un *issue* para pedir que se agregue el contenido que te gustaría ver,
asegúrate de que incluya las respuesta a las siguientes preguntas:

1. ¿Qué contenido está faltando? Incluye referencias a libros, sitios web, u
otros recursos útiles para encontrar lo que estás sugiriendo
2. ¿Por qué es necesario?
3. ¿Cómo deberíamos agregarlo?

<!--
TODO: Revisar estas fuentes

[fuente: [Elasticsearch](https://github.com/elastic/elasticsearch/blob/master/CONTRIBUTING.md#feature-requests)] **Necesitas más inspiración?** [1] [Hoodie](https://github.com/hoodiehq/hoodie/blob/master/CONTRIBUTING.md#feature-requests) [2] [Ember.js](https://github.com/emberjs/ember.js/blob/master/CONTRIBUTING.md#requesting-a-feature)
-->

<!-- TODO: Definir si vamos a tener un proceso de revisión>
# Proceso de Revisión del código

### Explica que necesita una contribución para ser aceptada luego de que se hace el submit.

Quién la revisa? Quien necesita firmar antes de que sea aceptada? Cuando debería
esperar el contribuidor que le respondas? Cómo puede tener un contribuidor
acceso a hacer commits, si fuese necesario?

> El core team revisa los Pull Requests semanalmente en una junta tripartita que
> se lleva a cabo en un Google Hangout público. El hangout se anuncia en las
> actualizaciones semanales y son enviados a la lista puppet-dev. Las notas son
> publicadas en el repo de Puppet Community community-triage e incluye un enlace
> a la grabación del hangout en YouTube. Luego de que se da la retroalimentación
> se esperan respuestas en las siguientes dos semanas. Luego de ello puede que
> se cierre el pull request debido a la inactividad.

[fuente: [Puppet](https://github.com/puppetlabs/puppet/blob/master/CONTRIBUTING.md#submitting-changes)] **Necesitas más inspiración?** [1] [Meteor](https://meteor.hackpad.com/Responding-to-GitHub-Issues-SKE2u3tkSiH ) [2] [Express.js](https://github.com/expressjs/express/blob/master/Contributing.md#becoming-a-committer) -->

## Convenciones

La documentación en este repo está creada utilizando el lenguaje
[Markdown](https://en.wikipedia.org/wiki/Markdown). Es un lenguaje que permite
crear texto con formato utilizando un editor de texto plano.

Mira los siguientes recursos para conocer más sobre este lenguaje:

* [Escritura y formato básico](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).
Lee esta guía primero para conocer lo básico que se necesita al editar
documentos en Markdown.
* [Edición avanzada](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting).
Lee esta otra guía para ver cómo crear tablas, bloques de código, diagramas,
etc.
* [Guía básica](https://markdownguide.offshoot.io/basic-syntax/). Una guía
  básica de lo que se puede hacer con Markdown.
* [Guía avanzada](https://markdownguide.offshoot.io/extended-syntax/). Una guía
  avanzada para usuarios de Markdown.
* [Markdown](https://daringfireball.net/projects/markdown/). Sitio de John
Grubber, uno de los creadores
* [Edición de Markdown en Visual Studio Code](https://code.visualstudio.com/docs/languages/markdown).
  Funcionalidades de Visual Studio Code para la edición de Markdown.

### Edición

Usamos [Visual Studio Code](https://code.visualstudio.com/download) para editar
los archivos de este repo. Aunque puedes usar cualquier editor de texto, este
documento asume que usas ese editor de código.

> [!TIP]
> Como probablemente uses el editor en otros proyectos, considera crear un
> perfil antes de agregar estas extensiones que te sugerimos a continuación.
> Consulta [este link](https://code.visualstudio.com/docs/editor/profiles) para
> obtener más información sobre los perfiles en Visual Studio Code.

Instala las siguientes extensiones que son útiles para facilitar la edición:

* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker):
  Corrector ortográfico para el texto.
* [Code Spell Checker - Spanish](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker-spanish):
  Corrector ortográfico para idioma español.
* [Markdown Checkboxes](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-checkbox):
  Agrega compatibilidad con casillas de verificación a la vista previa de
  Markdown.
* [Markdown Emoji](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-emoji):
  Agrega compatibilidad con la sintaxis de emoji a la vista previa de Markdown.
* [Markdown Footnotes](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-footnotes):
  agrega compatibilidad con la sintaxis de ^notas al pie a la vista previa de
  Markdown.
* [Markdown Preview GitHub Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles):
  Utiliza el estilo de GitHub en la vista previa de Markdown.
* [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid):
  Agrega soporte para diagramas en Mermaid.
* [Markdown yaml Preamble](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid):
  Aunque no usamos actualmente las *front matters* de YAML, podríamos usarlas en
  el futuro y esta extensión es recomendada.
* [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint):
  *Linting* de Markdown y controles de estilo.

Otras extensiones útiles:

* [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense):
  Para auto-completar de nombres de archivos.
* [Rewrap](https://marketplace.visualstudio.com/items?itemName=stkb.rewrap):
  Para formatear el ancho del archivo a cierto número de columnas, que en
  nuestro caso es 80.
* [Numbered Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.numbered-bookmarks):
  Para navegar fácilmente dentro de un archivo mediante marcadores.
* [Print](https://marketplace.visualstudio.com/items?itemName=pdconsec.vscode-print):
  Permite imprimir archivos Markdown.

Además, esta es la configuración sugerida del editor y sus extensiones:

```json
{
  "files.autoSave": "afterDelay",
  "git.enableSmartCommit": true,
  "window.commandCenter": true,
  "cSpell.language": "en,es-ES",
  "editor.renderWhitespace": "selection",
  "editor.wordWrapColumn": 120,
  "markdown.validate.enabled": true,
  "markdown.updateLinksOnFileMove.enabled": "prompt",
  "rewrap.wrappingColumn": 80,
  "rewrap.autoWrap.enabled": true,
  "workbench.editor.untitled.hint": "hidden",
  "markdown.validate.enabled": true,
  "markdown.updateLinksOnFileMove.enabled": "prompt",
  "workbench.startupEditor": "none",
}
```

Para verificar los links usamos la herramienta Linkspector disponible
[aquí](https://github.com/UmbrellaDocs/linkspector). La puedes ejecutar a
demanda con el comando `linkspector check`. La [configuración existente](/.linkspector.yml) considera
el código HTTP 103 —además de 200, 201 y 204— como un correcto.

### Organización del contenido

El contenido está organizado en estas carpetas:

1. Entregable proyecto
2. Técnicas y herramientas
3. Plantillas
4. Conceptos
5. Unidades temáticas

Cada carpeta tiene un archivo Markdown ‑con extensión `.md`‑ cuyo nombre
coincide con el de la carpeta y sirve como tabla de contenido de la carpeta
‑excepto que usa dos guiones bajos `__` en lugar de uno para separar el número
del resto de nombre; esto para que quede ordenado antes de los demás archivos‑:
por ejemplo, la carpeta `4_Conceptos` tiene un archivo `4__Conceptos.md`.

> [!IMPORTANT]
> Mira la sección [Nombres de archivos](#nombres-de-archivos), más adelante en
> este documento, para conocer más detalles sobre las convenciones sobre los
> nombres de archivos y carpetas.

En algunas carpetas el contenido está organizado de manera jerárquica, pero no
utilizamos sub carpetas, sino que agregamos niveles a los nombres de archivos:
por ejemplo, el tema `5. Unidades temáticas` tiene algunos de los siguientes
niveles:

* <span>5.</span> Unidades temáticas
  * 5.1
    * 5.1.1
    * 5.1.2
  * 5.2
    * 5.2.1

Los nombres de los archivos en la carpeta `5_Unidades_tematicas` comienzan con:

`5_Unidades_tematicas`

`5__Unidades_tematicas.md`

`5_1__⋯.md`

`5_1_1⋯.md`

`5_1_2⋯.md`

`5_2__⋯.md`

`5_2_1⋯.md`

### Referencias a las fuentes

Respetamos la propiedad intelectual dando atribución al origen del contenido
incluido en los documentos.

Cuando el contenido de un documento fue tomado de una fuente, incluimos el texto
"Tomado de", seguido de una notas al pie, al final de la primera frase del
documento.

#### Ejemplo

> Esta es la plantilla para un requerimiento funcional o no funcional. Tomado de
> [^1].

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.

#### Fuente

``` markdown
Esta es la plantilla para un requerimiento funcional o no funcional. Tomado de [^1].

[^1]: Robertson, S. & Robertson, J. (2012). Mastering the Requirements Process:
Getting Requirements Right, 3<sup>rd</sup> Edition. Addison-Wesley Professional.
```

> [!NOTE]
> Aunque las notas al pie aparecen al final del documento, en el documento en
> Markdown ponemos la referencia inmediatamente después de donde de usa, y no al
> final para que sea más fácil editar el documento.

En el caso de una imagen, el texto "Tomado de" va al final del pie de foto,
seguido de una nota al pie.

> [!TIP]
> Mira [este link](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#footnotes)
> para tener más información sobre cómo crear notas al pie en Markdown.

Cuando usamos tablas en HTML no es posible agregar notas al pie. En ese caso
las referencias las agregamos así:

#### Ejemplo

<table>
    <tr>
        <td>
            Ver debajo <span id="back_ref_1"><a href="#ref_1">↓</a></span>
        </td>
      </tr>
</table>

-----

<span id="ref_1">Robertson, S. & Robertson, J. (2012). Mastering the
Requirements Process: Getting Requirements Right, 3<sup>rd</sup> Edition.
Addison-Wesley Professional.</span><a href="#back_ref_1" title="Volver...">↩︎</a>

#### Fuente

```html
<table>
    <tr>
        <td>
            Ver debajo <span id="back_ref_1"><a href="#ref_1">↓</a></span>
        </td>
      </tr>
</table>

-----

<span id="ref_1">Robertson, S. & Robertson, J. (2012). Mastering the
Requirements Process: Getting Requirements Right, 3<sup>rd</sup> Edition.
Addison-Wesley Professional.</span><a href="#back_ref_1" title="Volver...">↩︎</a>
```

### Leyendas de figuras

Al incluir figuras en un documento las acompañamos de una pequeña leyenda debajo
que explica o describe brevemente la figura. Esa descripción se utiliza también
como como texto alternativo al embeber la imagen. Lo mismo hacemos con las
tablas cuando resulta necesario o conveniente.

Estas leyendas las incluimos en itálica, asegurándonos de asociarles un número
según la cantidad de figuras presentes hasta el momento en el documento,
empezando por uno ‑1‑. Si hay figuras y tablas en un mismo documento, las
contamos por separado, por lo que puede haber una *Tabla 1* y una *Figura 1* en
un mismo documento. `Figura` o `Tabla` se separa del resto de la leyenda por `:`
‑dos puntos‑.

Antes de la imagen agregamos un elemento HTML `anchor` cuyo identificar `id` es
`figura` o `tabla`, según corresponda, seguido del número respectivo. Esto
permite hacer referencia a esa figura con `[Figura N](#figura-n)` como se
muestra más abajo.

Al incluir las leyendas de las figuras y tablas de esta forma, podemos
crear referencias desde dentro y fuera del documento.

#### Ejemplo

<a id="figura-1"/>

![El ciclo de vida DAD](/diagrams/DAD_Lifecycle.svg)

*Figura 1: El ciclo de vida DAD.*

§

Ver [Figura 1](#figura-1).

#### Fuente

```markdown
<a id="figura-1"/>

![El ciclo de vida DAD](/diagrams/DAD_Lifecycle.svg)

*Figura 1: El ciclo de vida DAD.*

§

Ver [Figura 1](#figura-1).
```

> [!NOTE]
> Hay configurado un *snippet* `figura` para insertar el código necesario para
> incluir una figura.

### Viñetas

Usamos el símbolo `*` para las viñetas; no usamos `-`.

### Incisos

Cuando queremos incluir en una frase un texto en forma de aclaración o
explicación ‑lo que en gramática se conoce como
[inciso](https://www.rae.es/drae2001/inciso#)‑, usamos `‑` que corresponde con
la [raya](https://www.rae.es/dpd/raya) o `EM DASH`, código Unicode `U+2014` o
UTF-8 `E28094`; no usamos `-` o guión; una [Github
Action](https://github.com/marketplace/actions/find-and-replace) reemplaza ese
carácter por `NON-BREAKING HYPHEN`, código Unicode `U+2011` o UTF-8 `E28091`.

Puedes generar una raya:

* En Windows: con <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>-</kbd>
* En Mac: con <kbd>Option</kbd> + <kbd>Shift</kbd> + <kbd>-</kbd>

### Palabras en inglés u otros idiomas

Cuando no existe una traducción ampliamente aceptada de una palabra en inglés
u otro idioma al español, preferimos usar la palabra original; esa palabra la
escribimos *en cursiva*.

### Notas, consejos, avisos, etcétera

Incluimos notas ‑*notes*‑, consejos ‑*tips*‑, avisos ‑*warnings*‑, etc. usando
la notación de citas en bloque según se describe
[aquí](https://github.com/orgs/community/discussions/16925).

#### Ejemplo

> [!NOTE]
> Destaca información que los usuarios deben tener en cuenta, incluso cuando hojean.

> [!TIP]
> Información opcional para ayudar al usuario a tener más éxito.

> [!IMPORTANT]
> Información crucial necesaria para que los usuarios tengan éxito.

> [!WARNING]
> Contenido crítico que exige atención inmediata del usuario debido a riesgos potenciales.

> [!CAUTION]
> Consecuencias potenciales negativas de una acción.
</br>

#### Fuente

```text
> [!NOTE]
> Destaca información que los usuarios deben tener en cuenta, incluso cuando hojean.

> [!TIP]
> Información opcional para ayudar al usuario a tener más éxito.

> [!IMPORTANT]
> Información crucial necesaria para que los usuarios tengan éxito.

> [!WARNING]
> Contenido crítico que exige atención inmediata del usuario debido a riesgos potenciales.

> [!CAUTION]
> Consecuencias potenciales negativas de una acción.
```

### Nombres de archivos

No usamos caracteres especiales o letras con tilde en los nombres de archivos.

Tampoco usamos espacios, separamos las palabras que componen el nombre con guión
bajo `_`.

El nombre comienza con mayúscula.

<!-- TODO: evaluar incluir otras convenciones para commits, issues, etc.

### Explica si tienes alguna convención de mensajes de commit.

**Necesitas más inspiración?** [1] [Angular](https://github.com/angular/material/blob/master/.github/CONTRIBUTING.md#submit) [2] [Node.js](https://github.com/nodejs/node/blob/master/CONTRIBUTING.md#step-3-commit)

### Explica si usas alguna convención para el etiquetado de issues.

**Necesitas más inspiración?** [1] [StandardIssueLabels](https://github.com/wagenet/StandardIssueLabels#standardissuelabels) [2] [Atom](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#issue-and-pull-request-labels)

-->

## TODOs

Para manejar la lista de TODO usamos la [extensión Todo
Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
que permite ver los TODO directamente en el editor.

También usamos la [*GitHub action* TODO to
Issue](https://github.com/marketplace/actions/todo-to-issue) para convertir los
nuevos TODO en *issues*.

<!-- Lo siguiente debe ser lo último de este archivo -->

> [!NOTE]
> La línea que ves debajo y el texto que le sigue son la nota al pie que
> mostramos en la sección de [referencias](./CONTRIBUTING.md#fuente).
