---
title: My AI Gemini - AI content generation - documentación y manual de usuario
description: Guía de configuración, trabajo diario y resolución de problemas para propietarios de tiendas que ya tienen instalado el módulo My AI Gemini en el back office de PrestaShop.
sidebar:
  label: My AI Gemini - AI content generation - documentación y manual de usuario
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product and Category Descriptions with Gemini en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Las capturas de pantalla de este manual proceden de un back office en inglés. Cada botón y cada nombre de campo se escribe exactamente como aparece en pantalla.

## 1. Requisitos

Antes de empezar, compruebe que su tienda y su servidor cumplen los puntos siguientes.

- **PrestaShop:** 1.6, 1.7, 8 y 9 (todas las versiones desde la 1.6 hasta la 9.99.99).
- **PHP:** 7.0 o superior. El instalador se niega a continuar con un PHP más antiguo y muestra el mensaje "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **Extensiones de PHP:** cURL (cada llamada a Gemini y cada descarga de página), JSON, DOM (lectura de páginas web para New product y para la búsqueda de fotos), mbstring y fileinfo (comprobación de las imágenes descargadas).
- **Conexión saliente:** su servidor debe poder abrir conexiones seguras (HTTPS) con el servicio Google Gemini. Si el servidor bloquea las conexiones salientes, no se puede generar nada.
- **Otros módulos:** el módulo no necesita ningún otro módulo.
- **Cuenta de Google:** necesita su propia clave de API de Google Gemini. Créela en https://aistudio.google.com/apikey y manténgala privada. Google factura o limita el uso según su propia cuenta de Google, no a través de este módulo.
- **Tiempo y tamaño:** cada campo es una petición a Gemini. Los textos largos y los modelos lentos pueden tardar más de un minuto por petición. Una ejecución masiva grande o un lote de cron grande tarda lo mismo que todas sus peticiones sumadas, así que empiece con listas pequeñas.

## 2. Instalación

1. Abra **Modules** y después **Module Manager**.
2. Haga clic en **Upload a module** y suelte el archivo ZIP, o súbalo con su método habitual.
3. Haga clic en **Install** junto al módulo cuando aparezca en la lista y confirme.
4. Tras la instalación aparece una nueva entrada llamada **AI Content Generator** en el menú izquierdo, dentro de la sección **Modules**. Haga clic en ella: se abre el **Dashboard** del módulo. Las mismas pantallas también son accesibles desde **Module Manager**, **Configure**.
5. Antes de que se pueda generar nada, abra **Settings**, después **Gemini**, pegue la clave en **Google Gemini API KEY** y guarde (detalles en el capítulo 3).

La instalación crea 16 plantillas de prompt ya preparadas (nombres de producto, descripciones, meta títulos, meta descripciones y etiquetas) para que pueda probar el módulo de inmediato. No vacía la caché de la tienda. Si la entrada de menú no aparece, abra de nuevo cualquier página del back office: el módulo vuelve a colocar la entrada de menú cada vez que se carga una página del back office.

**Desinstalación.** La desinstalación elimina la entrada de menú **AI Content Generator**, borra las plantillas de prompt y todo el History (por lo que también desaparecen las listas de restauración en los productos) y borra los ajustes del módulo, incluida la clave de API y los secretos de cron. No toca los textos, imágenes y productos que ya se hayan escrito o creado con el módulo. Algunos filtros de pantalla que usó en las páginas **Generate** pueden quedar guardados en los ajustes de la tienda; son inofensivos. Volver a instalar empieza desde un estado limpio: regresan las 16 plantillas por defecto, y los ajustes, plantillas y el History antiguos no se restauran.

## 3. Configuración y trabajo diario en el back office

### 3.1 Todo el proceso, paso a paso

1. **Conectar Gemini.** **Settings**, **Gemini**: pegue la clave de API, mantenga o cambie el modelo y guarde.
2. **Probar.** **Settings**, **Playground**: escriba una instrucción breve y pulse **Generate**. Si ve una respuesta, la conexión funciona. No se guarda nada en su catálogo.
3. **Definir el estilo de la tienda (opcional).** **Settings**, **Studio**: escriba la voz de marca, el público, el tono, las palabras que se deben conservar y las palabras prohibidas.
4. **Preparar instrucciones.** **Settings**, **Prompt templates**: conserve las plantillas por defecto o añada las suyas. Las plantillas activadas se ofrecen en el resto de lugares.
5. **Elegir cómo trabajar:**
   - Un producto cada vez: abra el producto, después **Modules**, **My AI Gemini**, y pulse **Fill** junto a un campo (3.16).
   - Muchos productos o categorías: **Generate**, **Products** o **Categories** (3.9 y 3.10).
   - Un producto que todavía no existe: **New product** (3.11).
   - Automáticamente, en lotes pequeños, sin que nadie haga clic: **Cron** (3.12).
6. **Comprobar el resultado.** **History** enumera cada petición con su prompt, respuesta, estado y consumo de tokens. **Dashboard** muestra las mismas cifras en gráficos.
7. **Deshacer.** En un producto: **Modules**, **My AI Gemini**, **History**: **Restore** recupera el texto anterior.

Los textos se guardan directamente en el producto o la categoría en cuanto Gemini responde, salvo donde este manual indique otra cosa (los botones **Try**, el **Playground**, **Generate data** y los botones **Generate with AI** junto a los campos, que solo colocan el texto en el formulario abierto hasta que usted guarda).

### 3.2 Abrir el módulo y moverse por él

Abra **AI Content Generator** en el menú izquierdo. La barra superior de cada pantalla tiene estos elementos: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** y, en el extremo derecho, **Updates**. Sitúe el ratón sobre un elemento para ver una breve explicación. Bajo **Settings** aparece una segunda fila con **General**, **Gemini**, **Studio**, **Prompt templates** y **Playground**. Bajo **Generate** la segunda fila muestra **Products** y **Categories**.

El botón redondo **Help** en el borde de cada página del módulo abre un panel lateral con una breve explicación de la página en la que se encuentra. Una línea de ese panel aún se refiere a una cuenta de OpenAI (véase el capítulo 5); use su clave de Google Gemini.

También puede llegar al módulo desde **Module Manager** con el botón **Configure**, desde el botón de acceso directo de la barra superior (3.18) y desde un enlace en la lista de productos (3.18).

### 3.3 Dashboard

El **Dashboard** es un informe. Nunca escribe textos de productos ni de categorías.

