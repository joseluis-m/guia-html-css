# Introducción

Esta guía es una **página web** que resume los fundamentos de HTML y CSS, orientados a los módulos de Formación Profesional de **Administración de Sistemas Informáticos en Red (ASIR)**, **Desarrollo de Aplicaciones Web (DAW)** y **Desarrollo de Aplicaciones Multiplataforma (DAM)**.

El objetivo es proporcionar una referencia accesible y completa para estudiantes, con contenidos teóricos, buenas prácticas y ejemplos prácticos. La página está construida con una estructura semántica clara, un diseño moderno y limpio, y se puede navegar mediante enlaces internos. Cada sección incluye explicaciones detalladas y el código HTML está comentado para facilitar la comprensión. Finalmente, se aportan ejercicios, retos y recursos adicionales para profundizar en el aprendizaje.

<br>

# Estructura y accesibilidad de la página

Una página web bien estructurada en HTML utiliza **etiquetas semánticas** para darle significado al contenido. Esto mejora la accesibilidad y la usabilidad, pues tanto los navegadores como las tecnologías de asistencia (lectores de pantalla) pueden interpretar mejor la página. Por ejemplo, en lugar de usar contenedores genéricos `<div>` para todo, conviene emplear etiquetas como `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` y `<footer>` para delimitar las distintas partes de la página. Estas etiquetas describen el tipo de contenido que envuelven, dando contexto a usuarios y motores de búsqueda. Un lector de pantalla, por ejemplo, puede saltar directamente al `<nav>` para navegar por el sitio o ignorar un `<aside>` si se indica contenido complementario, mejorando la **experiencia de accesibilidad** para usuarios con discapacidad visual.

En esta guía, la estructura HTML general sigue estas buenas prácticas semánticas. Hay un `<header>` que contiene el título y la barra de navegación interna, un `<main>` con varias secciones (`<section>`) para los temas principales, y un `<footer>` con información final. La navegación interna (usando una lista de enlaces `<a href="#seccion">`) permite saltar a cada sección dentro de la misma página, mejorando la **usabilidad**. Además, se aplican principios de diseño responsive para que la página sea legible en distintos dispositivos (ver sección de CSS).

En cuanto a **accesibilidad**, aparte de las etiquetas semánticas, se han seguido otras recomendaciones: por ejemplo, todas las imágenes incluyen atributos `alt` descriptivos; los formularios (que veremos más adelante) utilizan etiquetas `<label>` asociadas a sus campos para facilitar su uso con lectores de pantalla; y se cuida el contraste de colores y la legibilidad de las tipografías. También se establece el atributo `lang="es"` en el `<html>` para indicar que el contenido está en español, ayudando tanto a buscadores como a tecnologías de apoyo a procesar correctamente el idioma.

Por último, la estructura bien definida no solo ayuda a accesibilidad, **SEO** y navegación, sino también al mantenimiento del código. Un HTML semántico y limpio es más fácil de entender y actualizar por otros desarrolladores en proyectos colaborativos. En resumen, esta página ejemplifica una organización lógica del contenido y aplica estándares web modernos para ser clara, accesible y fácil de ampliar.

<br>

# Fundamentos de HTML

En esta sección se cubren los contenidos esenciales de HTML, incluyendo las etiquetas básicas y la estructura de un documento, el uso de etiquetas semánticas, la creación de formularios con validación integrada, y nociones de SEO básico aplicadas al HTML.

## Etiquetas básicas y estructura semántica

Un documento HTML comienza con la declaración de tipo `<!DOCTYPE html>` (para indicar al navegador que usamos HTML5), seguida de la etiqueta raíz `<html lang="es">` que engloba todo el contenido. Dentro de `<html>` diferenciamos dos partes: el **head** (`<head>`) y el **body** (`<body>`). En el `<head>` colocamos meta-información sobre la página, como el `<title>` (título que aparece en la pestaña del navegador y en resultados de búsqueda), la codificación de caracteres (`<meta charset="UTF-8">` para soportar caracteres especiales), la meta-descripción para SEO, enlaces a hojas de estilo CSS, etc. En el `<body>` va el contenido visible de la página estructurado con las etiquetas apropiadas.

Las **etiquetas HTML básicas de contenido** incluyen los encabezados `<h1>` a `<h6>` (siendo `<h1>` el título principal y los demás subtítulos por orden de jerarquía), párrafos `<p>` para texto, enlaces `<a>` para hipervínculos, imágenes `<img>` (siempre con atributo `alt` para texto alternativo), listas `<ul>` (no ordenadas, con viñetas) y `<ol>` (ordenadas, numéricas) junto con `<li>` para cada elemento de lista, y otras como `<strong>` o `<em>` para dar énfasis a texto en **negrita** o *cursiva*. Además, se pueden emplear etiquetas para estructurar datos y contenido complementario: para presentar información en formato tabular se utilizan `<table>`, `<thead>`, `<tbody>`, `<tfoot>`, `<tr>`, `<th>` y `<td>`; para mostrar ejemplos de código se recomienda el uso conjunto de `<pre>` y `<code>`; y para agrupar imágenes con una leyenda se emplean `<figure>` y `<figcaption>`.

A medida que creamos la estructura del contenido, es importante usar **HTML semántico**. Por ejemplo, en vez de muchos `<div>` anidados sin significado, se usan contenedores semánticos: `<header>` para el encabezado de la página o de una sección, `<nav>` para agrupación de enlaces de navegación, `<main>` para envolver el contenido principal del documento, `<section>` para secciones temáticas dentro del `<main>`, `<article>` para contenido que podría ser independiente (una publicación, noticia o artículo), `<aside>` para contenidos relacionados pero secundarios (como barras laterales, citas, información adicional) y `<footer>` para el pie de página.

Este enfoque semántico mejora la comprensión del documento por parte de los buscadores y ayuda al **SEO**: los motores de búsqueda utilizan estas etiquetas para entender mejor la estructura y contenido, lo que influye en la clasificación en resultados. Además, contribuye a la **accesibilidad**, facilitando la navegación por secciones usando ayudas técnicas. En el código de la página de esta guía, cada sección está marcada con sus etiquetas correspondientes y comentarios que indican su propósito (por ejemplo, `<!-- SECCIÓN: Fundamentos de HTML -->` antes del bloque de contenido de HTML).

## Formularios y validación en HTML5

Los **formularios** son una parte fundamental de muchas páginas web, ya que permiten la entrada de datos del usuario. En HTML, un formulario se define con `<form>` y suele incluir controles como campos de texto (`<input type="text">`), campos de correo (`<input type="email">`), contraseñas (`<input type="password">`), casillas de verificación (`<input type="checkbox">`), botones de opción (`<input type="radio">`), selectores desplegables (`<select>` y `<option>`), áreas de texto multilinea (`<textarea>`), entre otros. Cada control debe llevar un atributo `name` para identificar el dato que envía y es buena práctica asociar un `<label for="idCampo">` a cada control (mediante el atributo `id` en el control) para que el formulario sea accesible: al hacer click en la etiqueta, el campo correspondiente recibe el foco.