![My AI Gemini – Dashboard con rango de fechas, tarjetas y gráficos](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

Arriba elige el periodo. La línea **Active service** siempre muestra Gemini y el modelo guardado en la pantalla **Gemini**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Botones de periodo rápido. El elegido aparece resaltado. Solo cambian las cifras y los gráficos de esta página. |
| **From** y **To** | Fechas de los últimos 30 días | Su propio periodo. Pulse **Apply** para volver a dibujar. Si From es posterior a To, el módulo los intercambia. |
| **Apply** | – | Vuelve a dibujar las tarjetas y los gráficos con las fechas escritas. |
| **Requests** | Contado desde History | Cada llamada guardada en el periodo, correcta o fallida. |
| **Success** | Contado desde History | Llamadas que no terminaron con un error. |
| **Errors** | Contado desde History | Llamadas que terminaron con un error. |
| **Tokens sent** | Contado desde History | Tamaño total de sus instrucciones enviadas a Gemini. |
| **Tokens received** | Contado desde History | Tamaño total de las respuestas. |
| Gráfico **Requests and errors** | – | Gráfico de líneas, un punto por día. En periodos de más de 120 días, un punto cubre una semana. |
| Gráfico **Tokens sent and received** | – | El mismo periodo, dos líneas. |
| Gráfico **Requests by model** | – | Gráfico de barras: cuántas peticiones atendió cada modelo. |

Si los gráficos están vacíos, no se generó nada en ese periodo. El Dashboard también existe como un pequeño bloque en el dashboard principal de PrestaShop, pero ese bloque no recibe las cifras de History, así que sus tarjetas y gráficos permanecen vacíos. Use el **Dashboard** del módulo.

### 3.4 Settings – General

Abra **Settings** y después **General**. Estos interruptores deciden lo que ven los empleados en el back office. Guardar no reescribe ningún texto de producto.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Live mode** | Disabled | Marca el módulo como funcionando en la tienda real. Actívelo en la tienda de producción. Déjelo desactivado en una copia de prueba para señalar que la configuración no es la de producción. Las mismas herramientas funcionan en ambos estados. |
| **Debug mode** | Disabled | Escribe mensajes técnicos adicionales en el registro de PrestaShop (**Advanced Parameters**, **Logs**) cuando falla una llamada a Gemini. Actívelo solo mientras investiga un error y luego desactívelo. Los clientes nunca lo ven. |
| **API timeout (seconds)** | 120 | Cuántos segundos puede durar una llamada a Gemini antes de que el módulo se rinda. 120 sirve para descripciones normales. Súbalo hasta 600 para textos SEO largos o modelos lentos. Los valores inferiores a 10 pasan a 10, los superiores a 600 pasan a 600, y un valor vacío o no numérico pasa a 120. Un timeout corto falla rápido y registra un error. |
| **Product Edit History** | Enabled | Muestra la pestaña **History** con botones **Restore** en la página de producto (**Modules**, **My AI Gemini**). Desactivado oculta esa lista. Las filas anteriores permanecen en el **History** de toda la tienda en cualquier caso. |
| **Admin Top Bar CTA** | Enabled | Coloca un pequeño botón de varita mágica en la barra superior de cada página del back office que abre un cuadro de prompt. Desactivado elimina solo ese botón. El menú del módulo se mantiene. |
| **Product edit page Form** | Enabled | Muestra el panel del generador en **Modules**, **My AI Gemini** en la página de producto. Actívelo para los editores del catálogo. Desactívelo si solo se van a usar la generación masiva y el cron. |
| **AI Image Finder** | Enabled | Muestra la pestaña **Photos** en la página de producto. Desactivado la oculta. Una imagen solo se importa después de que alguien la marque y confirme. |
| **AI Image Search Prompt** | Una instrucción integrada en inglés que pide 5 direcciones de páginas | La instrucción que se envía cuando alguien busca imágenes de producto. Las palabras {product_name} y {product_description} se sustituyen por el producto actual. Mantenga la petición de una lista de direcciones de páginas. Un prompt más preciso da páginas más relevantes. |
| **Save** | – | Guarda todos los campos anteriores. Mensaje: **Settings Updated**. |

Los dos campos de imagen aparecen tanto aquí como en la pantalla **Images** (3.14). Son los mismos dos ajustes.

### 3.5 Settings – Gemini

Abra **Settings** y después **Gemini**. Aquí conecta la cuenta de Google y define cuán variada es la redacción. Cada generación (botones de producto, ejecuciones masivas, cron, New product, búsqueda de fotos, Playground) usa estos valores.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Google Gemini API KEY** | Vacío | El secreto que permite a su tienda llamar a su cuenta de Gemini. Pegue la clave de https://aistudio.google.com/apikey. Se eliminan los espacios al principio y al final. Si deja el cuadro sin tocar, se conserva la clave guardada. Una clave vacía o incorrecta hace fallar las llamadas y el error se escribe en History. |
| **Model** | gemini-2.0-flash | El modelo de Gemini que escribe el texto. Opciones integradas: gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. La siguiente generación usa el modelo que guarde. Un modelo que su clave no puede usar devuelve un error en lugar de texto. |
| **Add a Gemini model** (cuadro con **Add model**) | – | Añade un nombre de modelo que no está en la lista integrada. Escriba el nombre exacto de su cuenta de Gemini y pulse **Add model**. El nombre aparece en **Model** y se selecciona al instante. Los nombres añadidos tienen un enlace **Remove** al lado. Los nombres integrados no se pueden eliminar. |
| **Max Tokens** | 3200 | Límite superior de la longitud de una respuesta, contado en tokens, no en palabras. Unos 256 bastan para una meta descripción, 1000 o más para una descripción HTML completa. Un límite bajo corta la respuesta. Un límite alto permite un texto más largo. Algunos modelos Gemini 2.5 gastan parte de este límite en «pensar», así que manténgalo holgado para ellos. |
| **Temperature** | 0.7 | Con qué libertad elige palabras el modelo. Manténgase entre 0 y 1. Aproximadamente 0.2 sirve para especificaciones y texto meta, aproximadamente 0.7 para descripciones. Un valor bajo repite una estructura similar. Un valor alto da una redacción más variada y más riesgo de salirse del encargo. |
| **Top P** | 1 | Una segunda forma de acotar la elección de la siguiente palabra. En esta versión el valor se guarda pero no se envía a Gemini, así que cambiarlo no modifica las respuestas. |
| **Frequency Penalty Value** | 0 | Pensado para desalentar frases repetidas. Se guarda pero en esta versión no se envía a Gemini, por lo que no tiene efecto en las respuestas. |
| **Presence Penalty Value** | 0 | Pensado para empujar el texto hacia puntos nuevos. Se guarda pero en esta versión no se envía a Gemini, por lo que no tiene efecto en las respuestas. |
| **Save** | – | Guarda el formulario. Mensaje: **OpenAi Settings Updated** (el módulo aún usa aquí la redacción antigua). |

Mensajes que puede ver en esta pantalla:

| Mensaje | Causa | Qué hacer |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | El cuadro de la clave tiene menos de 10 caracteres y aún no hay ninguna clave guardada. | Pegue la clave completa y pulse **Save** otra vez. |
| **OpenAi Model field is invalid!** | El nombre del modelo tiene menos de 3 caracteres. | Elija un nombre de la lista **Model**. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | La clave guardada tenía espacios alrededor. | Nada: el módulo lo corrigió. |
| **Model added.** | El nuevo nombre se guardó y se seleccionó. | Pulse **Save** si también cambió otros campos. |
| **That model is already built in.** | El nombre que escribió ya está en la lista. | El módulo lo selecciona por usted. |
| **Model removed.** | Se eliminó un nombre añadido. | Si era el modelo activo, elija de nuevo un modelo Gemini (véase el capítulo 5). |
| **Built-in models cannot be removed.** | Intentó eliminar un nombre integrado. | Nada que hacer. |
| **Enter a model id such as gpt-4.1.** | El cuadro del nombre de modelo estaba vacío o tenía caracteres no permitidos. | Escriba un nombre de Gemini, por ejemplo gemini-2.5-flash. El ejemplo de este mensaje es un resto del pasado. |

### 3.6 Settings – Studio

Abra **Settings** y después **Studio**. Studio añade reglas de la casa sobre cada prompt: botones de producto, ejecuciones masivas, cron y el Playground. Los campos vacíos se omiten. El módulo además indica siempre a Gemini que escriba en el idioma del elemento que se genera.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Brand voice** | Vacío | Le dice al modelo quién habla para que el texto suene como su tienda. Escriba un breve encargo, por ejemplo: taller especializado, frases cortas, sin exageraciones. Cambiarlo no reescribe los textos ya guardados. |
| **Audience** | Vacío | Nombra al lector, por ejemplo instaladores profesionales o compradores primerizos. Las nuevas respuestas usan un vocabulario dirigido a ese lector. |
| **Tone** | Vacío | Una o dos palabras para el ambiente: formal, cercano, técnico. No cambia el modelo ni la temperatura. |
| **Glossary** | Vacío | Nombres de marca, materiales y grafías que el modelo debe copiar exactamente. Un término por línea. Los términos no incluidos aún pueden reformularse. |
| **Forbidden words** | Vacío | Palabras y frases que no deben aparecer en una respuesta guardada. Una por línea. La lista también se envía al modelo como palabras que evitar. Rechazar una respuesta que coincida solo ocurre cuando **Quality gate** está activado. |
| **Monthly generation budget** | 0 | Número máximo de generaciones correctas en el mes natural en curso, contadas desde History. 0 significa sin límite. Al alcanzar el tope, las nuevas peticiones se detienen con un mensaje de presupuesto hasta el mes siguiente. Las llamadas fallidas no se cuentan. |
| **Quality gate** | Enabled | Comprueba cada respuesta con **Forbidden words** antes de guardar nada. Activado rechaza una respuesta coincidente: el producto queda sin cambios y History registra un error. Desactivado guarda la respuesta aunque contenga una palabra de la lista. Con una lista Forbidden words vacía la barrera no tiene nada que comprobar. |
| **Save studio** | – | Guarda el formulario. Mensaje: **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Abra **Settings** y después **Prompt templates**. Una plantilla es una instrucción guardada. Los editores la eligen por su título en lugar de escribir el mismo encargo una y otra vez.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

La lista muestra estas columnas: **ID**, **Title**, **Prompt**, **Status** (haga clic en la marca o la cruz para activar o desactivar la plantilla), **Timestamp**. Cada fila tiene **Edit** y **Delete**. Marque varias filas y use la acción masiva **Delete** (se le pregunta "Are you sure you want to delete the selected prompts?"). El botón verde con el signo más sobre la lista crea una plantilla nueva.

El formulario de plantilla:

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Status** | Interruptor Enabled / Disabled | Muestra u oculta la plantilla en las listas usadas en la página de producto, en el cuadro de prompt de la barra superior, en la generación masiva y en el cron. Active las plantillas que su personal deba usar. Desactive un borrador en lugar de eliminarlo. |
| **Prompt title** | Vacío (obligatorio) | El nombre que ven los editores en la lista. No se envía a Gemini. Use una etiqueta corta, por ejemplo HTML description with features. |
| **Prompt content** | Vacío (obligatorio) | La instrucción enviada a Gemini. Escríbala como si diera instrucciones a un redactor: longitud, HTML, idioma. Puede usar marcadores de posición (3.19). Las comillas dobles se cambian por comillas simples al guardar. |
| **Save Prompt** | – | Guarda la plantilla. |
| **Go Back to Module Settings** | – | Vuelve a la lista sin guardar. |

Mensajes: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** seguido de un número, **Failed to edit prompt template! Please fill the form with the right informations!**.

Las 16 plantillas por defecto son: Product name 1–2, Product description 1–7 (la séptima incorpora los enlaces de las imágenes del producto), Product meta title 1–3, Product meta description 1–3 y Product tags. Dos de las plantillas de meta descripción mencionan un smartwatch; edítelas antes de usarlas si vende otra cosa. Los textos de las plantillas se guardan en el idioma que usaba la tienda en la instalación.

### 3.8 Settings – Playground

Abra **Settings** y después **Playground**. Es un bloc de notas: envía una instrucción libre al modelo activo y muestra la respuesta en la página.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Escriba la instrucción en el cuadro grande ("Ask the model anything about your catalog").
2. Pulse **Generate**.
3. Lea la respuesta bajo el botón, con el número de tokens utilizados.

Puede mencionar el nombre de la tienda, la dirección de la tienda, el nombre de un producto, una referencia o características si quiere que la respuesta se base en datos del catálogo. Se aplican las reglas de Studio. No se cambia ningún producto, categoría ni campo meta, y la llamada queda registrada en History. Si el cuadro está vacío verá "Write a prompt first." Use el Playground para probar la clave y pulir un prompt antes de convertirlo en plantilla.

### 3.9 Generate – Products

Abra **Generate** y después **Products**. La generación masiva tiene dos pasos. Durante el paso 1 no se envía nada a Gemini.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Paso 1 – filtrar los productos.** Todos los filtros son opcionales y no se guardan como ajustes de la tienda.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Product Categories** | Nada marcado | Conserva los productos que están en cualquiera de las categorías marcadas, o la tienen como categoría principal. Un árbol vacío no filtra por categoría. |
| **Brand** | **Select brand** | Conserva los productos de un fabricante. La primera opción significa todas las marcas. |
| **Product status** | **Active** | **Active** conserva los productos a la venta, **Disabled** los desactivados, **Both** todos. |
| **Product stock** | **All products** | **Only in stock products** descarta los productos sin cantidad disponible. |
| **Update only** | **Update all** | Usa History. La primera opción conserva los productos que este módulo nunca ha escrito. La segunda conserva los que ya ha escrito. Las etiquetas aún dicen "OpenAi content" (véase el capítulo 5). |
| **Product IDs** | Vacío | Escriba ids separados por comas, por ejemplo 12,45,103. Solo pueden aparecer esos productos. |
| **Product Reference** | Vacío | Escriba una o varias referencias separadas por comas. |
| **Product Add Date From** / **Product Add Date To** | Vacío | Conservan los productos creados después de la primera fecha y antes de la segunda. |
| **Minimum product ID** / **Maximum product ID** | Vacío | Conservan los productos dentro de ese rango de ids. |
| **Product Limit** | Vacío | Número máximo de productos cargados en la lista. Use un número pequeño como 20 la primera vez. |
| **Go to next step** | – | Construye la lista. |
| **Module settings** | – | Botón junto a **Go to next step**. Abre la página de ajustes de otro módulo (véase el capítulo 5); use en su lugar **Settings** en la barra del módulo. |

**Paso 2 – escribir.** La página muestra ahora el panel **Mass product generation** con una tabla de los productos encontrados (columnas **ID**, **Reference**, **Result**).

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Template** | **Choose a template** | Copia el texto de una plantilla activada en el cuadro de abajo. El título en sí no se envía. |
| Cuadro de prompt grande | Vacío | La instrucción enviada para cada producto. Los marcadores se rellenan para cada producto (3.19). Si lo deja vacío, se usa una instrucción estándar para cada campo. |
| **What to generate** | **Descriptions** | **Descriptions** escribe la descripción larga y la corta. **Meta title and meta description** escribe ambos campos meta. **Descriptions and meta together** escribe los cuatro. Cada campo es una petición independiente. Los demás campos (incluidos el nombre del producto y las etiquetas) nunca se cambian aquí. |
| **Existing text** | **Replace** | **Replace** sobrescribe el campo. **Skip if filled** deja en paz un campo relleno y no envía nada a Gemini para él. **Add above** y **Add below** conservan el texto antiguo y añaden el nuevo antes o después. |
| **Languages** | Está marcado el idioma que usa en el back office | Marque cada idioma que desee. Cada idioma marcado se genera por separado. Debe marcarse al menos uno ("Select at least one language."). |
| **Run on the list below** | – | Inicia la ejecución. |

Durante la ejecución, la línea sobre el botón muestra el progreso, por ejemplo "3 / 40 – description". Cada fila de la tabla muestra un resultado como "description: success Content successfully generated and updated to product." o "description: skipped Product skipped." o un texto de error. La ejecución toma los productos uno a uno y guarda cada respuesta de inmediato, de modo que un fallo en un producto no deshace los ya guardados. No cierre la página hasta que vea "Finished … products."

### 3.10 Generate – Categories

Abra **Generate** y después **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Paso 1 – filtrar las categorías.**

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Categories** | Nada marcado | Marque las categorías que incluir. Un árbol vacío incluye todas las categorías que coincidan con el estado. |
| **Category status** | **Active** | **Active**, **Disabled** o **Both**. |
| **Go to next step** | – | Construye la lista. Todavía no se genera nada. |
| **Module settings** | – | Abre la página de ajustes de otro módulo (véase el capítulo 5). |

**Paso 2 – escribir.** El panel **Mass category generation** enumera las categorías (columnas **ID**, **Result**).

| Campo | Al inicio | Qué hace |
|---|---|---|
| Cuadro de prompt grande | Vacío | La instrucción enviada para cada categoría. Puede usar {category_name}, {category_description}, {category_parent_name} y los marcadores de la tienda (3.19). Escriba siempre un prompt aquí: para las categorías no hay instrucción estándar. |
| Lista de campos | **Description** | **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Solo se guarda ese campo. |
| Lista de texto existente | **Replace** | **Replace** sobrescribe. **Skip if filled** deja en paz un campo relleno. |
| Lista de idiomas | Su idioma del back office | Un idioma por ejecución. Ejecute de nuevo para otro idioma. |
| **Run on the categories below** | – | Inicia la ejecución. Cada categoría se guarda en cuanto llega su respuesta. |

Bajo la tabla hay un segundo formulario titulado **Generate category content** con un botón **Generate content**. No genera nada: solo le devuelve al filtro de categorías. Use siempre **Run on the categories below**.

### 3.11 New product

Abra **New product**. Esta pantalla convierte un encargo breve en el borrador de un producto que todavía no existe.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **What is the product?** | Vacío | El encargo. Escriba unas frases con materiales, público y nombres que deban mantenerse. Un encargo más rico da un borrador más ajustado. Un encargo vacío se rechaza. |
| **Optional source URL** | Vacío | Una dirección completa de una página pública sobre el producto. El texto de la página (título, descripción, precio) se añade a su encargo. Un cuadro vacío o una página que la tienda no pueda leer se ignora. |
| **Language** | Idioma por defecto de la tienda | El idioma en el que se guardan nombre, descripciones, meta y etiquetas. Los demás idiomas no se rellenan. Elija el idioma por defecto de la tienda, porque PrestaShop espera un nombre en él. |
| **Default category ID** | 2 | El número de la categoría en Catalog, Categories. 2 suele ser Home. El nuevo producto se coloca en esa categoría y esta se convierte en la categoría por defecto. |
| **Generate data** | – | Pide un borrador a Gemini y lo imprime debajo como texto estructurado (nombre, descripciones, meta, etiquetas, referencia, precio, características). No se guarda ningún producto. |
| **Create product** | – | Guarda el borrador como un nuevo producto activo. Establece nombre, descripciones, meta, etiquetas, características, referencia y precio a partir del borrador, visibilidad en todas partes y una cantidad en stock de 100. No se adjuntan imágenes; añádalas después (3.16). Línea de resultado: "Product #" seguido del número del nuevo producto. |

Si no hay una clave de API guardada, verá "Add an API key in the module settings first." Pulsar **Create product** antes de **Generate data** muestra "Generate the product first." Tras la creación, compruebe el precio, el impuesto y las imágenes: el módulo asigna el primer grupo de reglas de impuestos y el precio sugerido por Gemini.

### 3.12 Cron

Abra **Cron**. El cron es para el servidor, no para una persona: su servidor llama a una dirección web secreta según un calendario y la tienda rellena cada vez un pequeño lote de productos o categorías. No ocurre nada hasta que el servidor solicita la dirección.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

La pantalla tiene dos formularios: uno para productos y otro para categorías. Cada uno tiene su propio botón **Save**, y no se muestra ningún mensaje de confirmación tras guardar.

**Formulario de cron de productos**

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Enable Cron Feature** | **No** | Interruptor de todo el cron (productos y categorías). Mientras sea **No**, cada llamada se rechaza con "Cron Job feature is disabled. You can enable it from the module settings." Actívelo solo después de guardar los demás campos. |
| **Cron Job Secret Token** | Un valor aleatorio largo | La contraseña que debe estar en la dirección. Sin ella la tienda rechaza la llamada. Sustituirla invalida la dirección anterior. El botón **Generate Token** junto al campo puede no hacer nada en esta versión; si no lo hace, escriba usted mismo un valor largo. |
| **Update Field** | **description** | Qué único campo de producto reescribe el cron: **name**, **description**, **description_short**, **meta_title**, **meta_description** o **tags**. Para rellenar varios campos, cree varios comandos de cron. |
| **Selected Products** | **pendingGemini** | Qué productos siguen esperando. **pendingGemini**: productos que este módulo nunca ha escrito con éxito (cualquier campo). **pendingField**: productos que aún no se han generado para el campo elegido, de modo que un catálogo puede procesarse con varios cron jobs. **emptyField**: solo productos cuyo campo elegido está vacío en el idioma elegido. |
| **Product Categories** | Nada marcado | Limita la ejecución a las categorías marcadas (véase el capítulo 5 para una advertencia). |
| **Product ID list** | Vacío | Ids de producto explícitos separados por comas. Los caracteres que no sean dígitos se eliminan al guardar. |
| **Language** | Idioma por defecto de la tienda | La versión de idioma que se escribe. |
| **Product to update** | 5 products | Tamaño del lote por llamada: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000. Empiece con 5 o 10 para que un modelo lento no alcance el límite de tiempo del servidor. Los productos se toman por orden de ID. |
| **Prompt Template** | Primera plantilla de la lista | La instrucción guardada que se usa para cada producto. Los marcadores se rellenan por producto (3.19). |
| **Enable Debug** | **No** | **Yes** hace que la dirección imprima el plan (consulta, productos seleccionados, prompts finales) y no guarde nada. Desactívelo antes de que el planificador del servidor use la dirección. |
| **CRON JOB interval** | **Every Hour** | Una sugerencia mostrada para su propia planificación. El módulo no ejecuta ningún planificador. Defina el calendario real en su servidor. |
| **Product Cron Job command** | – | Muestra el prefijo de la dirección. En esta versión la línea de comando en pantalla está incompleta (véase abajo). |
| **Save** | – | Guarda los ajustes del cron de productos. |

El **formulario de cron de categorías** tiene su propio **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (los mismos tres modos), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** y **Save**. Siempre omite la categoría raíz de la tienda.

**La dirección que da al servidor.** Sobre los formularios la pantalla imprime una dirección de productos y una de categorías, cada una terminando tras el secreto. También hay que indicar al servidor qué trabajo ejecutar. Añada esto al final de la dirección de la pantalla:

| Trabajo | Dirección completa | Notas |
|---|---|---|
| Productos | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Use el secreto del formulario de productos. |
| Categorías | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | La línea de categorías en pantalla termina con `&entity=category`; sustituya ese final por `&action=generateCategoryContent`. |

Extras opcionales que puede añadir para anular el formulario guardado en un comando: para productos `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (ids separados por comas), `productIds`; para categorías `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. Los valores no añadidos proceden del formulario guardado.

**Planificador.** En el panel de su alojamiento cree una tarea programada que abra la dirección completa, por ejemplo con `curl -s "ADDRESS"` cada hora. Pruebe primero en un navegador con **Enable Debug** en **Yes**: verá qué productos se procesarían y los prompts finales. Después póngalo en **No** y abra la dirección una vez más. Cada llamada real actualiza un lote y se detiene.

Respuestas que puede ver al abrir la dirección:

| Respuesta | Causa | Qué hacer |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | El lote funcionó. | Nada. |
| **N pending products.** | Debug está activado, no se guardó nada. | Desactive debug cuando esté satisfecho. |
| **No products to update.** / **No categories to update.** | Ya nada coincide con **Selected Products** ni con los demás filtros. | El trabajo ha terminado, o cambie la regla. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** está en **No**. | Póngalo en **Yes** y pulse **Save**. |
| **The token does not exist or it's wrong!** | Falta el secreto o no coincide. | Copie de nuevo la dirección desde la pantalla. |
| **Invalid action!** | La dirección no tiene la parte `action`, o es incorrecta. | Añada la parte `action` de la tabla anterior. |
| **updatedField parameter is wrong!** | El campo no está permitido para ese trabajo. | Elija un campo del formulario. |
| **All must include all mandatory parameters!** | Un valor guardado (por ejemplo la plantilla) está vacío. | Elija un **Prompt Template** y guarde. |
| **productTarget parameter is wrong! Allowed values: …** | El nombre del modo en la dirección es incorrecto. | Use uno de los tres modos. |
| **Error!** seguido de un mensaje | Gemini rechazó o falló. | Lea el mensaje y después revise History. |
| **Error! The model returned an empty response.** | Gemini no devolvió nada, por ejemplo porque el límite de Max Tokens era demasiado bajo. | Suba **Max Tokens** en la pantalla **Gemini**. |
| **Monthly generation budget reached.** | Se agotó el presupuesto de Studio. | Suba el presupuesto o espere al mes siguiente. |
| **Reply rejected by the studio quality gate.** | La respuesta contenía una palabra prohibida. | Edite la lista o la plantilla. |
| **Error! Could not save product …** | PrestaShop rechazó el nuevo texto (por ejemplo, demasiado largo). | Revise el campo y el prompt. |

Una llamada de cron se detiene en el primer error e informa de cuántos elementos ya se habían actualizado antes.

### 3.13 History

Abra **History**. Es el registro de lo que se pidió y de lo que volvió. Abrir o filtrar la página no borra nada ni cambia productos.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Atajos de fechas. |
| **From** / **To** | El mes actual | Su propio periodo. |
| **Model** | **Any** | Solo peticiones hechas con ese modelo. |
| **Type** | **Any** | Solo un tipo de trabajo, por ejemplo una descripción de producto o un meta título de categoría. |
| **Status** | **Any** | **Success** o **Error**. |
| **Language** | **Any** | Solo peticiones para ese idioma. |
| **Employee** | **Any** | Solo peticiones iniciadas por ese usuario del back office. |
| **Product / category ID** | Vacío | Un número de producto o de categoría. |
| **Prompt or reply contains** | Vacío | Una palabra que debe estar en el prompt, la respuesta o el texto del error. |
| **Filter** | – | Aplica los filtros. |

Tarjetas: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. Un guion en una columna de tokens significa que Gemini no devolvió un recuento para esa llamada. Debajo, cinco tablas agrupan las peticiones filtradas: **By day**, **By model**, **By type**, **By language**, **By employee**, con una pequeña barra que muestra la proporción de tokens. Un pequeño número en cursiva junto a un recuento de llamadas es el número de errores.

La lista inferior tiene las columnas **ID**, **Status** (**Success** en verde o **Error** en rojo), **Prompt** (primeros 180 caracteres), **Reply / Error**, **Provider** (servicio, modelo y duración), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp** y un botón **View** que abre el prompt completo y la respuesta con **Back to the list**. La lista muestra 50 filas por página.

El botón de la barra de herramientas **Clear list** borra todas las filas de History de una vez, sin preguntar. Hágalo solo a propósito: los botones de restauración en los productos, el contador del presupuesto mensual y los modos de cron **pendingGemini** y **pendingField** dependen de History, así que tras vaciarla el cron trata cada producto como aún no escrito.

### 3.14 Images

Abra **Images**. Esta pantalla solo activa o desactiva la búsqueda de fotos de producto y guarda su instrucción. No descarga ninguna imagen.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **AI Image Finder** | Enabled | Muestra la pestaña **Photos** en la página de producto. Desactivado la oculta. |
| **AI Image Search Prompt** | Instrucción integrada en inglés | La instrucción que pide a Gemini direcciones de páginas donde probablemente haya fotos de este producto. {product_name} y {product_description} se sustituyen por el producto actual. Mantenga la petición de una lista sencilla de direcciones. |
| **Save** | – | Guarda ambos campos. Mensaje: **Settings saved.** |

La búsqueda encuentra páginas web que ya muestran su producto; no crea imágenes. Compruebe que tiene derecho a usar cualquier imagen que importe.

### 3.15 Updates

Abra **Updates** (extremo derecho de la barra del módulo). La página consulta MyPresta.eu para ver si hay un archivo de módulo más reciente. No cambia su catálogo y no instala nada.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Pregunta una vez, de inmediato. Verá **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Interruptor Enabled o Disabled | Enabled: aproximadamente cada tres días el back office comprueba y muestra un aviso con un enlace cuando existe una versión más reciente. Este ajuste se comparte con otros módulos de MyPresta en la misma tienda. |
| **Product Page** | – | Un enlace a la página del módulo en MyPresta.eu, donde puede leer qué ha cambiado y descargar el archivo. |
| **Save** | – | Guarda el ajuste de notificaciones. Mensaje: **Update settings saved.** |

### 3.16 Trabajar en la página de edición de producto

Abra **Catalog**, **Products**, edite un producto y abra **Modules**, después **My AI Gemini**. El producto debe haberse guardado ya una vez. El panel aparece cuando **Product edit page Form** o **Product Edit History** (3.4) están activados.

![Página de edición de producto – panel My AI Gemini](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

El panel tiene hasta cuatro pestañas: **Generate**, **Simulate**, **Photos** y **History**.

**Pestaña Generate**

| Campo | Al inicio | Qué hace |
|---|---|---|
| Botones **Language** | El primer idioma | Elija qué versión de idioma se escribe. **Every language** escribe todos los idiomas activos, uno tras otro. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** o **Skip if filled**. Skip no envía nada a Gemini para un campo relleno. |
| Tarjetas de campo | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Pulse **Fill** en la tarjeta para escribir ese campo y guardarlo en el producto al instante. |
| **SEO pack** – **Fill all** | – | Escribe el nombre, ambas descripciones y ambos campos meta en una sola petición y los guarda. |
| **Use your own instruction or a saved prompt** | Cerrado | Ábralo para filtrar las plantillas guardadas por título o texto, elegir un mosaico (**Standard brief** o una plantilla activada) y editar el cuadro **Instruction**. Si el cuadro está vacío, **Fill** usa una instrucción estándar para el campo. |

La respuesta se imprime bajo el panel. El texto se guarda en el producto de inmediato, pero los campos del formulario de producto abierto no se actualizan solos: recargue la página de producto antes de editar y de pulsar guardar en el formulario; de lo contrario, los valores antiguos del formulario pueden sobrescribir el texto nuevo.

**Pestaña Simulate.** La misma elección de idioma y las mismas tarjetas de campo, pero los botones dicen **Try**. La respuesta se queda en esta página y el producto no se cambia. Úsela para comprobar primero la redacción.

![Página de edición de producto – pestaña Photos](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Pestaña Photos.** Pulse **Find pages**. El módulo pide a Gemini hasta 5 páginas que probablemente muestren este producto, lee hasta 24 imágenes de ellas y las muestra como pequeñas miniaturas. Marque las que desee y pulse **Add selected to this product**. La primera imagen marcada se convierte en la portada si añade varias. No se guarda nada antes de pulsar el botón. La línea bajo los botones indica el progreso: "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." Tras añadir, recargue la página de producto para verlas. Si el interruptor está desactivado, verá una nota que le indica activar **AI Image Finder** en **Settings**, **General**.

**Pestaña History.** Una tabla con **When**, **Type**, **Status** y un botón **Restore** para cada escritura correcta que guardó un valor anterior. Pulse **Restore**, confirme "Restore the previous value?" y el texto anterior vuelve. Las filas fallidas no tienen botón. Un SEO pack restaurado devuelve el nombre, ambas descripciones y ambos campos meta. Sin filas verá "No generations for this product yet."

**Botones Generate with AI junto a los campos.** En la página de producto el módulo también añade un botón **Generate with AI** junto a los campos de descripción, descripción corta, meta título y meta descripción. Si la tienda tiene más de un idioma, pregunta "Generate this field for the current language, or for every active language?" con **Current language**, **All languages** y **Cancel**. El texto va solo al formulario abierto: "Text is in the field. Save the product to keep it." Los demás campos no se cambian. Para un producto que nunca se guardó verá "Save the product once before generating."

### 3.17 Trabajar en la página de edición de categoría

Edite una categoría en **Catalog**, **Categories**. Junto a los campos de descripción, descripción adicional, meta título y meta descripción el módulo añade el botón **Generate with AI**. Funciona exactamente igual que en los productos: elija el idioma actual o todos los idiomas, el texto se coloca en el formulario y usted guarda la categoría para conservarlo ("Text is in the field. Save the category to keep it."). Una categoría que nunca se guardó muestra "Save the category once before generating." El mismo cuadro de prompt de la barra superior (3.18) también funciona en las páginas de categoría, de páginas CMS y de marcas, y las registra en History.

### 3.18 Accesos directos: barra superior, lista de productos y Help

- **Botón de la barra superior.** Con **Admin Top Bar CTA** activado, un icono de varita mágica está en la barra superior. Abre el cuadro **My AI Gemini** con una lista **Template**, un área de texto y **Generate**. La respuesta se muestra bajo el botón, con el número de tokens. No cambia ningún campo. Use la **×** para cerrar.
- **Lista de productos.** En la lista de productos de **Catalog**, **Products**, el módulo añade un enlace **My AI Gemini** junto a las acciones masivas o en la barra de herramientas. Abre **Generate**, **Products**.
- **Help.** El botón **Help** de cada página del módulo abre la explicación de la página.

### 3.19 Marcadores de posición que puede usar en los prompts

En las plantillas, el cuadro **Instruction**, los cuadros de prompt masivos y el Playground puede escribir marcadores entre llaves. El módulo los sustituye por datos reales para cada elemento antes de enviar la instrucción.

| Marcador | Funciona para | En qué se convierte |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Productos | Los datos propios del producto en el idioma elegido. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Productos | Nombre y descripción de la categoría principal, nombres de todas las categorías (separados por comas), nombre de la marca. |
| {product_attributes}, {product_features}, {product_feature_values} | Productos | Atributos de las combinaciones, nombres de características y pares nombre de característica:valor. |
| {product_images} | Productos | Los enlaces de las imágenes del producto, separados por comas. |
| {category_name}, {category_description}, {category_parent_name} | Categorías | Los datos propios de la categoría y el nombre del padre. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | Páginas CMS, marcas (cuadro de la barra superior) | El título de la página o los datos de la marca. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Todo | Nombre de la tienda, dominio, nombre del idioma, país por defecto y código de la moneda por defecto. |

Un marcador que no tiene datos se convierte en texto vacío. Los marcadores de categorías no se sustituyen en los prompts de productos, ni al revés.

## 4. Front de la tienda

My AI Gemini no tiene interfaz para clientes. No añade nada a las páginas de producto, las páginas de categoría, el carrito, el pie de página ni la cuenta de cliente, y no hay nada en el tema que activar o desactivar. El front de la tienda no recibe ninguna plantilla del módulo, por lo que no se muestra ninguna captura de pantalla.

El módulo sí es propietario de dos direcciones web que no son páginas para clientes:

| Dirección | Quién la usa | Qué hay que saber |
|---|---|---|
| Dirección de cron (`…/module/myaigemini/cron?secret=…&action=…`) | El planificador de su servidor | Descrita en 3.12. Abierta sin el secreto correcto solo responde "The token does not exist or it's wrong!". Manténgala privada: quien la conozca puede iniciar un lote. |
| Dirección interna usada por las pantallas del módulo | Los propios botones del módulo en el back office | No la abra ni la comparta. Rechaza las peticiones sin el secreto propio del módulo ("Error! Invalid token!"). |

## 5. Problemas

**No se genera nada y veo el mensaje "The Gemini API key is not set. Add it in the module settings."**
El cuadro de la clave en **Settings**, **Gemini** está vacío. Pegue la clave de https://aistudio.google.com/apikey y pulse **Save**.

**Aparece un error de Google en un resultado, en History o en una respuesta de cron (por ejemplo un mensaje que empieza por "Google Gemini API Error").**
Google rechazó la llamada: clave incorrecta o desactivada, un modelo que su clave quizá no pueda usar, límites gratuitos agotados o una región bloqueada. Abra **History**, pulse **View** en la fila roja para leer el texto completo. Corrija la clave o elija otro modelo en **Settings**, **Gemini**, y vuelva a intentarlo.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
El modelo necesitó más tiempo que **API timeout (seconds)**. Suba el timeout en **Settings**, **General** (hasta 600), acorte el texto o elija un modelo más rápido como gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" o "The model returned an empty response."**
La respuesta se cortó o está vacía. Suba **Max Tokens** en **Settings**, **Gemini**. Algunos modelos Gemini 2.5 usan parte del límite para «pensar».

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google se negó a responder a la instrucción. Reescriba la plantilla o el texto del producto que usa.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
Se agotó el tope en **Settings**, **Studio**, **Monthly generation budget**. Súbalo o ponga 0 para quitar el límite.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** está activado y la respuesta contenía una línea de **Forbidden words**. El producto quedó sin cambios. Edite la lista, cambie el prompt o desactive la barrera.

**"Error! Prompt is missing or too short!"**
La instrucción tiene menos de 4 caracteres. Escriba una instrucción completa o elija una plantilla.

**Una fila de una ejecución masiva muestra "skipped Product skipped."**
**Existing text** está en **Skip if filled** y el campo ya tenía texto. Elija **Replace**, **Add above** o **Add below** para escribir de todos modos.

**Después de eliminar un modelo añadido, todas las peticiones fallan.**
Eliminar el modelo activo restablece el nombre del modelo a gpt-4o, que Gemini no conoce. Abra **Settings**, **Gemini**, elija un nombre de Gemini en **Model** (por ejemplo gemini-2.0-flash) y pulse **Save**.

**Las pantallas aún dicen "OpenAi" o "gpt".**
Esta versión aún conserva algunas expresiones de una versión anterior: la confirmación **OpenAi Settings Updated**, el error **OpenAi Model field is invalid!**, las etiquetas de filtro "Products that have not been updated with OpenAi content" y "Products that already have been updated with OpenAi content" en **Generate**, **Products**, el ejemplo "gpt-4.1" en el cuadro del modelo y en el mensaje "Enter a model id such as gpt-4.1.", el nombre de servicio "openai" en la columna **Provider** de History y la línea del panel **Help** "Paste the secret key from your OpenAI account". Todo ello son solo palabras. El módulo llama a Google Gemini. Use una clave de https://aistudio.google.com/apikey y nombres de modelos Gemini.

**El botón "Module settings" en Generate abre la página de otro módulo o un error.**
Ese botón apunta a los ajustes de un módulo hermano más antiguo y no a este. Use **Settings** en la barra del módulo.

**El formulario inferior "Generate category content" no hace nada.**
Solo recarga el filtro de categorías. Pulse **Run on the categories below** en el panel que está encima.

**El cron de productos no hace nada.**
Compruebe, por este orden: **Enable Cron Feature** está en **Yes** y guardado; la dirección contiene `&action=generateProductContent`; el secreto de la dirección coincide con la pantalla; hay un **Prompt Template** elegido; **Enable Debug** está en **No**; su servidor realmente llama a la dirección (mire el registro de su planificador). Una prueba en el navegador con **Enable Debug** en **Yes** imprime lo que se ejecutaría.

**El comando de cron en pantalla termina justo después del secreto y el botón "Generate Token" no hace nada.**
Limitación conocida de esta versión. La página no completa la línea de comando y el botón del token no rellena el campo. Construya usted mismo la dirección como se muestra en 3.12 y escriba un secreto largo si quiere cambiarlo.

**El cron sigue reescribiendo productos de una categoría marcada.**
Cuando **Product Categories** está marcado, en cada llamada se seleccionan los productos cuya categoría principal está marcada, aunque ya se hubieran escrito. Para las ejecuciones programadas deje el árbol de categorías vacío y limite la ejecución con **Product ID list**, o use **Enable Debug** para comprobar qué productos se eligen antes de programarlo.

**El cron procesa de nuevo los mismos productos después de vaciar History.**
Los modos de cron **pendingGemini** y **pendingField** usan History para saber qué ya está escrito. Tras **Clear list** todo cuenta como no escrito. Use **emptyField** si quiere que los campos rellenos se dejen en paz.

**Top P, Frequency Penalty y Presence Penalty no cambian nada.**
En esta versión solo **Temperature** y **Max Tokens** se envían a Gemini. Los otros tres se guardan pero no se usan.

**Falta la entrada de menú "AI Content Generator".**
Abra de nuevo cualquier página del back office; el módulo vuelve a colocar la entrada. Si sigue sin aparecer, desinstale e instale de nuevo el módulo (esto borra History y los ajustes).

**No hay panel "Modules → My AI Gemini" en la página de producto.**
Compruebe que **Product edit page Form** (o **Product Edit History**) está activado en **Settings**, **General**, que el producto se guardó una vez y que abre la pestaña **Modules** del producto. Los botones **Generate with AI** junto a los campos los añade el módulo por separado y pueden seguir visibles aunque el panel esté desactivado.

**El texto que generé desapareció después de guardar el producto.**
El formulario de producto estaba abierto con los valores antiguos. Recargue la página de producto después de usar **Fill** y edite solo después. Use **Restore** en la pestaña **History** para recuperar un texto anterior.

**El bloque Dashboard del dashboard principal de PrestaShop está vacío.**
Ese bloque no recibe las cifras de History. Abra **AI Content Generator**, **Dashboard**.

**Búsqueda de fotos: "The search did not return photos. Reload the product page and try again." o "No photos were found on the suggested pages."**
Gemini sugirió páginas que no se pudieron leer o que no contenían imágenes adecuadas. Pulse **Find pages** otra vez o mejore **AI Image Search Prompt** en **Images**. Las páginas en direcciones privadas o locales se rechazan.

**New product muestra "Failed to parse AI response. Please try again." o "Failed to create product".**
Gemini no devolvió un borrador utilizable, o la tienda rechazó los datos (por ejemplo un idioma sin nombre en el idioma por defecto). Pulse **Generate data** de nuevo, elija el idioma por defecto de la tienda y compruebe el número de categoría.

## 6. Para el desarrollador

### 6.1 Resumen

| Elemento | Valor | Dónde se define |
|---|---|---|
| Nombre técnico | `myaigemini` | Archivo principal del módulo |
| Clase principal | `myaigemini` (extends `Module`) | Archivo principal del módulo |
| Versión | **1.1.0** | Archivo principal del módulo |
| Nombre mostrado | My AI Gemini - AI content generation | Archivo principal del módulo |
| Autor | MyPresta.eu | Archivo principal del módulo |
| Tab | `front_office_features` | Archivo principal del módulo |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | Archivo principal del módulo |
| PHP | 7.0 o superior (`MIN_PHP_VERSION`, comprobado en `install()`) | Archivo principal del módulo |
| API | Google Gemini en `https://generativelanguage.googleapis.com/v1beta`, clave como parámetro de consulta `key` | Archivo principal del módulo |
| Origen de la clave | https://aistudio.google.com/apikey | Archivo principal del módulo |
| Prefijo de configuración | `MYPRESTA_MYAIGEMINI_` | Archivo principal del módulo |
| Prefijo CSS | `.mag-` (más `.myaigemini-ui`, `.myaigemini-stats`) | Archivo principal del módulo |

Flujo de datos: una pantalla (panel de producto, ejecución masiva, cuadro de la barra superior, Playground) envía por POST al controlador front del módulo `ajax` con el token secreto; el controlador construye el prompt (plantilla, marcadores, `Studio::decorate`), llama a `OpenAIService` (un cliente de Gemini que conserva su antiguo nombre de clase), escribe el resultado en el producto o la categoría e inserta una fila en `myaigemini_log`. El cron funciona igual a través del controlador front `cron`. El texto generado se guarda con `Product::save()` o `Category::save()`.

Parámetros de URL en la página de configuración: `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` es la pestaña **Gemini**; en **Generate** `products` y `categories`), rango del dashboard `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. En History: `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 Archivos

| Archivo | Finalidad | Área |
|---|---|---|
| `myaigemini.php` | Clase principal: instalación y desinstalación, formularios de configuración (General, Gemini, Studio, plantillas), Dashboard, hooks, colocación del menú, catálogo de modelos. | Código del módulo |
| `autoload.php` | Carga las clases del módulo sin Composer. | Código del módulo |
| `src/OpenAIService.php` | Cliente de Gemini (`generateContent`, `models`); timeouts; recuerda los parámetros que un modelo rechaza. | Código del módulo |
| `src/Studio.php` | Decoración del prompt, presupuesto mensual, comprobación de palabras prohibidas, SEO pack y prompts de textos alt. | Código del módulo |
| `controllers/admin/AdminMyAIGeminiMain.php` | Entrada de menú; redirige al Dashboard. | Código del módulo |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Oculto; redirige a Settings. | Código del módulo |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (filtros y paneles masivos). | Código del módulo |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Código del módulo |
| `controllers/admin/AdminMyAIGeminiCron.php` | Formularios de **Cron**. | Código del módulo |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Código del módulo |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | Formulario de **Images** y acciones de búsqueda de fotos. | Código del módulo |
| `controllers/front/ajax.php` | Acciones JSON usadas por las pantallas. | Código del módulo |
| `controllers/front/cron.php` | Punto final del cron. | Código del módulo |
| `lib/sectionHelp.php` | Texto del panel Help. | Código del módulo |
| `lib/updateChecker.php` | Comprobación de actualizaciones (`myaigeminiUpdate`). | Código del módulo |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Ayudante de compatibilidad y la herramienta de búsqueda del módulo. | Código del módulo |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Pantallas. | Código del módulo |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Comportamiento de las pantallas. | Código del módulo |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Estilos. | Código del módulo |
| `translations/*.php` | Archivos de idioma (muchos idiomas). | Código del módulo |

Recursos referenciados pero no incluidos: `views/js/admin.js`, `views/css/admin.css` (controladores Main y Settings), `views/js/product_creator.js` y `views/css/product_creator.css` (controlador New product). Se omiten en silencio; los botones de New product los gestiona `back.js`.

### 6.3 Controladores

| Controlador | Clase y padre del menú | Notas |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (padre: sección Modules) | Entrada visible **AI Content Generator**. `initContent()` redirige a la página de configuración con `mag_tab=dashboard`. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (padre: AdminMyAIGeminiMain) | Pestaña oculta (`active = 0`). **Generate**. `mag_sub` `products` / `categories`; nombres de envío `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (padre: AdminMyAIGeminiMain) | Oculto. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (respuesta de marcador "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (padre: AdminMyAIGeminiMain) | Oculto. Solo redirección. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (padre: AdminMyAIGeminiMain) | Oculto. Envío `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (padre: AdminMyAIGeminiMain) | Oculto. `clear_log` vacía la tabla del registro. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (padre: AdminMyAIGeminiMain) | Oculto. Acciones `searchImages`, `extractImages` (hosts privados rechazados), `saveImages`. Envío del formulario `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (padre: –) | Requiere `secret_token` igual a `MYPRESTA_MYAIGEMINI_TOKEN`, de lo contrario "Error! Invalid token!". Acciones: `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (ningún botón llama a esta última). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (padre: –) | Requiere `MYPRESTA_MYAIGEMINI_ENABLE_CRON` y un `secret` igual a `_SECRET` o `_CAT_SECRET` (cualquiera de los secretos abre ambas acciones). `action` = `generateProductContent` o `generateCategoryContent`. |

Los formularios de filtro de Generate enlazan "Module settings" con `configure=mychatgpt`. La salida del hook del panel de edición de productos se construye en `renderProductModulesContent()`.

SQL de selección del cron: el filtro de categorías y la lista de ids de producto se añaden a la cláusula WHERE; la condición de categoría (`id_product IN (…) OR id_category_default IN (…)`) no está entre paréntesis, por lo que el OR amplía toda la condición. `pendingGemini` y `pendingField` usan `NOT EXISTS` sobre filas de `myaigemini_log` cuyo estado está vacío o no es `error`; `pendingField` también coincide con `type = product_<field>` / `category_<field>`. `emptyField` une `product_lang` / `category_lang` para el idioma elegido. Longitudes de texto de producto al guardar: nombre 128, descripción corta 799 (cron) u 800 (ajax), meta título 69, meta descripción 159.

### 6.4 Hooks

Registrados en `install()`: `displayAdminProductsMainStepLeftColumnMiddle` (devuelve una cadena vacía), `displayAdminProductsMainStepLeftColumnBottom` (vacío), `actionProductFormBuilderModifier` (sin acción), `displayAdminProductsExtra` (renderiza el panel en la pestaña **Modules** del producto), `displayBackOfficeHeader` (carga los recursos, ejecuta `ensureLongSecrets()` y `placeModuleMenu()`, registra una sola vez la pestaña del buscador de imágenes, añade variables JS), `displayBackOfficeTop` (el cuadro de la barra superior cuando `TOPCTA` está activado, y variables JS para ids de categoría, CMS y marca), `displayFooter` (vacío), `displayHeader` (vacío), `dashboardZoneTwo` (renderiza `dashboard.tpl` sin sus datos). `actionProductGridDataModifier` existe como método pero no está registrado. El módulo no tiene métodos `enable()` ni `disable()`. El módulo no expone hooks propios.

`hookDisplayBackOfficeHeader` carga `product-fields.js` en las páginas de edición de producto y de categoría independientemente del interruptor `MYPRESTA_MYAIGEMINI_PRODUCT` (el interruptor solo controla el panel de la pestaña Modules).

### 6.5 Overrides

El módulo no tiene overrides. No sustituye ningún archivo del núcleo.

### 6.6 Base de datos

| Tabla | Contenido | Notas |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 filas insertadas en la instalación. | Creada en la instalación, eliminada en la desinstalación |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pares `old_` / `new_` para `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Índices en `id_product` y `status`. | Creada en la instalación, eliminada en la desinstalación |

Ambas tablas usan el motor de la base de datos de la tienda y se eliminan en la desinstalación. Las tres columnas de tokens también las añade en tiempo de ejecución `ensureUsageColumns()` cuando el Dashboard, History o una escritura de registro de cron/ajax las necesita y faltan. `ai_service` siempre guarda el valor `openai` (resto del pasado). El `postProcess()` del generador masivo escribe los valores de filtro enviados en claves de configuración como `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS` cada vez que se carga **Generate**. La desinstalación no elimina esas claves.

### 6.7 Claves de configuración y traducciones

Prefijo `MYPRESTA_MYAIGEMINI_`. Valores escritos por `install()`:

| Clave | Por defecto | Significado |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Interruptores de live y debug (`PrestaShopLogger` con tipo de objeto `MyAIGemini`). |
| `TIMEOUT` | `120` | Segundos; limitado a 10–600; el timeout del navegador es este valor más 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Lista de restauración, cuadro de la barra superior, panel de producto. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, texto integrado | Interruptor de la búsqueda de fotos e instrucción. `IMAGEFINDER_TAB_OK` marca la reparación única de la pestaña. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caracteres aleatorios | Token de ajax, secreto del cron de productos, secreto del cron de categorías. Los valores de menos de 24 caracteres se regeneran en la siguiente página del back office. |
| `API_KEY` | un solo espacio | Se guarda recortada; el formulario conserva la clave guardada si el cuadro está vacío. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, vacío | Modelo activo y nombres añadidos (uno por línea). Eliminar el modelo añadido activo establece `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Se envían a Gemini como `temperature` y `maxOutputTokens`. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Guardados; no incluidos en la petición a Gemini. |
| `MODEL_CAPS` | vacío | Parámetros aprendidos por modelo. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vacío | Textos de Studio. |
| `BUDGET`, `QUALITY` | `0`, `1` | Tope mensual; quality gate. |
| `ENABLE_CRON` | `0` | Interruptor global del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Elección de intervalo (6 = Every Hour). Solo guardado; usado para mostrar. |
| `updatedField`, `catupdatedField` | `description`, `description` | Campo del cron (los nombres de clave se escriben como `MYPRESTA_MYAIGEMINI_updatedField`, etc.). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Modo de selección del cron. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Tamaño del lote. |
| `promptTemplateId`, `catpromptTemplateId` | vacío | Plantilla del cron. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Idioma del cron. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, vacío | Debug del cron y selector heredado. |
| `productIdsList`, `categories` | vacío | Filtros del cron. |

La desinstalación elimina las claves anteriores más `ACTIVE_SERVICE`, `GEMINI_API_KEY` y `GEMINI_MODEL` (nombres antiguos), las pestañas y ambas tablas. El back office también elimina `GEMINI_API_KEY`, `GEMINI_MODEL` y `ACTIVE_SERVICE` en cada carga de la página de configuración. Las claves compartidas `mypresta_updates`, `update_myaigemini` y `updatev_myaigemini` pertenecen al comprobador de actualizaciones y no se eliminan.

Traducciones: añada un idioma creando `translations/{iso}.php` (el módulo incluye muchos). Los textos pasan por `$this->l()` en la clase principal y por `l s='…' mod='myaigemini'` en las plantillas. Los controladores de administración traducen mediante `trans()` en PrestaShop 8 y 9 y mediante el `l()` del módulo en 1.6 y 1.7. Textos no traducidos: el título de columna **ID**, la etiqueta **Cron Job Secret Token** y **Generate Token**, los mensajes de JavaScript en `back.js`, `image-finder.js` y la página del selector de fotos ("Write a prompt first.", "Looking for photos…" y similares), y el borrador devuelto por New product. Las descripciones de campo son entradas `desc` construidas con `fieldHelp()` en las definiciones de formulario, con la forma "What it does / How to configure / Effect"; el texto del panel Help está en `lib/sectionHelp.php`.

Los marcadores se sustituyen en `controllers/front/ajax.php` (ejecuciones interactivas) y `controllers/front/cron.php` (cron); las listas son iguales salvo que el cron no tiene marcadores de CMS ni de marca.

### 6.8 Ampliación

No hay plantilla front que sobrescribir en un tema. Para añadir marcadores de prompt, amplíe los bloques de sustitución en `ajax.php` y `cron.php`. Para cambiar el comportamiento del servicio de IA, edite `src/OpenAIService.php` (`createChatCompletion()` construye la carga útil de Gemini). Para añadir un modelo, use **Add a Gemini model** o amplíe `getPopularGeminiModels()`. El CSS personalizado puede apuntar a las clases `.mag-` en las pantallas del módulo. Cambiar el formato de la dirección de cron requiere editar `AdminMyAIGeminiCron.php` y las plantillas `cron.tpl` y `cron-info.tpl`.

## 7. Ayuda

Página del módulo: https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

Para pedir ayuda:

1. Inicie sesión en su cuenta de cliente en mypresta.eu.
2. Vaya a la página de contacto.
3. Elija el asunto **Support for paid modules**. Para los módulos de pago el formulario indica que debe haber iniciado sesión; tras iniciarla, elija este módulo en su historial de compras.
4. Describa lo que hizo, lo que esperaba y lo que vio. Añada la fila roja de **History** (ábrala con **View**) o el texto del mensaje de la pantalla, y el nombre del modelo que usa.