HTML5 introdujo una serie de **atributos de validación** incorporados que permiten verificar la información ingresada por el usuario **sin necesidad de JavaScript**. Por ejemplo, podemos marcar un campo como obligatorio con `required`, definir patrones de formato con `pattern` (expresiones regulares), establecer límites numéricos con `min` y `max`, longitudes mínimas/máximas de texto con `minlength` y `maxlength`, entre otros. Los campos de tipo email, URL, número, etc., ya llevan implícitas ciertas validaciones de formato. Cuando un formulario utiliza estos atributos, los navegadores modernos impedirán el envío si los datos no cumplen las restricciones, mostrando mensajes de error predeterminados (que incluso se pueden personalizar con atributos como `title` o usando la API de Constraint Validation en JavaScript si se desea mejorar la interfaz de error).

Un ejemplo sencillo incluido en esta página es un pequeño formulario de contacto donde se utiliza `required` para campos obligatorios y `type="email"` para validar automáticamente que el correo tenga un formato válido. Gracias a HTML5, al intentar enviar el formulario, el navegador verificará estos requisitos y avisará al usuario si olvidó llenar algo o si el formato es incorrecto, mostrando mensajes como "Este campo es obligatorio" o "Introduzca una dirección de correo electrónico válida". **Es importante destacar** que la validación del lado del cliente (con HTML5 o incluso con JavaScript) no sustituye la validación del lado del servidor; siempre se debe verificar en el servidor los datos recibidos, por seguridad. Aun así, estas validaciones en HTML mejoran la experiencia de usuario al dar una retroalimentación inmediata.

En el código, hemos comentado cada parte del formulario para explicar su rol (por ejemplo, `<!-- Campo de email con validación HTML5 -->`). También se ilustra el uso del atributo `placeholder` para mostrar texto de ayuda dentro de los campos antes de que el usuario escriba, y cómo agrupar controles relacionados con `<fieldset>` y `<legend>` (por ejemplo, para un grupo de botones de opción).

## SEO básico en HTML

Aunque el posicionamiento en buscadores (SEO) es un tema extenso que involucra muchos factores, desde el punto de vista de HTML hay algunas prácticas básicas que se han aplicado en esta guía:

- **Título de la página único y descriptivo**: La etiqueta `<title>` en el `<head>` contiene un título claro ("Guía integral de HTML y CSS...") que describe el contenido. Los buscadores muestran este título en los resultados, y debe tener idealmente menos de ~60 caracteres y contener palabras clave relevantes.
- **Meta descripción**: En el `<head>` se incluye `<meta name="description" content="...">` con un resumen de la página. Esta descripción suele aparecer debajo del título en los resultados de Google. Una meta-descripción bien redactada puede mejorar la tasa de clicks hacia tu página (por ejemplo, la descripción de esta guía menciona que es un recurso integral en español para fundamentos de HTML/CSS en FP, lo que la hace atractiva para el público objetivo).
- **Uso de encabezados jerárquicos**: Estructurar el contenido con `<h1>` para el título principal y `<h2>`, `<h3>`, etc. para subsecciones ayuda a los buscadores a entender la organización del contenido. En esta página, el `<h1>` es el título de la guía, y cada sección principal tiene un `<h2>` (ej.: "Fundamentos de HTML", "Fundamentos de CSS", etc.), con posibles `<h3>` para subdivisiones internas. Mantener esta jerarquía coherente es importante para SEO y accesibilidad, ya que refleja la importancia relativa de cada sección.
- **Etiquetas semánticas**: Como se mencionó, ayudan al SEO al proporcionar contexto. Por ejemplo, Google reconoce `<nav>` como navegación, `<article>` como contenido autónomo, etc., lo cual puede influir positivamente. **Las etiquetas semánticas son esenciales para SEO** ya que los motores de búsqueda las usan para entender mejor la estructura de la página.
- **Texto alternativo en imágenes**: Cualquier imagen (`<img>`) tiene atributo `alt` descriptivo. No solo es vital para usuarios que no pueden ver la imagen, sino que permite a Google indexar y entender el contenido de la imagen. Por ejemplo, si en una sección se muestra un diagrama o logo, el alt lo describe ("Diagrama del modelo de caja en CSS", etc.).
- **URLs amigables y dominio**: Este punto aplica más cuando uno despliega el sitio; en nuestro caso, al ser una sola página local o para GitHub Pages, la URL será fija. En un proyecto real, se recomienda usar URLs legibles y relacionadas con el contenido.
- **Meta etiquetas adicionales**: Por simplicidad, esta guía no profundiza en meta-etiquetas avanzadas (como `meta keywords` –que hoy en día tienen poca relevancia–, o las metaetiquetas de Open Graph para redes sociales). Sin embargo, cabe destacar que **las meta-etiquetas más importantes para SEO** son el título y la descripción, además de la correcta estructuración con encabezados. Una frase célebre es que *"las meta etiquetas son la base del SEO"*, siendo de lo primero que se configura al crear una página web.

En resumen, siguiendo estas prácticas HTML básicas (estructura semántica, títulos y metadatos adecuados, alt en imágenes, etc.), sentamos una buena base para que la página sea indexada correctamente por los motores de búsqueda y sea accesible para los usuarios. Los contenidos de esta guía están organizados pensando en ello, de modo que resulten claros tanto para usuarios como para buscadores.

<br>

# Fundamentos de CSS

A continuación, se abordan los temas fundamentales de CSS necesarios para dar estilo y diseño a las páginas HTML: cómo seleccionar elementos para aplicar estilos, en qué consiste el modelo de caja y cómo manejar espacios/márgenes, cómo lograr un diseño adaptable a distintos dispositivos con media queries, y sistemas de diseño modernos con Flexbox y Grid, además de pseudo-clases y animaciones para interactividad.

## Selectores CSS

Los **selectores** nos permiten indicar a qué elementos HTML se aplican ciertas reglas CSS. CSS ofrece multitud de tipos de selectores, pero los más usados incluyen:

- **Selector de elemento** (o etiqueta): se refiere a todas las etiquetas de un tipo dado. Ejemplo: `p { ... }` aplicará a todos los párrafos `<p>` de la página; `header { ... }` al elemento `<header>`, etc.
- **Selector de clase**: se define en HTML con el atributo `class`. En CSS se denota con un punto `.` seguido del nombre de la clase. Ejemplo: `.destacado { color: red; }` afecta a cualquier elemento con `class="destacado"`. Es útil para aplicar estilos a grupos específicos de elementos, independientemente de su tipo.
- **Selector de ID**: usa el atributo `id` de un elemento, y en CSS se denota con `#`.  
  Por ejemplo, `#menu { ... }` estilizará el elemento con `id="menu"`.  
  Los IDs deben ser únicos en la página, por lo que este selector apunta como máximo a un elemento. Su uso se reserva para casos necesarios (a veces para JavaScript), pero en CSS moderno se prefieren más las clases que los IDs por flexibilidad.
- **Selectores de descendiente/combinadores**: permiten seleccionar elementos en función de su posición en el árbol DOM. Por ejemplo, `main p { ... }` estiliza solo los `<p>` que estén dentro de `<main>`. Otro ejemplo, `section#intro em { ... }` aplicaría a `<em>` dentro de `<section id="intro">`. Existen combinadores de hijo directo (`>`), de hermano adyacente (`+`), de hermano general (`~`), etc., para casos más precisos.
- **Selectores de atributo**: seleccionan elementos según la presencia o valor de un atributo. Por ejemplo, `input[type="email"] { ... }` podría dar estilo a campos de entrada de email, o `a[target="_blank"] { ... }` a enlaces que abren en nueva pestaña.
- **Selectores universales**: el asterisco `*` selecciona *todos* los elementos. Se usa con cuidado, típicamente en reseteos o para heredar estilos globales (`* { box-sizing: border-box; }` es un ejemplo común para aplicar el modelo de caja alternativo a todo elemento, de lo cual hablaremos en el modelo de caja).
- **Selectores de pseudo-clase**: se tratan en detalle más abajo, pero mencionar aquí que notaciones como `a:hover` o `input:focus` también actúan como selectores que eligen elementos en cierto estado.

Al escribir CSS, hay que considerar la **especificidad** de los selectores: por ejemplo, un selector de ID tiene más peso que uno de clase, y este a su vez más que uno de elemento. Si dos reglas entran en conflicto, la de mayor especificidad (o la última definida si la especificidad es igual) prevalecerá. Para mantener el código manejable, es recomendable no abusar de selectores demasiado complejos; a menudo una combinación de clases bien pensadas es suficiente para seleccionar lo que queremos estilizar.

En la hoja de estilo de esta guía, verás ejemplos de todos estos tipos de selectores. Por ejemplo, usamos selectores de elemento para estilo general de tipografía (`body`, `h1`, `h2`, etc.), selectores de clase para componentes específicos (como `.codigo` para formatear bloques de código de ejemplo), y selectores anidados (combinadores) para casos como `.navbar a` (enlaces dentro de la barra de navegación).  
Los comentarios en el CSS explican la intención de cada bloque de estilos.

## El modelo de caja (CSS Box Model)

![Diagrama del modelo de caja en CSS](https://media.gcflearnfree.org/content/5ef2084faaf0ac46dc9c10be_06_23_2020/box_model.png "CSS Box Model")

En CSS, cada elemento HTML se representa como una **caja rectangular** compuesta por varias áreas: el contenido, el relleno (*padding*), el borde (*border*) y el margen (*margin*). En otras palabras, todo lo que vemos en la página está dentro de cajas, y comprender cómo funcionan es clave para controlar el diseño. **Cada caja tiene un área de contenido** (que contiene el texto, imagen u otros elementos hijos) y opcionalmente áreas de relleno alrededor del contenido, un borde alrededor del relleno, y un margen externo fuera del borde. El tamaño de cada área se puede ajustar mediante propiedades CSS:

- `width`/`height`: afectan el área de contenido
- `padding`: el espacio entre contenido y borde
- `border-width`: (y estilo/color de borde) para el borde
- `margin`: para el espacio externo

En el diagrama (y en las herramientas de desarrollo de los navegadores, que suelen mostrar este modelo visualmente), podemos identificar:

- **La caja de contenido** (*content box*) en el centro, cuyo tamaño depende de lo que contiene o de medidas que le demos
- **El padding** alrededor, generalmente transparente, que empuja el contenido hacia adentro
- **El border** alrededor del padding, con grosor y color definidos
- **El margin** fuera del borde, que es espacio en blanco que separa esta caja de otras cajas vecinas

### ¿Por qué es importante esto?

Porque cuando definimos, por ejemplo, `width: 200px` para un elemento, por defecto eso **no** incluye el padding ni el border.  
Si además le damos `padding: 20px` y un `border: 2px solid`, el espacio total que ocupará la caja horizontalmente será: `200 + 20 + 20 + 2 + 2 = 244px`. A veces esto sorprende a principiantes. Si quisiéramos que esos 200px incluyeran todo (contenido + padding + border), podríamos usar la propiedad `box-sizing: border-box;` en ese elemento (o globalmente para todos, ya que muchos frameworks lo hacen por defecto). Con `box-sizing: border-box`, el cálculo del ancho total cambia para que `width` **sí** incluya el padding y el border, facilitando definir tamaños fijos sin sorpresas.

Además, el **margin** tiene la particularidad de colapsar verticalmente en algunos casos (por ejemplo, dos `<p>` seguidos cada uno con margin-top/margin-bottom pueden compartir parte del margen en vez de sumarlos, según las reglas de colapso de márgenes). Esto hay que tenerlo en cuenta al espaciar elementos.

En la hoja CSS de esta guía, hemos definido algunos estilos relacionados con el modelo de caja: un reset para establecer `box-sizing: border-box` globalmente (así manejar anchos es más intuitivo), márgenes por defecto para títulos y párrafos, y padding interno en ciertos contenedores para separar el contenido de sus bordes. Cada sección del contenido quizás tenga un `padding: 2rem` alrededor, por ejemplo, para que el texto no pegue con el borde de la ventana. Los comentarios en el CSS señalan estas decisiones.

En resumen, dominar el modelo de caja permite controlar correctamente **espaciados y tamaños** en CSS. Es un concepto fundamental: **contenido + padding + border + margin = espacio total ocupado por el elemento**. Si esto se entiende bien, resolver problemas de diseño como "¿por qué mi elemento se desborda?" o "¿cómo centro esta caja?" se vuelve más sencillo.

## Diseño responsive con *media queries*

Hoy en día es indispensable que un sitio web se vea bien y sea usable tanto en pantallas grandes de ordenador como en tablets o móviles. El **diseño responsive** (responsivo, *responsive design*) es la técnica que permite adaptar el diseño a diferentes tamaños de pantalla. En CSS, la herramienta principal para lograrlo son las **media queries** (consultas de medios).

Una media query permite aplicar un conjunto de estilos solo si se cumple una condición, típicamente relacionada con las características del dispositivo o ventana. El caso más común es usar la anchura de la pantalla (*viewport*) como criterio. Por ejemplo, podríamos escribir en el CSS:

```css
@media (max-width: 600px) {
  /* Estilos CSS para móviles: se aplican cuando el ancho es 600px o menos */
  nav ul {
    flex-direction: column;
  }
  body {
    font-size: 16px;
  }
}
```

En esta guía, se ha adoptado una filosofía **mobile-first**: se definen primero los estilos para pantallas pequeñas (móviles), y luego mediante media queries se ajusta o mejora el diseño para pantallas más grandes. Por ejemplo, el menú de navegación en el header quizás en móvil se muestre como un menú desplegable vertical (o un ícono de "menú" hamburguesa, si se implementara JavaScript), mientras que en escritorio ese mismo menú se muestra horizontalmente. De hecho, en nuestro CSS tenemos algo inverso al ejemplo anterior: el `nav ul` está en columna por defecto (pensando en móvil), y mediante `@media (min-width: 601px)` lo ponemos en fila (`flex-direction: row`) para pantallas más amplias.

Otros usos comunes de media queries incluyen ajustar tamaños de fuente, cambiar layouts de múltiples columnas a una sola columna, ocultar elementos menos importantes en pantallas pequeñas, o cambiar imágenes por versiones más pequeñas. Por ejemplo, podríamos tener `.sidebar { display: block; }` en escritorio y `.sidebar { display: none; }` en móvil si una barra lateral no es crítica en pantallas pequeñas.

Es importante elegir algunos **puntos de corte (breakpoints)** adecuados, basados en el contenido y no solo en dispositivos específicos. Un diseño típico puede tener breakpoints alrededor de:

- **600px** (teléfonos en modo vertical)
- **768px** (tablet vertical o teléfonos grandes)
- **992px** (tablet horizontal o pantallas medianas)
- **1200px** (desktop grande)

En esta página, dado que principalmente es texto, con un diseño de una columna, no fueron necesarias muchas variaciones; pero se incluyó al menos una para demostrar la técnica.

### ¿Por qué preocuparnos por esto?

Además de la obvia mejora de experiencia de usuario, hoy día Google penaliza sitios que no sean móviles (*mobile-friendly*). De hecho, según un estudio citado por GoodFirms,  
**un diseño no adaptativo es la razón principal por la que un usuario abandona un sitio web** en dispositivos móviles. La capacidad de CSS para crear diseños fluidos o adaptativos sin crear sitios separados para móvil/escritorio es una gran ventaja.

En la práctica, para un diseño responsive efectivo también utilizamos unidades relativas como porcentajes o `em`/`rem` en vez de siempre píxeles, y herramientas como **Flexbox** y **Grid** (que veremos a continuación) que facilitan diseños flexibles. Esta guía usa medidas responsivas (por ejemplo, anchos máximos en porcentaje para imágenes, o la tipografía base en `em`) de manera que se pueda escalar fácilmente.

En el código CSS proporcionado, se pueden ver las **media queries** aplicadas (busca `@media` en el archivo CSS). Los comentarios explican qué cambio se hace en cada breakpoint. Por ejemplo: a cierto ancho, aumentar padding lateral del contenido para verse mejor en pantallas grandes, o reubicar la navegación.

## Layouts con Flexbox y Grid

CSS ha evolucionado y hoy contamos con **módulos de diseño avanzados** que facilitan la creación de layouts complejos sin recurrir a trucos como elementos flotantes.  
Los más importantes son **Flexbox** y **CSS Grid**:

### Flexbox (Flexible Box Layout)

Es un sistema de distribución en una dimensión (una fila horizontal o una columna vertical) muy útil para alinear y distribuir elementos en un contenedor.  
Flexbox está diseñado para manejar el layout **en una sola dirección** a la vez (horizontalmente o verticalmente). Un contenedor flex (`display: flex`) permite que sus elementos internos (flex items) se expandan o contraigan para llenar espacio disponible y para alinearlos fácilmente al inicio, final, centro, etc., tanto en eje principal como en eje perpendicular. Con Flexbox es sencillo (por ejemplo) centrar un elemento tanto horizontal como verticalmente (algo que con técnicas antiguas era engorroso). También permite reordenar elementos, distribuir espacio sobrante equitativamente o según proporciones (usando la propiedad `flex` en los items), y crear diseños responsive simples (por ejemplo, una barra de navegación donde algunos elementos ocupan más espacio que otros automáticamente).

**Ejemplos de uso de Flexbox en la guía**:

- La barra de navegación del header está construida con `display: flex` para alinear los enlaces en fila y separarlos con espacio entre ellos.
- En la sección de ejercicios, podríamos usar flexbox para colocar tarjetas de reto una al lado de la otra en filas.

**Propiedades clave de Flexbox**:

- `justify-content`: alineación horizontal de los items (al inicio, centro, fin, espacio equidistante, etc.).
- `align-items`: alineación vertical de los items dentro del contenedor flex.
- `flex-direction`: fila o columna.
- `flex-wrap`: si los elementos exceden el espacio, permitir que salten a otra línea.
- En los hijos: `flex-grow`, `flex-shrink`, `flex-basis` (o la abreviatura `flex`) para controlar cómo se dimensionan y ajustan.

En resumen, Flexbox es ideal para **diseños unidireccionales** y componentes, como barras de menú, galerías simples, tarjetas, pie de página distribuido, etc.

### Grid Layout

Es el módulo CSS diseñado para **diseño en dos dimensiones**, es decir, manejar filas y columnas a la vez. Con **CSS Grid** podemos definir una rejilla (*grid*) en un contenedor, especificando cuántas columnas y filas tiene, con qué tamaños (fijos en px, flexibles en %, o usando fracciones `fr`), y luego colocar los elementos hijos en esa rejilla según posiciones. Grid permite hacer layouts muy potentes. Por ejemplo, un esquema completo de una página: definir una cuadrícula de 3 columnas y 4 filas, donde la cabecera ocupa el ancho completo en la primera fila, el contenido principal ocupa un bloque central de las filas siguientes, una barra lateral ocupa las dos filas del lado derecho, etc. Todo esto con solo CSS, sin alterar el orden en HTML necesariamente.

Un contenedor se hace grid con `display: grid`. Podemos definir columnas con `grid-template-columns` y filas con `grid-template-rows`.

Por ejemplo: `grid-template-columns: 1fr 2fr 1fr;` define 3 columnas donde la del medio es el doble de ancha que las laterales. Podemos colocar hijos usando propiedades como: `grid-column: 1 / 3;`. Esto haría que ese elemento abarque desde la columna 1 hasta antes de la 3 (o sea, que cubra columnas 1 y 2). Grid también soporta nombrar áreas y ubicarlos por nombres, lo que hace muy legible la distribución.

En esta guía no se necesitaba un layout complejo de múltiples columnas para el contenido principal (es más bien una columna central de texto), pero para mostrar Grid hemos incluido un ejemplo en código: en la sección de "Ejemplos profesionales", los tres ejemplos (ASIR, DAW, DAM) se maquetan en una cuadrícula flexible. En pantallas anchas aparecen en tres columnas lado a lado, y automáticamente (gracias a Grid y a @media queries) en pantallas pequeñas se reorganizan en una sola columna. Esto se logró con unas pocas líneas de CSS Grid.

### Cuándo usar Flexbox o Grid

Flexbox se recomienda para diseños lineales (una barra, un componente, una fila de cards que se envuelven en la siguiente línea si hay muchas, etc.), mientras que Grid brilla en layouts globales de página o secciones enteras donde se necesita controlar ambas dimensiones al mismo tiempo (por ejemplo, una galería de fotos en un grid de 3x3). A veces se combinan: por ejemplo, puedes usar Grid para el layout general de la página (header, sidebar, main, footer) y dentro de cada área usar Flexbox para alinear elementos internos de esa sección.

En esta página de guía hemos documentado en los comentarios del CSS cómo se configuran estos sistemas. Cabe destacar que tanto Flexbox como Grid son ampliamente soportados por navegadores modernos. Aportan mucho al trabajo cotidiano, reduciendo la necesidad de hacks. Su uso práctico se ve en el código, por ejemplo:

- `.nav-links { display: flex; justify-content: space-around; }` para distribuir equitativamente los enlaces de navegación.
- `.ejemplos { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1rem; }` para colocar tres bloques (ASIR, DAW, DAM) en un grid con espacio (*gap*) entre ellos.

## Pseudo-clases y animaciones CSS

Las **pseudo-clases** en CSS permiten aplicar estilos a elementos **según su estado** o según ciertas condiciones, sin necesidad de clases extra ni JavaScript. Se escriben con dos puntos `:` antes del nombre.

Algunas de las más comunes:

- `:hover`: se activa cuando el cursor del usuario está **encima** de un elemento (por ejemplo, sobre un enlace o botón). Suele utilizarse para efectos visuales como cambiar el color de un botón al pasar el ratón. En esta página, los enlaces de la barra de navegación cambian de apariencia con *hover* para indicar interactividad.
- `:active`: estado **activo** de algunos elementos, por ejemplo, un enlace o botón en el momento de ser pulsado (click sostenido).
- `:focus`: cuando un elemento (generalmente enlace o campo de formulario) tiene el foco, es decir, está seleccionado para recibir entrada (por ejemplo, un input en el que hemos hecho click o navegado con TAB). Es importante estilizar el *focus* (como con `outline`) para accesibilidad, de modo que quienes navegan con teclado sepan dónde están. Esta guía mantiene los *outlines* por defecto en elementos con focus para no restar accesibilidad.
- `:visited`: se aplica a enlaces `<a>` que el usuario ya ha visitado antes (historial del navegador). Por temas de privacidad, solo se puede cambiar propiedades limitadas (color normalmente) para indicar enlaces ya vistos.
- `:first-child`, `:last-child`, `:nth-child(n)`: permiten seleccionar un elemento según su posición entre sus hermanos. Por ejemplo, `.lista li:first-child { ... }` estilizaría solo el primer `<li>` de una lista con clase "lista". En esta página podríamos usar `section:nth-child(even)` para dar un fondo gris claro a cada sección par, por ejemplo, alternando colores de fondo para mejorar la separación visual.
- `:disabled`, `:checked`, etc.: se aplican en controles de formulario; por ejemplo `input:disabled` para campos deshabilitados, `input:checked` para checkboxes o radios marcados.

Las pseudo-clases hacen muy poderoso el CSS para interactuar con la acción del usuario. Por ejemplo, un simple *hover* en CSS puede sustituir la necesidad de un script para resaltar botones.

## Animaciones en CSS

Por otro lado, las **animaciones en CSS** permiten dar dinamismo a la página de forma ligera. Hay dos mecanismos principales:

- **Transiciones (*transitions*)**: Permiten que un cambio de estilo ocurra de forma **gradual y animada** en lugar de instantánea. Por ejemplo, si un enlace cambia de color en `:hover`, podemos agregar `transition: color 0.3s;` al enlace, de modo que al hacer *hover* el color se desplace suavemente en 0.3 segundos en vez de cambiar abruptamente. En la guía, los botones y enlaces tienen transiciones en propiedades como background, color o transform para lograr efectos de *hover* más agradables.
- **Animaciones con `@keyframes`**: Son más complejas; permiten definir una secuencia de estados (fotogramas clave) y crear animaciones más elaboradas que pueden ejecutarse independientemente del *hover* o no (por ejemplo, una animación continua al cargar la página). Se define un `@keyframes nombre` con pasos del 0% al 100% (o *from/to*) indicando cómo cambian ciertas propiedades, luego se aplica a un elemento con `animation: nombre 5s infinite;` (por ejemplo). Un uso podría ser hacer parpadear un texto, o mover un elemento. En esta página, por simplicidad, no se incluyó ninguna animación compleja con *keyframes*, pero sí pequeñas transiciones y un efecto de *hover* que escala ligeramente un elemento usando `transform: scale(1.05)` para hacerlo destacar al pasar el cursor.

**Ejemplo concreto implementado**: Los enlaces del menú superior tienen `transition: background-color 0.3s;` y en `:hover` cambiamos su fondo (*background-color*) y texto. El resultado es un efecto suave al pasar el ratón. También en el botón de "volver arriba" (si existiese en el *footer*) podríamos animarlo con una pequeña transición o rotación al hacer *hover*.

Con CSS3, incluso se pueden combinar **pseudo-clases con animaciones**: por ejemplo, usando `:focus` en un campo de formulario para hacer que un borde brille con una animación, etc. Las posibilidades son amplias y ayudan a mejorar la **interactividad sin escribir JavaScript**.

En suma, las pseudo-clases permiten reaccionar a estados del DOM (enlace visitado, elemento *hover*, etc.) y las animaciones/transiciones añaden vida al diseño. Ambos recursos han sido aplicados modestamente en esta guía para enriquecer la experiencia: ver el CSS para detalles, con comentarios explicativos junto a cada uso.

## Uso de frameworks CSS (Bootstrap y Tailwind)

En entornos profesionales es común apoyarse en frameworks o librerías CSS para acelerar el desarrollo y asegurar un diseño consistente. Dos de los más populares hoy día son **Bootstrap** y **Tailwind CSS**. Incluir conocimiento de ellos en esta guía es relevante porque en proyectos actuales de ASIR, DAW y DAM, a menudo se espera que los desarrolladores estén familiarizados con al menos uno.

### Bootstrap

Bootstrap (actualmente en su versión 5) es el framework CSS más conocido. Proporciona una extensa colección de componentes predefinidos (botones, barras de navegación, modales, carruseles, etc.) y un poderoso sistema de **cuadrícula (grid)** responsiva. Basta incluir el archivo CSS de Bootstrap (por ejemplo, vía CDN) y añadir a nuestro HTML las clases adecuadas para obtener diseños modernos sin empezar desde cero. Por ejemplo, para crear un layout de dos columnas que se apilan en móvil, usaríamos una estructura con clases de la grid de Bootstrap:

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Columna 1</div>
    <div class="col-md-6">Columna 2</div>
  </div>
</div>
```

En nuestra página de guía, hemos integrado Bootstrap en una sección de ejemplo para mostrar su uso: en la sección de **Ejercicios prácticos**, los desafíos están presentados como *cards* usando las clases de Bootstrap (por ejemplo, `card`, `card-body`, `btn btn-primary`, etc.), demostrando cómo en pocas líneas obtenemos un estilo agradable (mira el código fuente: verás el `<link>` a Bootstrap en el `<head>` y las clases en HTML).

### Tailwind CSS

Por otro lado, Tailwind CSS es un framework reciente que adopta un enfoque diferente, conocido como **utility-first**. En lugar de componentes preestilizados, Tailwind proporciona **clases de utilidad de bajo nivel** (por ejemplo, `bg-blue-500` para poner fondo azul, `text-center` para centrar texto, `p-4` para padding, `grid-cols-3` para una grid de 3 columnas, etc.) que se combinan para construir diseños personalizados. Es muy flexible: no impone un estilo predefinido sino que **acelera escribir CSS en línea en las clases HTML**. Por ejemplo, un botón se podría diseñar escribiendo: `<button class="px-4 py-2 bg-green-600 text-white rounded hover:bg-green-700">Enviar</button>` usando utilidades de Tailwind para padding horizontal y vertical, fondo verde, texto blanco, bordes redondeados y un hover más oscuro, todo sin escribir CSS en un archivo separado.

Tailwind suele integrarse en proyectos mediante un proceso de build (PostCSS) que elimina las clases no usadas, por lo que puede mantenerse muy eficiente. Para propósitos de aprendizaje, también ofrecen un archivo CDN. En esta guía no se incluyó directamente Tailwind por cuestiones de scope, pero se comenta porque en el mercado laboral actual Tailwind está ganando mucha popularidad por su enfoque altamente personalizable. A diferencia de Bootstrap que brinda componentes listos, Tailwind te da control completo sobre la apariencia sin estar limitado por diseños prehechos​. La contrapartida es que puede resultar abrumador al inicio (tantas clases utilitarias) y el HTML se llena de clases, pero muchos desarrolladores valoran su eficiencia y consistencia.

### ¿Cuál usar?

Depende del proyecto.  
- **Bootstrap** es genial para prototipos rápidos o cuando no se quiere pensar en diseño desde cero; trae un estilo uniforme "de fábrica".  
- **Tailwind** es ideal cuando se busca un diseño único pero se quiere evitar escribir todo el CSS manualmente; actúa como una biblioteca de piezas de Lego para el diseño.

No son excluyentes: **ambas son herramientas útiles**. Incluso existen otros frameworks (Bulma, Foundation, Materialize, etc.), pero Bootstrap sigue siendo un "clásico confiable" y Tailwind el "nuevo competidor en escena" enfocado en utilidades.

En la práctica profesional en **DAW/DAM**, es común que proyectos *front-end* usen frameworks: por ejemplo, en una aplicación web quizá el front se resuelva con **React + Tailwind**,  
o con un template **Bootstrap**. Para un **administrador de sistemas (ASIR)**, saber integrar un template Bootstrap en una intranet o personalizarlo puede ser útil también. Por ello, esta guía motiva a los estudiantes a al menos **familiarizarse** con estos frameworks, además de dominar lo fundamental de CSS puro.

> *En el código de esta página web, la sección de recursos adicionales incluye enlaces a las documentaciones oficiales de Bootstrap y Tailwind.*

<br>

# Integración de IA en el aprendizaje de HTML/CSS

![Logos de ChatGPT, Gemini y Copilot](https://images.gizbot.com/webp/img/2024/12/chatgpt-vs-gemini-vs-copilot3-1733462365.jpeg "ChatGPT, Gemini, Copilot logos")

En los últimos años, la Inteligencia Artificial (IA) se ha convertido en una aliada para el aprendizaje y la productividad en programación. Existen **herramientas de IA para código** que pueden ayudar a los desarrolladores a generar fragmentos, corregir errores e incluso aprender conceptos nuevos de forma interactiva. Incorporar la IA en el proceso de aprender HTML/CSS puede ser muy beneficioso:

- **Asistentes virtuales y chatbots**: Herramientas como **ChatGPT** (OpenAI) o asistentes integrados en editores de código pueden responder dudas de teoría (`¿Qué hace exactamente la propiedad flex-basis?`), explicar por qué un código no funciona o incluso generar código de ejemplo a partir de lenguaje natural. Por ejemplo, un estudiante podría pedir: _"Genérame el código HTML y CSS para una tarjeta con imagen a la izquierda y texto a la derecha"_ y el asistente produciría un boceto de código que luego el estudiante puede analizar y modificar. Esto **acelera la obtención de ejemplos prácticos**.
- **Generadores de código**: Hay herramientas en línea donde describes un diseño y la IA produce el HTML/CSS. Si bien no sustituyen entender cómo hacerlo manualmente, pueden servir para estudiar cómo la IA resuelve ciertos problemas de maquetación. Por ejemplo, ver el código que genera una IA para un formulario puede enseñarnos diferentes formas de estructurarlo.
- **Copilot en IDEs**: Extensiones como **GitHub Copilot** integran IA en editores como Visual Studio Code. Mientras escribes, sugieren automáticamente código. Podría autocompletar una estructura `<header>...</header>` completa con `nav` al detectar que quieres un layout típico, o sugerir reglas CSS. Esto en aprendizaje puede guiar al alumno sobre sintaxis y opciones disponibles, aunque hay que tener cuidado de no volverse dependiente y usarlo más como guía que como copy + paste.
- **Depuración de código**: Una IA puede ayudar a depurar HTML/CSS. Si el estudiante describe: _"Tengo un div que no se centra verticalmente pese a usar align-items en flex"_, la IA puede señalar posibles causas (como no tener `height` definido, o no estar usando `flex` en el elemento padre correcto). Esta capacidad de consulta instantánea a veces supera estar buscando en Google por mucho tiempo.
- **Explicación de conceptos**: Del lado teórico, se puede usar IA para que explique con otras palabras un concepto difícil. Por ejemplo: _"Explícame el modelo de caja como si tuviera 5 años"_ o _"¿Por qué los margin colapsan?"_

Es importante mencionar que, si bien estas herramientas son impresionantes, **no reemplazan la comprensión**. Pueden acelerar la escritura de código, pero el desarrollador debe revisar y entender lo que hacen. Al aprender, conviene usar la IA para experimentar y obtener *feedback*, pero siempre acompañando con lectura de documentación oficial (por ejemplo MDN) y práctica manual.

En esta guía no se incluye una sección de IA como contenido visible para el usuario final, pero en esta documentación se resalta su uso para que los estudiantes **aprovechen estas herramientas en su proceso formativo**. Por ejemplo, un reto propuesto podría ser: _"Utiliza ChatGPT para generar un ejemplo de formulario con 3 campos y valida uno de ellos con HTML5; luego interpreta el código generado y adáptalo."_ De esta forma se integra la IA como **parte activa del aprendizaje**.

En el ámbito profesional, la IA ya está ayudando a infinidad de desarrolladores a potenciar su trabajo sin afectar la calidad del código. **Aprender a colaborar con herramientas como ChatGPT o Copilot es una habilidad nueva** que sumada al dominio de HTML/CSS puede hacer a un desarrollador mucho más eficiente. En FP de informática, esto se traduce en estar actualizado con las metodologías modernas de desarrollo.

<br>

# Ejemplos profesionales de uso (ASIR, DAW, DAM)

Para contextualizar la teoría en situaciones reales, veamos cómo los conocimientos de HTML y CSS se aplican en proyectos típicos de cada especialidad:

- **En ASIR (Administración de Sistemas Informáticos en Red)**: Si bien el foco de ASIR es la gestión de sistemas y redes, un administrador de sistemas a menudo necesita desplegar o mantener interfaces web internas. **Ejemplo**: La creación de una página web para el monitoreo de servidores o una intranet sencilla. Un técnico superior en ASIR podría usar HTML/CSS para construir un panel de control que muestre el estado de servicios (con íconos de colores para activo/inactivo) o un formulario interno para reportar incidencias de hardware. También, al implementar soluciones como WordPress o wikis corporativas, el administrador con conocimientos de HTML/CSS puede: personalizar las plantillas, ajustar estilos o solucionar problemas de visualización. Por ejemplo: al integrar un script de monitoreo, quizás deba maquetar el output en una tabla HTML estilizada para fácil lectura; documentar la infraestructura en una página HTML con diagramas e imágenes; o asegurarse de usar etiquetas semánticas y diseño responsive para que se vea bien en distintos dispositivos dentro de la empresa.

- **En DAW (Desarrollo de Aplicaciones Web)**: Aquí es donde HTML y CSS son el pan de cada día. Un desarrollador web debe maquetar interfaces de usuario atractivas y funcionales. **Ejemplo**: El front-end de una aplicación de gestión (clientes, ventas, etc.) hecha en un proyecto final de DAW. El estudiante DAW aplicará etiquetas semánticas para la estructura (`header` con logo y menú, `main` con formularios de registro, tablas de datos, etc.), formularios bien construidos para CRUD de datos y CSS (posiblemente con Flexbox/Grid) para crear un dashboard responsive. Otro ejemplo típico es un **sitio web corporativo** o una **landing page** de marketing: requiere maquetar secciones de hero (encabezado con imagen de fondo y texto superpuesto), secciones de productos en grid, testimonios en carrusel (podría usar Bootstrap allí), y un footer con información de contacto. Todo esto demandará dominar tanto HTML (por SEO se cuidarán encabezados, alt en imágenes, microdatos quizás) como CSS (para diseño atractivo, animaciones sutiles, adaptabilidad móvil). En los proyectos DAW se valora mucho la correcta separación de contenido (HTML) y presentación (CSS), así como usar diseños semánticos, *wireframes*, archivos ordenados, etc., tal como se ejemplifica en esta guía.

- **En DAM (Desarrollo de Aplicaciones Multiplataforma)**: Aunque el foco aquí son aplicaciones de escritorio y móviles nativas, el mundo multiplataforma frecuentemente incorpora tecnologías web. **Ejemplo**: Desarrollo de una aplicación móvil híbrida o progresiva (PWA) usando Ionic/Cordova, React Native Web o tecnologías similares donde partes de la interfaz son HTML/CSS renderizado en webviews. Un DAM con conocimientos web puede crear la interfaz de una app móvil utilizando HTML5 para la estructura y CSS (junto con frameworks como Ionic que proveen componentes) para el estilo, logrando que la app luzca nativa. Otro ejemplo es el uso de **Electron** para aplicaciones de escritorio: Electron utiliza HTML/CSS/JS para crear UI de escritorio; muchos editores de código y herramientas (como Visual Studio Code) funcionan así. Así que un DAM podría terminar estilando ventanas de una app de escritorio con CSS. Incluso en desarrollo Android o iOS nativo, a veces se utiliza HTML/CSS para contenidos embebidos (como mostrar una ayuda formateada dentro de la app). Un ejemplo concreto podría ser un proyecto DAM donde se haga un cliente de chat multiplataforma y se diseñe una pequeña página HTML para el manual de uso integrado en la aplicación, o para mostrar mensajes con formato (usando WebView). Los fundamentos de maquetación y estilos aprendidos se aplican directamente allí.

En todos estos casos, vemos que **HTML/CSS son habilidades transversales**. Un administrador de sistemas con conocimiento web puede resolver necesidades sin depender totalmente de un desarrollador; un desarrollador web obviamente lo requiere para su día a día; y un desarrollador multiplataforma amplía su horizonte pudiendo crear interfaces web/híbridas

> *Actualmente, DAM se centra en crear aplicaciones que funcionan en diversas plataformas (móviles, escritorio, etc.) y DAW se especializa en aplicaciones web, lo cual ofrece ventajas específicas al abordar los retos técnicos de cada entorno. Sin embargo, existen opiniones en la comunidad que sugieren que, a futuro, la creciente convergencia de tecnologías y el avance de frameworks multiplataforma harán que esta distinción desaparezca, favoreciendo un enfoque de desarrollo más integral y unificado. Actualmente, la especialización aún es valiosa para responder a demandas concretas del mercado, pero es posible que en pocos años la línea que separa DAM de DAW sea menos relevante.*

<br>

# Ejercicios prácticos y retos

Para consolidar el aprendizaje, se proponen algunos ejercicios y desafíos prácticos que los estudiantes pueden realizar:

1. **Maquetar una página sencilla con HTML semántico**: Dado un contenido (por ejemplo, el texto de una noticia o artículo), estructúralo en HTML5 usando `<header>`, `<nav>`, `<article>`, `<aside>` y `<footer>`. Asegúrate de incluir al menos una lista, un enlace y una imagen con `alt`. _Reto adicional_: valida tu HTML con una herramienta como [W3C Validator](https://validator.w3.org/) para asegurarte de que no tiene errores.
2. **Formulario de contacto con validación nativa**: Crea un formulario de contacto que solicite nombre, email, teléfono y mensaje. Utiliza los tipos de input adecuados (`type="email"`, `type="tel"`, etc.) y marca los campos obligatorios con `required`. Añade también un `pattern` para validar el teléfono (por ej., que sean 9 dígitos). Prueba el formulario en un navegador y verifica los mensajes de error que aparecen al dejar campos vacíos o con formato inválido. _Reto adicional_: investiga cómo cambiar el mensaje de validación por defecto a español (hint: atributo `lang` o API Constraint Validation).
3. **Diseño responsive con media queries**: Comienza con un HTML sencillo (puede ser la estructura del ejercicio 1 o 2) y su correspondiente CSS para desktop. Luego agrega *media queries* para que en pantallas pequeñas la disposición cambie. Por ejemplo, si en desktop tienes un `<aside>` al lado del `<article>` (dos columnas), en móvil haz que el `<aside>` aparezca debajo del `<article>` (una sola columna). Prueba redimensionando la ventana del navegador o usando las herramientas de desarrollador en modo móvil para asegurarte de que el diseño se adapta correctamente.
4. **Ejercicio con Flexbox**: Crea un contenedor `<div>` con 5 cajas dentro (pueden ser `<div>` con una breve palabra o número). Usa CSS Flexbox para distribuir esas cajas con espacio igual entre ellas, centradas horizontalmente y alineadas abajo (si alguna tiene más texto que otra). Luego, modifica el CSS para que en pantallas estrechas (mobile) el flex contenedor haga `wrap` y las cajas se muestren en varias filas. Este ejercicio te hará manipular `justify-content`, `align-items`, `flex-wrap` y posiblemente `align-content`. _Reto adicional_: Intenta utilizar `order` (propiedad flex) para cambiar el orden visual de las cajas sin alterar el HTML.
5. **Grid avanzado**: Diseña una galería de imágenes usando CSS Grid. Por ejemplo, 6 imágenes que en desktop se muestren en 3 columnas x 2 filas, y en móvil en 2 columnas x 3 filas (o 1 columna x 6). Usa `grid-template-columns` con `fr` y aplica `gap` para separar las imágenes. Asegúrate de que las imágenes tengan `max-width: 100%` en CSS para que no se desborden de su celda. _Reto adicional_: Haz que alguna imagen ocupe dos columnas o dos filas (utilizando `grid-column: span 2` en el CSS correspondiente).
6. **Utilizando un framework**: Toma uno de tus ejercicios anteriores (por ejemplo, el formulario de contacto) y reházlo usando **Bootstrap**. Aprovecha su sistema de grid (clases `row`, `col`), sus componentes de formulario (clases como `form-control` en inputs, etc.) y estilos predeterminados. Compara cuánto CSS tuviste que escribir a mano versus cuánto vino ya estilado por Bootstrap. _Reto adicional_: Repite con **Tailwind CSS** (puedes usar su CDN para no tener que configurar build). Escribe las clases utilitarias directamente en el HTML para dar estilo similar. Reflexiona sobre las diferencias en el enfoque de ambos frameworks.
7. **Experimento con ChatGPT u otra IA**: Plantea un pequeño desafío, por ejemplo: _"crear un botón con efecto hover que parpadee mediante CSS"_, primero intenta resolverlo por tu cuenta. Luego pregunta a ChatGPT cómo lo haría. Compara su solución con la tuya, pruébala y ajusta según tu criterio. Este ejercicio ayuda a aprender a validar y entender las sugerencias de la IA en lugar de tomarlas como caja negra.

<br>

# Documentación del código y preparación para GitHub

Todo el código fuente de esta guía (HTML y CSS) está **comentado** para explicar la finalidad de cada sección y muchas de las líneas clave, de modo que al leer el código los estudiantes puedan entender el propósito de cada fragmento. Por ejemplo, al inicio del HTML verás comentarios indicando dónde comienza la cabecera, dónde está la navegación interna, cada sección principal tiene un comentario identificándola, y en el CSS hay bloques separados con comentarios como `/* Estilos de navegación */` o `/* Responsive */` para agrupar reglas relacionadas. Estos comentarios sirven como **documentación interna** dentro del código.

Adicionalmente, esta explicación extensa que estás leyendo actuaría como una **documentación externa (README)** que describe cada parte del HTML. De hecho, este proyecto subido a GitHub, incluye un archivo `README.md` en formato Markdown (lo estás leyendo ahora mismo) donde se detalla la estructura del proyecto, instrucciones de uso, y aclaraciones de cómo está organizado el código. Esto cumple con el punto de tener el proyecto listo para GitHub: los archivos están listos para ser versionados y compartidos, con una documentación que facilita a cualquier colaborador entender la finalidad de cada porción.

En cuanto a la **escalabilidad y adaptabilidad** del diseño por los estudiantes, se ha mantenido un estilo lo más modular y sencillo posible. Por ejemplo, la hoja CSS utiliza variables CSS (custom properties) para colores principales, de manera que cambiando un par de valores se puede alterar la paleta completa. También se evitó usar IDs en CSS para facilitar la extensión del código  
y evitar conflictos de especificidad. Todo está pensado para que un estudiante pueda tomar esta base y ampliarla fácilmente: añadir otra sección en HTML siguiendo la estructura comentada, agregar nuevas clases en el CSS siguiendo los patrones existentes, etc. El código comentado guía ese proceso.

Además, se cumple con tener un **diseño moderno y profesional**: se eligieron tipografías legibles (una fuente sans-serif limpia para párrafos y una serif elegante para títulos integradas desde Google Fonts en el `<head>`), junto a una paleta de colores coherente (azul para cabecera/acento y grises claros como fondo alterno). El CSS está organizado por secciones y bien comentado, facilitando la comprensión del _qué_ se hace y, sobre todo, _del porqué_ de cada decisión de diseño.

## Archivos del proyecto

Los archivos fuente principales del proyecto son:

- `index.html`: contiene la estructura semántica del documento, comentada y clara.
- `styles.css`: con buenas prácticas CSS, uso de Flexbox/Grid, media queries y comentarios.
- `README.md`: (este archivo) con explicación general y justificación de diseño y estructura.

Estos archivos están preparados con el objetivo de subirse a este repositorio en GitHub y permitir su distribución, reutilización o colaboración educativa.
