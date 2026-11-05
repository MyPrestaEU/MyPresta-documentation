---
title: "My AI Mistral - AI content generation - documentación y manual de usuario"
description: "Instrucciones de configuración, uso diario y solución de problemas para comerciantes que ya tienen My AI Mistral instalado en su tienda PrestaShop."
sidebar:
  label: "My AI Mistral - AI content generation - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Meta and catalog descriptions with Mistral AI en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Requisitos

### 1.1 Tienda y servidor

| Elemento | Necesario | Notas |
|---|---|---|
| PrestaShop | 1.6 hasta 9.x | El módulo declara compatibilidad con las versiones 1.6 a 9.99.99. La pestaña **My AI Mistral** de la página de edición del producto y los pequeños botones "Generate with AI" están pensados para PrestaShop 1.7, 8 y 9. |
| PHP | 7.0 o superior | La instalación se detiene con un mensaje cuando el servidor ejecuta un PHP anterior. |
| Extensiones de PHP | cURL, JSON, mbstring, DOM | cURL se usa en cada llamada a Mistral AI. DOM y mbstring se usan para leer las páginas web del buscador de fotos y para medir y recortar el texto generado. |
| Conexión saliente | HTTPS (puerto 443) hacia `api.mistral.ai` | El servidor debe tener permiso para llamar a la API de Mistral AI. Los planes de alojamiento que bloquean las conexiones salientes no funcionan. |
| Dirección del front de la tienda | Accesible desde el navegador | Los botones del back office envían sus peticiones a una dirección del front de su tienda. Una solicitud de contraseña, una regla de cortafuegos o una página de mantenimiento que bloquee esa dirección hace que los botones fallen. |

### 1.2 Cuenta de Mistral AI

1. Cree una cuenta en la consola de Mistral AI y abra la página de claves de API: https://console.mistral.ai/api-keys/
2. Cree una clave y cópiela. La consola la muestra una sola vez.
3. Asegúrese de que la cuenta puede usar la API (un plan o una facturación que incluya acceso a la API). Cada texto generado es una petición a la API que se paga o se descuenta de su cuota.

El módulo no necesita ningún otro módulo y no añade ningún override. No muestra nada a sus clientes.

### 1.3 Costes y carga

- Un campo generado en un idioma equivale a una petición. Un lote de 40 productos con descripciones y metaetiquetas en dos idiomas son 40 × 4 × 2 = 320 peticiones, porque la opción de descripciones escribe dos campos y la opción meta escribe otros dos.
- Cada petición espera la respuesta como máximo el tiempo fijado en **API timeout (seconds)** (120 segundos por defecto). Un lote grande iniciado desde el navegador es lento por naturaleza; use cron para catálogos grandes.
- El módulo puede dejar de generar tras un número mensual de peticiones correctas (**Monthly generation budget** en Studio).

## 2. Instalación

### 2.1 Instalar el módulo

1. Abra **Modules > Module Manager** (**Modules and Services** en PrestaShop 1.6).
2. Haga clic en **Upload a module** (**Add a new module** en 1.6) y elija el archivo ZIP del módulo.
3. Haga clic en **Install** y después en **Configure**.

Lo que la instalación hace por usted:

- Añade la entrada de menú del back office **AI Content Generator** bajo **Modules**. Abre la página de ajustes del módulo, y las demás pantallas se alcanzan desde la barra de menú situada en la parte superior de esa página.
- Crea dos tablas en la base de datos: una para las plantillas de prompt y otra para el historial de peticiones.
- Guarda 16 plantillas de prompt listas para usar (nombres de producto, descripciones, metatítulos, metadescripciones y etiquetas). Todas empiezan activadas.
- Genera los códigos secretos para los botones del back office y para cron, y selecciona el modelo **mistral-small-latest**.
- No vacía la caché de PrestaShop. Si la entrada de menú no aparece, vacíe la caché en **Advanced Parameters > Performance**.

En la primera visita puede ver un mensaje verde "Mistral AI API Key has been automatically cleaned (whitespace removed)". Solo significa que la clave vacía de relleno se ha ordenado. No hay ningún problema.

### 2.2 Primeros pasos tras la instalación

1. Abra **AI Content Generator > Settings > Mistral** y pegue su clave de API.
2. Mantenga el modelo por defecto para una primera prueba y haga clic en **Save**.
3. Abra **Settings > Playground**, escriba una instrucción corta y haga clic en **Generate**. Una respuesta indica que la conexión funciona.
4. Abra un producto existente, vaya a su pestaña **Modules**, elija **My AI Mistral**, abra **Simulate** y haga clic en **Try** junto a **Meta title**. Se muestra el texto y no se guarda nada.

### 2.3 Actualización

Suba el nuevo ZIP en Module Manager del mismo modo que en la primera instalación. Los ajustes, las plantillas y el historial se conservan. La página **Updates** del módulo indica si existe una versión más reciente (sección 3.15).

### 2.4 Desinstalación

La desinstalación elimina las entradas de menú, las plantillas de prompt, todo el historial de peticiones y los ajustes del módulo, incluidos la clave de API y los secretos de cron. Una reinstalación empieza desde cero y crea secretos nuevos, por lo que hay que sustituir todas las direcciones que haya dado a un programador de tareas.

Los textos ya escritos en productos y categorías, las fotos importadas, los productos creados con **New product** y las etiquetas permanecen en su tienda. Los ajustes de la comprobación de actualizaciones y algunos valores de filtro sobrantes no se eliminan.

## 3. Configuración y trabajo en el back office

Las capturas de pantalla de este manual muestran el back office en inglés. Los nombres de menús, campos y botones se indican en inglés y en negrita, tal como los ve en pantalla.

### 3.1 Cómo fluye el trabajo

1. **Connect** – pegue la clave de API y elija el modelo (Settings – Mistral).
2. **Set the rules** – normas de la casa, presupuesto y control de calidad (Settings – Studio).
3. **Prepare prompts** – edite o añada plantillas de prompt (Settings – Prompt templates) y pruébelas en el Playground.
4. **Generate** – elija una de tres vías:
   - un producto cada vez, desde la página de edición del producto (sección 3.16) o con los pequeños botones "Generate with AI" junto a los campos (sección 3.17);
   - muchos productos o categorías a la vez, desde las páginas Generate (secciones 3.9 y 3.10);
   - automáticamente en pequeños lotes, con cron (sección 3.12).
5. **Check** – cada petición se registra en History (sección 3.13). Un texto erróneo puede restaurarse desde la pestaña History del propio producto.

Cada página de ajustes tiene su propio botón **Save**. Guarde una página antes de salir de ella, porque las páginas no comparten un único formulario.

### 3.2 Abrir el módulo y la barra de menú

Abra **Modules > AI Content Generator**, o haga clic en **Configure** en Module Manager. Cada pantalla muestra la misma barra de menú en la parte superior:

| Opción de menú | Qué abre |
|---|---|
| Dashboard | Tarjetas de uso y gráficos (sección 3.3). |
| Settings | Un grupo con cinco subpáginas: General, Mistral, Studio, Prompt templates, Playground (secciones 3.4 a 3.8). |
| Generate | Generación masiva para productos y para categorías (secciones 3.9 y 3.10). |
| New product | Crear un producto a partir de un breve briefing (sección 3.11). |
| Cron | Direcciones para la generación programada (sección 3.12). |
| History | Lista de todas las peticiones con filtros y totales de tokens (sección 3.13). |
| Images | Ajustes del buscador de fotos (sección 3.14). |
| Updates | Comprobación de actualizaciones (sección 3.15). |

Cada pantalla tiene un botón **Help**. Abre un panel lateral con una breve explicación de esa pantalla. Al pasar el ratón sobre una opción de menú aparece una pista de una línea. Debajo de cada campo encontrará una descripción en tres partes: qué hace el campo, cómo configurarlo y cuál es el efecto.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

El Dashboard cuenta lo que ha hecho el módulo en el periodo seleccionado. La línea superior indica el servicio activo y el modelo.

| Elemento | Por defecto | Qué muestra |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | rellenado según el periodo | Un intervalo personalizado. Si From es posterior a To, las dos fechas se intercambian. |
| Requests | – | Cada llamada guardada a Mistral AI en el periodo. |
| Success | – | Llamadas que devolvieron un texto. |
| Errors | – | Llamadas que fallaron. Abra History para ver el motivo. |
| Tokens sent | – | Tamaño de las instrucciones que envió. |
| Tokens received | – | Tamaño de las respuestas. |
| Requests and errors | – | Gráfico de líneas por día. |
| Tokens sent and received | – | Gráfico de líneas por día. |
| Requests by model | – | Gráfico de barras. |

La página solo informa. Desde aquí no se genera ni se modifica nada del catálogo, y History no se borra.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Abra **Settings > General**. Esta página decide lo que ven los empleados en el back office. Guardarla no cambia ningún texto de producto.

| Campo | Por defecto | Qué hace |
|---|---|---|
| Live mode | Disabled | Marca el módulo como en funcionamiento en la tienda real y no en una configuración de prueba. Actívelo en la tienda de producción. |
| Debug mode | Disabled | Escribe detalles de diagnóstico adicionales en el log de PrestaShop cuando falla una llamada al proveedor. Actívelo solo mientras investiga un error. Los clientes nunca lo ven. No es lo mismo que **Enable Debug** de la página Cron. |
| API timeout (seconds) | 120 | Cuántos segundos puede durar una llamada a Mistral antes de que el módulo se rinda. El valor se mantiene entre 10 y 600. Un valor vacío o no numérico se guarda como 120. Súbalo hacia 600 para textos largos y modelos lentos. |
| Product Edit History | Enabled | Muestra la subpestaña **History** en la página de edición del producto, para que pueda restituir un valor antiguo. Las filas pasadas permanecen en History en cualquier caso. |
| Admin Top Bar CTA | Enabled | Muestra el pequeño icono de varita en la barra superior del back office. Desactivarlo elimina solo ese botón, no el menú del módulo. |
| Product edit page Form | Enabled | Muestra el panel **My AI Mistral** (Generate, Simulate, Photos) en la pestaña **Modules** de la página de edición del producto. Desactívelo cuando solo vayan a usarse la generación masiva y cron. Los pequeños botones "Generate with AI" junto a los campos (sección 3.17) no se desactivan con este ajuste en esta versión. |
| AI Image Finder | Enabled | Muestra u oculta la búsqueda de fotos en la página de edición del producto. Una imagen se importa solo después de que usted la confirme. |
| AI Image Search Prompt | Instrucción integrada | La instrucción que se envía cuando alguien busca fotos. `{product_name}` y `{product_description}` se sustituyen por el producto actual. Mantenga la petición de una lista de direcciones de página en formato JSON. Los mismos dos campos se repiten en la página **Images**. |

Haga clic en **Save**. La confirmación es "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Abra **Settings > Mistral**. La página conecta la tienda con su cuenta de Mistral AI y define cuán variada es la redacción. Los campos de muestreo no cambian qué productos se actualizan.

| Campo | Por defecto | Qué hace |
|---|---|---|
| Mistral AI API KEY | vacío | La clave de https://console.mistral.ai/api-keys/. Los espacios se eliminan al guardar. Deje el campo intacto para conservar la clave almacenada. Se rechaza un valor de menos de 10 caracteres mientras no haya ninguna clave guardada. |
| Model | mistral-small-latest | El modelo que escribe el texto. La lista contiene los modelos integrados y los que usted añadió. Un modelo que su clave no puede usar devuelve un error de API en lugar de texto. |
| Add a Mistral model | vacío | Escriba el nombre exacto del modelo de su cuenta de Mistral y pulse **Add model**. El nuevo nombre aparece en la lista **Model** y pasa a ser el modelo activo de inmediato. Los nombres pueden contener letras, dígitos y los caracteres `.`, `_`, `:` y `-`. Junto a cada nombre añadido hay un enlace **Remove**. Los modelos integrados no se pueden eliminar. |
| Max Tokens | 3200 | La respuesta más larga en tokens. Use unos 256 para una metadescripción y 1000 o más para una descripción HTML completa. Un valor demasiado bajo corta el texto. Un valor alto cuesta más. |
| Temperature | 0.7 | Con qué libertad elige palabras el modelo, de 0 a 1. Alrededor de 0.2 va bien para metatextos y alrededor de 0.7 para descripciones. Cambie Temperature o Top P, no ambos. |
| Top P | 1 | Otra manera de limitar lo sorprendente que puede ser la siguiente palabra, de 0 a 1. Deje 1 si ajusta Temperature. |
| Frequency Penalty Value | 0 | De -2 a 2. Un valor positivo, como 0.3 a 0.6, reduce las frases repetidas dentro de una respuesta. |
| Presence Penalty Value | 0 | De -2 a 2. Un valor positivo reparte el texto en más puntos. Algunos modelos lo ignoran. |

Los modelos integrados son: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest y open-mistral-nemo.

Si Mistral rechaza uno de los ajustes numéricos para un modelo determinado, el módulo lo recuerda, omite ese ajuste para ese modelo y reintenta. No tiene que hacer nada.

El campo del nombre del modelo debe contener al menos 3 caracteres al guardar; de lo contrario la página muestra "OpenAi Model field is invalid!". La confirmación tras guardar es "OpenAi Settings Updated". Los mensajes "Model added.", "Model removed." y "That model is already built in." pertenecen a los botones de añadir y eliminar.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio se aplica sobre cada prompt, venga de donde venga la petición: página de producto, páginas Generate, cron, Playground o barra superior. Los campos vacíos se omiten.

| Campo | Por defecto | Qué hace |
|---|---|---|
| Brand voice | vacío | Un breve briefing que indica al modelo quién habla, por ejemplo "specialist workshop, short sentences, no hype". |
| Audience | vacío | El lector para el que escribir, por ejemplo "professional installers". |
| Tone | vacío | El estado de ánimo de la redacción. Basta con una o dos palabras. |
| Glossary | vacío | Nombres de marca, materiales y grafías que el modelo debe copiar exactamente. Un término por línea. |
| Forbidden words | vacío | Palabras y frases que no deben aparecer en una respuesta guardada. Una por línea. Solo se usa cuando Quality gate está Enabled. |
| Monthly generation budget | 0 | El máximo de generaciones correctas permitidas en el mes natural en curso. 0 significa sin límite. El contador vuelve a empezar el primer día del mes. Cuando se alcanza el número, la generación se detiene con un mensaje de presupuesto. Las llamadas fallidas no cuentan. |
| Quality gate | Enabled | Comprueba cada respuesta con Forbidden words antes de guardar nada. Una respuesta que contiene una palabra de la lista se rechaza, no se escribe en el producto y se guarda en History como error. Con Disabled, la respuesta se guarda igualmente. |

Haga clic en **Save studio**. La confirmación es "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

Una plantilla de prompt es una instrucción guardada. La página muestra la lista **Prompt Templates** con un botón para crear una nueva.

#### La lista

| Columna | Qué muestra |
|---|---|
| ID | Número de la plantilla. |
| Title | El nombre que ve en las listas de plantillas. |
| Prompt | El texto de la instrucción. |
| Status | Haga clic en el icono para activar o desactivar una plantilla. |
| Timestamp | Hora de creación. |

Cada fila tiene **Edit** y **Delete**. Marque varias filas y use el **Delete** masivo para eliminarlas. Las plantillas más recientes aparecen arriba.

#### El formulario "Generate Prompt Template"

| Campo | Por defecto | Qué hace |
|---|---|---|
| Status | sin definir | Las plantillas activadas se ofrecen en el panel de producto, en la página Generate – Products y en la barra superior. Las desactivadas permanecen en la tabla pero no se ofrecen allí. Elija **Enabled** antes de guardar, porque una plantilla nueva empieza sin ninguna selección. |
| Prompt title | vacío | El nombre mostrado en los desplegables. No se envía al modelo. Obligatorio. |
| Prompt content | vacío | La instrucción enviada al modelo. Los marcadores entre llaves se sustituyen para cada elemento antes del envío. Las comillas dobles se sustituyen por comillas simples al guardar. Obligatorio. |

Haga clic en **Save Prompt**. Las confirmaciones son "Prompt template successfully added!", "Prompt template successfully updated!" y "Prompt template removed.". **Go Back to Module Settings** vuelve a la lista.

#### Marcadores (placeholders)

| Marcador | Se sustituye por | Funciona en |
|---|---|---|
| {product_name} | Nombre del producto | Generación de productos |
| {product_description} | Descripción larga | Generación de productos |
| {product_description_short} | Descripción corta | Generación de productos |
| {product_tags} | Etiquetas actuales | Generación de productos |
| {product_reference} | Referencia | Generación de productos |
| {product_ean13} | Código EAN-13 | Generación de productos |
| {product_weight} | Peso | Generación de productos |
| {product_brand} | Nombre de la marca | Generación de productos |
| {product_default_category} | Nombre de la categoría por defecto | Generación de productos |
| {product_category_description} | Descripción de la categoría por defecto | Generación de productos |
| {product_categories} | Nombres de todas las categorías del producto | Generación de productos |
| {product_attributes} | Atributos de la combinación (grupo y valor) | Generación de productos |
| {product_features} | Nombres de las características | Generación de productos |
| {product_feature_values} | Características con sus valores | Generación de productos |
| {product_images} | Direcciones de las fotos del producto | Generación de productos |
| {category_name} | Nombre de la categoría | Generación de categorías |
| {category_description} | Descripción de la categoría | Generación de categorías |
| {category_parent_name} | Nombre de la categoría superior | Generación de categorías |
| {shop_name} | Nombre de la tienda | Generación de productos y de categorías |
| {shop_url} | Dominio de la tienda | Generación de productos y de categorías |
| {shop_language} | Nombre del idioma | Generación de productos y de categorías |
| {shop_country} | País por defecto | Generación de productos y de categorías |
| {shop_currency} | Código de la moneda por defecto | Generación de productos y de categorías |

"Generación de productos" significa el panel de producto, Generate – Products y el cron de productos. "Generación de categorías" significa Generate – Categories y el cron de categorías. Los marcadores no se sustituyen en el Playground ni en el cuadro de la barra superior, porque allí no hay ningún producto ni categoría seleccionados. Un marcador sin datos se sustituye por un texto vacío.

#### Las 16 plantillas que incluye el módulo

| N.º | Título | Finalidad |
|---|---|---|
| 1 | Product name 1 | Un nombre más corto y mejor, basado en el nombre actual. |
| 2 | Product name 2 | Un título de venta que usa la marca y la categoría por defecto. |
| 3 | Product description 1 | Descripción HTML con tres encabezados y las etiquetas en negrita. |
| 4 | Product description 2 | Descripción en tres secciones sencillas. |
| 5 | Product description 3 | Un briefing SEO largo que además pide ideas de encabezados, palabras clave y metatextos. |
| 6 | Product description 4 | Una petición breve de "descripción cautivadora". |
| 7 | Product description 5 | Descripción que usa las etiquetas del producto como palabras clave. |
| 8 | Product description 6 | Descripción que usa la marca y la categoría por defecto. |
| 9 | Product description 7 - using product images | Descripción que inserta las fotos del producto mediante {product_images}. |
| 10 | Product meta title 1 | Metatítulo SEO, de hasta 60 caracteres. |
| 11 | Product meta title 2 | Una segunda variante de metatítulo. |
| 12 | Product meta title 3 | Metatítulo que incluye la marca. |
| 13 | Product meta description 1 | Metadescripción SEO, de hasta 160 caracteres. |
| 14 | Product meta description 2 | Una segunda variante; el texto de ejemplo menciona un smartwatch. |
| 15 | Product meta description 3 | El mismo texto que el número 14. |
| 16 | Product tags | Cinco etiquetas en una línea, separadas por comas. |

Lea y ajuste las plantillas antes de usarlas con productos reales:

- La plantilla 3 pide al modelo que añada algunas faltas de ortografía al texto. Elimine esa frase.
- La plantilla 5 devuelve más que una descripción (ideas de encabezados, una lista de palabras clave y metatextos). Úsela como inspiración, no para guardar directamente en el campo de descripción.
- Las plantillas 5, 10, 13 y 16 piden una respuesta en inglés. Cambie esa línea si su tienda usa otro idioma.
- Las plantillas 14 y 15 están escritas para un smartwatch. Sustituya el ejemplo antes de usarlas.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

El Playground envía un prompt libre al modelo activo e imprime la respuesta debajo del botón. La respuesta se queda en esta página. No se guarda ningún producto ni categoría.

| Elemento | Por defecto | Qué hace |
|---|---|---|
| Prompt box | vacío | La instrucción para esta única llamada. Se le añaden las reglas de Studio. |
| Generate | – | Envía el prompt. Mientras espera, el área de respuesta muestra "Working…". |
| Answer area | – | La respuesta del modelo con el número de tokens usados. |

Mensajes: "Write a prompt first." (el cuadro está vacío) y "The request timed out or the shop blocked it." (véase la sección 5.2).

La petición se registra en History como cualquier otra.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Abra **Generate** y permanezca en **Products**. El trabajo tiene dos pasos: construir una lista y ejecutar la generación sobre ella.

#### Paso 1 – construir la lista ("Filter products to update")

En este paso no se envía nada al modelo. Los filtros empiezan con los valores siguientes cada vez que abre la página.

| Campo | Por defecto | Qué hace |
|---|---|---|
| Product Categories | ninguna marcada | Árbol de categorías. Solo se listan los productos que están en una categoría marcada, o que la tienen como categoría por defecto. Deje el árbol vacío para ignorar la categoría. |
| Brand | Select brand (all) | Solo productos de una marca. |
| Product status | Active | **Active**, **Disabled** o **Both**. |
| Product stock | All products | **All products** u **Only in stock products**. |
| Update only | Update all | Usa History: **Products that have not been updated with OpenAi content** lista los productos sin fila en History, **Products that already have been updated with OpenAi content** lista los productos con una fila, **Update all** ignora History. La palabra "OpenAi" en las dos primeras opciones es una etiqueta antigua; significa este módulo. Cuenta una fila de cualquier estado, también una fallida. |
| Product IDs | vacío | IDs de producto separados por comas, por ejemplo 12,45,103. Escriba solo dígitos y comas. |
| Product Reference | vacío | Una o varias referencias separadas por comas. La referencia debe coincidir exactamente. |
| Product Add Date From | vacío | Solo productos creados después de esta fecha y hora. |
| Product Add Date To | vacío | Solo productos creados antes de esta fecha y hora. |
| Minimum product ID | vacío | El ID de producto más pequeño de la lista. |
| Maximum product ID | vacío | El ID de producto más grande de la lista. |
| Product Limit | vacío | El máximo de productos que cargar. Use un número pequeño, como 20, en un catálogo grande. |

Haga clic en **Go to next step**. El botón **Module settings** que hay junto a él es un acceso directo antiguo y no abre los ajustes de este módulo.

#### Paso 2 – ejecutar la generación ("Mass product generation")

| Campo | Por defecto | Qué hace |
|---|---|---|
| Template | Choose a template | Copia una plantilla activada en el cuadro de prompt. El título en sí no se envía. |
| Prompt box | vacío | La instrucción enviada para cada producto, con los marcadores sustituidos por producto. Si el cuadro está vacío, se usa un briefing estándar para cada campo. |
| What to generate | Descriptions | **Descriptions** (descripción larga y corta), **Meta title and meta description** o **Descriptions and meta together** (los cuatro). Cada campo es una petición propia. |
| Existing text | Replace | **Replace** sobrescribe el texto. **Skip if filled** deja en paz un campo ya relleno y no llama al modelo para él. **Add above** y **Add below** conservan el texto antiguo y añaden el nuevo. |
| Languages | su idioma del back office marcado | Marque todos los idiomas que desee escribir. Cada idioma marcado es una petición más por campo. |

Haga clic en **Run on the list below**. La tabla lista los productos por ID y referencia. La ejecución recorre uno por uno cada producto, campo e idioma. La línea sobre el botón muestra el progreso, por ejemplo "3 / 120 – description", y la columna **Result** muestra la respuesta de cada paso. "skipped" significa que el campo ya tenía texto y usted eligió **Skip if filled**. Al terminar, la línea dice "Finished N products.".

No puede desmarcar productos individuales en la tabla. Cambie el filtro del paso 1 para cambiar la lista. Los nombres y las etiquetas no forman parte de esta ejecución; use la página de edición del producto o cron. El texto se guarda a medida que llega cada respuesta. Cerrar la página detiene la ejecución, y los productos ya procesados conservan su texto nuevo.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Abra **Generate** y cambie a **Categories**.

#### Paso 1 – construir la lista ("Filter categories to update")

| Campo | Por defecto | Qué hace |
|---|---|---|
| Categories | ninguna marcada | Marque las categorías que quiere listar. Sin nada marcado, la lista contiene todas las categorías que coinciden con el estado, incluidas Root y Home. Marque categorías concretas para evitarlo. |
| Category status | Active | **Active**, **Disabled** o **Both**. |

Haga clic en **Go to next step**.

#### Paso 2 – ejecutar la generación ("Mass category generation")

| Campo | Por defecto | Qué hace |
|---|---|---|
| Prompt box | vacío | La instrucción enviada para cada categoría. Use {category_name}, {category_description}, {category_parent_name} y los marcadores de la tienda. En esta página no hay lista de plantillas. |
| Field | Description | El campo que escribir: **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Solo se guarda ese campo. |
| Existing text | Replace | **Replace** o **Skip if filled**. |
| Language | su idioma del back office | Un idioma. Ejecute de nuevo para otro idioma. |

Haga clic en **Run on the categories below**. La tabla lista los ID de categoría y muestra un resultado para cada uno.

Si el cuadro de prompt está vacío, se usa un briefing estándar para descripción, metatítulo y metadescripción. Para **Name** y **Additional description** se usaría el briefing de descripción, así que escriba siempre su propio prompt para esos dos campos.

Debajo de la lista, la página también muestra el formulario más antiguo **Generate category content** con su botón **Generate content**. No genera nada. Use el botón de ejecución situado encima.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** pide al modelo un borrador completo de producto y puede insertarlo en el catálogo.

| Campo | Por defecto | Qué hace |
|---|---|---|
| What is the product? | vacío | Unas pocas frases: qué es el producto, materiales, público, nombres que conservar. Un briefing más rico da un borrador más cercano. Un cuadro vacío se rechaza. |
| Optional source URL | vacío | Una dirección http o https completa de una página pública. Su texto legible se añade al briefing. Una página que la tienda no pueda leer se ignora. |
| Language | idioma por defecto de la tienda | El idioma en el que se guardan nombre, descripciones, metatextos y etiquetas. Los demás idiomas no se rellenan. |
| Default category ID | 2 | El número de la categoría de **Catalog > Categories**. 2 suele ser Home. El producto se coloca allí. |

Botones:

- **Generate data** muestra el borrador como texto sin formato en el cuadro situado debajo de los botones. No guarda nada. El borrador contiene el nombre, descripciones, metatextos, etiquetas, referencia, un precio sugerido y características.
- **Create product** inserta el último borrador generado. El producto nuevo está **activo**, tiene un stock de **100**, usa el primer grupo de reglas de impuestos de la tienda y se coloca en la categoría que usted escribió. Tras el éxito, el cuadro muestra "Product #" y el número del nuevo producto.

El borrador no se puede editar en esta página. Revise después en el producto el precio, el impuesto, las fotos y la categoría; el precio es el que sugirió el modelo y puede ser 0. La página muestra "Add an API key in the module settings first." cuando no hay ninguna clave guardada.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Cron permite que su servidor actualice unos pocos productos o categorías cada vez que un programador de tareas abre una dirección. La página muestra: el panel **Category cron**, el formulario **CRON JOB Settings - Generate product content using Mistral AI**, el formulario **CRON JOB Settings - Generate category content using Mistral AI** y el panel **Cron parameters**. Los formularios solo construyen y guardan ajustes; nada se ejecuta hasta que su servidor llama a la dirección.

#### La dirección de cron

La dirección de productos tiene este aspecto:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

La dirección de categorías tiene este aspecto:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Sustituya `YOUR-SHOP.EXAMPLE` por la dirección de su tienda.
- Sustituya el secreto por el **Cron Job Secret Token** del formulario correspondiente. No lo publique nunca.
- La parte `&action=generateProductContent` o `&action=generateCategoryContent` es obligatoria. Sin ella, la dirección responde "Invalid action!".
- Los paneles de la página muestran la dirección solo hasta el secreto. El panel de categorías añade `&entity=category`, que la tienda no usa. Añada usted mismo la parte `action` como se muestra arriba.
- La línea "Command:" dentro de cada formulario muestra solo la dirección simple, sin el secreto ni la acción. Construya usted mismo la dirección completa.

#### Formulario de productos

| Campo | Por defecto | Qué hace |
|---|---|---|
| Enable Cron Feature | No | El interruptor general del cron de productos y de categorías. Con No, cada dirección de cron responde que la función está desactivada. |
| Cron Job Secret Token | aleatorio, 32 caracteres | La contraseña de la dirección de productos. Debe tener al menos 24 caracteres. Un secreto más corto se sustituye por uno aleatorio al cargar la página del módulo. |
| Update Field | description | Un campo por entrada del programador: name, description, description_short, meta_title, meta_description o tags. Para rellenar varios campos, cree varias entradas. |
| Selected Products | pendingMistral | Qué productos siguen esperando. **pendingMistral** toma los productos que no tienen ninguna fila correcta en History para ningún campo. **pendingField** toma los productos sin fila correcta para el campo elegido, de modo que varias entradas pueden rellenar campos distintos de los mismos productos. **emptyField** toma los productos cuyo campo elegido está vacío en el idioma elegido. |
| Product Categories | ninguna marcada | Limita la ejecución a los productos de las categorías marcadas. Véase la advertencia más abajo. |
| Product ID list | vacío | Una lista fija de IDs de producto separados por comas. Las letras se descartan al guardar. |
| Language | idioma por defecto de la tienda | El idioma que escribir. Otros idiomas necesitan su propia entrada. |
| Product to update | 5 products | Cuántos productos procesar por llamada: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000. Empiece con 5 o 10 para que un modelo lento no alcance el límite de tiempo del servidor. |
| Prompt Template | primera plantilla de la lista | La instrucción guardada que se usa para cada producto. Véase la nota más abajo. |
| Enable Debug | No | Con Yes, la dirección imprime lo que haría y no guarda nada. |
| CRON JOB interval | Every Hour | Un recordatorio de la frecuencia con la que piensa llamar a la dirección (desde cada minuto hasta cada 6 horas). El módulo no inicia nada por sí mismo. |

Haga clic en **Save**. La lista de **Prompt Template** no tiene opción vacía y muestra todas las plantillas guardadas, también las desactivadas, la más reciente primero. Hasta que guarde una, el formulario muestra la plantilla más reciente (Product tags). Elija siempre la plantilla que desea y guarde; de lo contrario se guarda la que se muestra.

Advertencia: cuando **Product Categories** tiene categorías marcadas, la tienda también elige productos cuya categoría por defecto está marcada, aunque ya se hubieran procesado. El cron puede entonces reescribir los mismos primeros productos en cada llamada. Deje vacío el árbol de categorías y use en su lugar **Product ID list**.

#### Formulario de categorías

| Campo | Por defecto | Qué hace |
|---|---|---|
| Cron Job Secret Token | aleatorio, 32 caracteres | La contraseña de la dirección de categorías. Al menos 24 caracteres. |
| Update Field | description | name, description, meta_title o meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** o **emptyField**, con el mismo significado que para los productos. |
| Language | idioma por defecto de la tienda | El idioma que escribir. |
| Categories to update | 5 categories | Cuántas categorías por llamada (las mismas opciones que para los productos). |
| Prompt Template | primera plantilla de la lista | La instrucción guardada. Escríbala para una categoría, no para un producto. |
| Enable Debug | No | Con Yes, la dirección imprime el plan y no guarda nada. |
| CRON JOB interval | Every Hour | Solo un recordatorio. |

Haga clic en **Save** bajo el formulario. Root y Home nunca los procesa el cron de categorías. El interruptor **Enable Cron Feature** está en el formulario de productos y también controla el cron de categorías.

#### Secretos y "Generate Token"

Si quiere un secreto nuevo, escríbalo a mano en el campo, de al menos 24 caracteres, con letras y dígitos. Es posible que el botón **Generate Token** no rellene el campo en esta versión, así que no cuente con él. Después de guardar un secreto nuevo, cámbielo también en su programador, porque la dirección antigua deja de funcionar. Cualquiera de los dos secretos abre cualquiera de las dos acciones, así que mantenga ambos en privado.

#### Configurar el programador de tareas

En un servidor Linux, añada a crontab una línea como esta (cada hora):

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Mantenga la dirección entre comillas, porque contiene el signo `&`. En Windows use el Programador de tareas con `curl.exe` y la misma dirección. Los paneles de alojamiento con una pantalla de "cron job" aceptan el mismo comando.

#### Probar con seguridad

1. Guarde el formulario con **Enable Cron Feature** en Yes y **Enable Debug** en Yes.
2. Abra la dirección completa en un navegador. Verá los ajustes leídos, la consulta y el prompt final, y no se guarda nada.
3. Ponga **Enable Debug** en No, guarde y abra la dirección de nuevo. La página responde ahora con un texto breve como "5 products have been updated.".

Si **Enable Debug** se queda activado, las llamadas programadas no guardan nada. Es el motivo más habitual por el que un cron "no hace nada".

El texto guardado se recorta a la longitud que permite PrestaShop: nombre 128, descripción corta 799, metatítulo 69 y metadescripción 159 caracteres. El texto antiguo se conserva en History, por lo que puede restaurarlo desde la página del producto.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Cada petición a Mistral AI se escribe en History con su instrucción, su respuesta o error, el modelo, el número de tokens y el tiempo que tardó.

#### Filtros y totales

| Elemento | Por defecto | Qué hace |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | rellenado según el periodo | Un intervalo personalizado. |
| Model | Any | Solo un modelo. |
| Type | Any | Solo un tipo de petición, por ejemplo product_description o category_meta_title. |
| Status | Any | Success o Error. |
| Language | Any | Solo un idioma. |
| Employee | Any | Solo las peticiones hechas por un empleado. |
| Product / category ID | vacío | Solo las peticiones de ese registro. |
| Prompt or reply contains | vacío | Una palabra buscada en la instrucción y en la respuesta. |
| Filter | – | Aplica los filtros. |

Las tarjetas muestran Requests, Success, Errors, Tokens sent, Tokens received, Tokens total y Average time. Un guion significa que Mistral no devolvió un recuento de tokens para esa llamada. Debajo de las tarjetas hay tablas **By day**, **By model**, **By type**, **By language** y **By employee** con las columnas Group, Calls, Sent, Received y Total. Un número pequeño junto a Calls es el número de errores de ese grupo.

#### La lista "Prompt history"

La lista sigue los filtros y muestra 50 filas por página.

| Columna | Qué muestra |
|---|---|
| ID | Número de la fila del log. |
| Status | Success o Error. |
| Prompt | La primera parte de la instrucción. |
| Reply / Error | La primera parte de la respuesta, o el texto del error. |
| Provider | El nombre del proveedor, el modelo, el código HTTP y el tiempo en segundos, separados por puntos. El nombre del proveedor sigue siendo "openai". |
| Sent / Received / Total | Tokens. |
| Entity ID | El producto o la categoría a la que iba dirigida la petición. |
| Type | El tipo de petición. |
| Timestamp | Cuándo se hizo la petición. |

Haga clic en **View** en una fila para leer el prompt y la respuesta completos. **Back to the list** vuelve a la lista.

**Clear list** (barra de herramientas) borra todas las filas, no solo las filtradas, y muestra "Log list successfully deleted.". También restablece la información que cron usa para saber qué elementos ya se actualizaron (los objetivos "pending" vuelven a empezar desde el principio), restablece el contador del presupuesto mensual y elimina los textos anteriores necesarios para **Restore**. No se puede deshacer.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

La página **AI Image Finder** contiene los mismos dos ajustes que el final de Settings – General. Guardarlos no descarga ninguna imagen ni cambia ningún texto.

| Campo | Por defecto | Qué hace |
|---|---|---|
| AI Image Finder | Enabled | Muestra u oculta la búsqueda de fotos en la página de edición del producto. |
| AI Image Search Prompt | Instrucción integrada | La instrucción que se envía cuando alguien busca fotos. `{product_name}` y `{product_description}` se sustituyen por el producto actual. El texto integrado pide exactamente 5 direcciones de página como lista JSON. Cambie la redacción si prefiere sitios de fabricantes. Un prompt vago devuelve enlaces sin relación. |

Haga clic en **Save**. La confirmación es "Settings saved.".

Cómo funciona: el modelo sugiere páginas web que probablemente muestren el producto, el módulo abre esas páginas y lista las fotos que encuentra, y usted marca las fotos que desea importar. El módulo no comprueba de quién son las fotos. Use solo fotos que tenga derecho a usar.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Elemento | Por defecto | Qué hace |
|---|---|---|
| Manual Check – Check Now | – | Pregunta una vez al servidor de actualizaciones por la última versión. La respuesta es "Module is up to date!" o "New version available!". |
| Automatic Notifications | Enabled | Aproximadamente cada tres días el módulo comprueba en segundo plano. Cuando existe una versión más reciente, los empleados ven un aviso en el back office. Elija Disabled para gestionar las actualizaciones a mano. |
| Product Page | – | Un enlace a la página del módulo. |

Haga clic en **Save**. La confirmación es "Update settings saved.". La comprobación envía a MyPresta.eu el nombre del módulo, su versión y la dirección de su tienda.

### 3.16 Página de edición del producto

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Abra **Catalog > Products**, edite un producto existente y abra la pestaña **Modules**. Elija **My AI Mistral**. La pestaña tiene las subpestañas **Generate**, **Simulate**, **Photos** y **History**. Las tres primeras aparecen cuando **Product edit page Form** está Enabled; **History** aparece cuando **Product Edit History** está Enabled.

#### Controles compartidos por Generate y Simulate

| Elemento | Por defecto | Qué hace |
|---|---|---|
| Language | primer idioma | Haga clic en un idioma, o en **Every language** para escribirlos todos uno tras otro. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** o **Skip if filled**. Se muestra solo en la subpestaña Generate. |
| Use your own instruction or a saved prompt | cerrado | Abre un cuadro de filtro y mosaicos: **Standard brief** y cada plantilla activada. Haga clic en un mosaico para usarlo. |
| Instruction | vacío | Su propio texto. Cuando está vacío, se usa el briefing estándar del campo cuyo botón pulsa. Los marcadores se sustituyen por los de este producto. |

El cuadro Instruction conserva el texto de la última ejecución. Después de pulsar un botón, el cuadro muestra el briefing que se usó, y el botón siguiente lo reutiliza. Vacíe el cuadro antes de pulsar el botón de otro campo.

#### Generate

Cada tarjeta tiene un botón **Fill**: **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** y **Tags**. El texto se **guarda de inmediato en el producto** y se muestra debajo de las tarjetas con el número de tokens. La tarjeta **SEO pack** tiene el botón **Fill all**; rellena el nombre, las dos descripciones y los dos campos meta en una sola petición y responde "SEO pack saved. Refresh the product to see it.".

Importante: el formulario del producto abierto en su navegador sigue conteniendo los textos antiguos. Recargue la página del producto antes de hacer clic en **Save** en PrestaShop; de lo contrario, los textos antiguos sobrescriben los nuevos.

#### Simulate

Las mismas tarjetas con el botón **Try**. El texto se muestra en la página y el producto no se modifica. Úselo para comparar prompts y modelos antes de que el módulo escriba.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Haga clic en **Find pages**. El modelo sugiere páginas que probablemente muestren el producto, y el módulo lista las fotos encontradas en ellas.
2. Marque las fotos que desee. El mensaje dice "Tick the photos you want, then add them to this product.".
3. Haga clic en **Add selected to this product**. Las fotos se descargan y se asocian al producto. El mensaje dice "Done. Reload the product to see the new photos." o indica el número añadido.

Cuando el buscador está desactivado, la pestaña lo indica y remite a Settings – General. Otros mensajes: "No photos were found on the suggested pages.", "The search failed." y "The photos could not be added.".

#### History

Una tabla con **When**, **Type**, **Status** y un botón **Restore** para las últimas 50 peticiones del producto. **Restore** pregunta "Restore the previous value?", devuelve el texto anterior y responde "Content successfully restored. Refresh this page to see changes.". El botón se muestra solo para cambios correctos que conservaron un texto anterior. Si no hay ninguno, la página dice "No generations for this product yet.".

### 3.17 Botones "Generate with AI" junto a los campos

En la página de edición del producto, un pequeño botón con el logotipo de Mistral está junto a los editores de **Description**, **Short description**, **Meta title** y **Meta description**. En la página de edición de categorías está junto a **Description**, **Additional description**, **Meta title** y **Meta description**.

1. Haga clic en el botón. Si la tienda tiene más de un idioma, elija **Current language**, **All languages** o **Cancel**.
2. Espere. El botón muestra un estado de ocupado mientras se ejecuta la petición.
3. El texto aparece en el campo. Haga clic en **Save** en el producto o la categoría para conservarlo. No se guarda nada antes de que lo haga.

El registro debe existir ya. En un producto nuevo, el botón responde "Save the product once before generating." y en una categoría nueva "Save the category once before generating.". Los errores aparecen en un cuadro de mensaje, por ejemplo "Generation failed.".

Estos botones usan siempre el briefing estándar del campo, no sus plantillas. Las normas de la casa, el presupuesto y el control de calidad de Studio, y el modelo de Settings, siguen aplicándose.

### 3.18 Otros accesos directos

| Lugar | Qué hace |
|---|---|
| Icono de varita en la barra superior | Abre un cuadro pequeño: **Template** opcional, un cuadro de texto y **Generate**. La respuesta se muestra en el cuadro; cópiela donde la necesite. No se guarda nada y los marcadores no se sustituyen. Oculte el icono con **Admin Top Bar CTA** en Settings – General. |
| Lista de productos | Un botón **My AI Mistral** junto a las acciones masivas o a la barra de herramientas de **Catalog > Products** abre la página Generate. |
| PrestaShop Dashboard | Un pequeño panel con los accesos directos **Mass content**, **Log** y **Cron** y el enlace al soporte de MyPresta.eu. |

## 4. Front de la tienda

My AI Mistral no tiene ninguna parte visible para los clientes. No añade bloques, páginas, scripts ni estilos a las páginas de su tienda, y los clientes no pueden ver que el módulo existe. Sus dos direcciones de front las usan solo el back office y su programador de tareas.

### 4.1 Direcciones

| Dirección | Usada por | Qué hacer |
|---|---|---|
| /module/myaimistral/cron | Su programador de tareas (sección 3.12) | Llámela con el secreto y la acción como se muestra en la sección 3.12. |
| /module/myaimistral/ajax | Los botones del back office | No la llame a mano ni la ponga en un programador de tareas. |

### 4.2 Qué responde la dirección de cron

La dirección responde con texto sin formato. Una ejecución se detiene en el primer error; los elementos ya terminados permanecen guardados.

| Respuesta | Significado | Qué hacer |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** está en No. | Póngalo en Yes y guarde. |
| The token does not exist or it's wrong! | El secreto falta, es incorrecto o es uno antiguo. | Copie el secreto actual del formulario. |
| Invalid action! | La parte `action` falta o está mal escrita. | Añada `&action=generateProductContent` o `&action=generateCategoryContent`. |
| updatedField parameter is wrong! | El campo no es uno de los permitidos. | Elija el campo de nuevo y guarde el formulario. |
| All must include all mandatory parameters! | Un ajuste guardado está vacío. | Guarde el formulario de nuevo, con un idioma y una plantilla elegidos. |
| productTarget parameter is wrong! Allowed values: … | El valor del objetivo es desconocido. | Elija **Selected Products** de nuevo. Lo mismo para el formulario de categorías. |
| No valid product IDs provided. | **Product ID list** contiene texto pero ningún número válido. | Corrija o vacíe la lista. |
| No products to update. / No categories to update. | Nada coincide con los ajustes. | Cambie los filtros o el objetivo, o dé el trabajo por terminado. |
| 5 products have been updated. / 5 categories have been updated. | La ejecución terminó. El número es el recuento. | Consulte los detalles en History. |
| 5 pending products. | Debug está activado; no se guardó nada. | Ponga **Enable Debug** en No. |
| Error! followed by a text | El proveedor devolvió un error. | Lea el texto, véase la sección 5.2. |
| Error! The model returned an empty response. | Mistral no envió texto. | Suba **Max Tokens** o cambie la plantilla. |
| Error! Could not save product 12: … | PrestaShop rechazó el texto de ese producto. | Lea el motivo que sigue; la ejecución se detuvo allí. |

## 5. Problemas

### 5.1 Instalación y menú

| Síntoma | Causa | Qué hacer |
|---|---|---|
| El instalador dice que el módulo requiere PHP 7.0 o superior | El servidor ejecuta un PHP anterior. | Cambie la versión de PHP en su panel de alojamiento e instale de nuevo. |
| "Could not create the module database tables." | El usuario de la base de datos no puede crear tablas. | Dé ese permiso al usuario o consulte con su proveedor de alojamiento. |
| Falta la entrada de menú AI Content Generator | Caché antigua, el módulo está desactivado o el perfil del empleado no tiene permiso. | Vacíe la caché, active el módulo y compruebe **Administration > Permissions** para el perfil. |
| La página del producto no tiene el panel My AI Mistral en la pestaña Modules | **Product edit page Form** y **Product Edit History** están ambos Disabled, o la página está en caché. | Active el ajuste en Settings – General y recargue la página del producto. |

### 5.2 Conexión con Mistral AI

| Síntoma | Causa | Qué hacer |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | No hay ninguna clave guardada. | Pegue la clave en Settings – Mistral. |
| "Mistral AI API KEY field is invalid!" | Menos de 10 caracteres y ninguna clave guardada. | Copie la clave completa de la consola. |
| "Mistral AI API Error (401): …" | La clave es incorrecta, está revocada o es de otra cuenta. | Cree una clave nueva y péguela de nuevo. |
| "Mistral AI API Error (429): …" | Se alcanzó un límite de Mistral. | Espere un minuto e inténtelo de nuevo, use lotes más pequeños o amplíe su plan. |
| "Mistral request timed out after N seconds…" | El modelo es lento o el texto es largo. | Suba **API timeout (seconds)** en Settings – General o use un modelo más rápido. |
| "The request timed out or the shop blocked it." | El servidor, un cortafuegos o el front de la tienda bloqueó la petición. | Permita HTTPS saliente hacia la API de Mistral y haga accesible la dirección del front de la tienda. |
| No se encuentra el modelo | Un nombre de modelo que su cuenta de Mistral no puede usar. | Elija otro modelo de la lista. |
| La lista Model cambió a gpt-4o después de eliminar un modelo | El módulo recurre a un nombre por defecto antiguo. | Elija de nuevo un modelo de Mistral y guarde. |
| "Error! Invalid token!" | El secreto que tiene la página abierta del back office ya no coincide con el de la tienda, por ejemplo tras una reinstalación. | Recargue la página. |

### 5.3 Generación

| Síntoma | Causa | Qué hacer |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | La API devolvió un error. Los detalles lo nombran. | Lea los detalles y la fila en History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | El límite de Studio se ha agotado. | Suba el presupuesto o espere al mes siguiente. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate encontró una palabra de su lista. | Edite la lista o el prompt y ejecute de nuevo. |
| "The model returned an empty response." o "The model hit the token limit before returning any text…" | **Max Tokens** es demasiado bajo o el modelo lo gastó pensando. | Suba **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral rechazó el contenido. | Reformule el prompt. |
| "Error! Prompt is missing or too short!" | El prompt tiene menos de 4 caracteres. | Escriba una instrucción más larga o deje el cuadro vacío. |
| Un metatítulo o una metadescripción termina de forma abrupta en una ejecución de cron | El cron recorta los metatítulos a 69 y las metadescripciones a 159 caracteres. | Pida en el prompt un texto más corto. |
| El producto muestra el texto antiguo tras la generación | El formulario del producto abierto en el navegador se guardó por encima. | Recargue la página del producto antes de hacer clic en Save. |
| Una fila dice "skipped" | El campo tenía texto y usted eligió Skip if filled. | Elija Replace para sobrescribir. |
| Se usa el mismo briefing para dos campos | El cuadro Instruction aún contiene el briefing anterior. | Vacíe el cuadro antes de pulsar otro campo. |
| Name o Additional description recibe en Generate – Categories un texto parecido a una descripción | El prompt vacío usa el briefing de descripción para esos dos campos. | Escriba su propio prompt. |
| "Error! This log entry has no previous value to restore." | La fila no conservó ningún texto antiguo, o la lista se vació. | El módulo no puede recuperar el texto antiguo. |
| "Error! This PrestaShop version does not support the category Additional Description field." | PrestaShop antiguo. | Omita ese campo. |

### 5.4 Fotos y New product

| Síntoma | Causa | Qué hacer |
|---|---|---|
| La pestaña Photos dice que el buscador está desactivado | **AI Image Finder** está Disabled. | Actívelo en Settings – General o en Images y recargue la página del producto. |
| "No photos were found on the suggested pages." | Las páginas sugeridas no tienen fotos utilizables. | Haga clic de nuevo en **Find pages** o añada las fotos a mano. |
| "The photos could not be added." | El servidor no pudo descargarlas. | Elija otras fotos. |
| "Failed to parse AI response. Please try again." | El modelo devolvió datos que el módulo no puede leer. | Haga clic de nuevo en **Generate data** o suba **Max Tokens**. |
| "Generate the product first." | Se hizo clic en **Create product** antes que en **Generate data**. | Genere primero. |
| "Prompt is required" | **What is the product?** está vacío. | Describa el producto. |

### 5.5 Cron

| Síntoma | Causa | Qué hacer |
|---|---|---|
| La dirección responde pero no cambia nada | **Enable Debug** está en Yes. | Póngalo en No y guarde. |
| La dirección dice que la función está desactivada | **Enable Cron Feature** está en No. | Póngalo en Yes. |
| El secreto cambió solo | Se sustituyó un secreto de menos de 24 caracteres. | Copie el nuevo secreto del formulario y actualice el programador de tareas. |
| Los mismos productos se reescriben cada vez | **Product Categories** está marcado (véase la sección 3.12). | Deje vacío el árbol de categorías y use **Product ID list**. |
| El cron usa la plantilla equivocada | El formulario mostraba la plantilla más reciente y esa elección se guardó. | Elija el **Prompt Template** correcto y guarde. |
| "Generate Token" no hace nada | El script del botón no se incluye en esta versión. | Escriba usted mismo el nuevo secreto. |
| "Command:" en el formulario no muestra ningún secreto | Muestra solo la dirección simple. | Construya la dirección como en la sección 3.12. |
| La dirección termina en un tiempo de espera agotado | Demasiados elementos por llamada. | Reduzca **Product to update**. |
| Al cabo de un tiempo se procesa todo de nuevo | **Clear list** en History eliminó el log que marca los elementos terminados. | No vacíe History mientras se ejecuta un cron, o use **Product ID list**. |

### 5.6 Textos que mencionan OpenAI o ChatGPT

El módulo se construyó a partir de un módulo anterior para otro proveedor de IA. Algunos textos aún muestran el nombre antiguo. No cambian el funcionamiento del módulo.

| Dónde | Qué ve | Significado |
|---|---|---|
| Settings – Mistral | El ejemplo de nombre de modelo en el campo de añadir es un nombre GPT; los mensajes "OpenAi Settings Updated" y "OpenAi Model field is invalid!". | Solo ejemplos y redacción. Escriba un nombre de modelo de Mistral. |
| Generate – Products | "OpenAi content" en **Update only**. | Significa contenido de este módulo. |
| Generate pages | Botón **Module settings**. | Un acceso directo antiguo que no abre este módulo. Use la barra de menú. |
| History | El proveedor muestra "openai". | Solo una etiqueta. |

## 6. Para el desarrollador

### 6.1 Resumen

| Elemento | Valor |
|---|---|
| Nombre del módulo | `myaimistral` |
| Nombre visible | My AI Mistral - AI content generation |
| Versión | 1.0.0 |
| Clase principal | `myaimistral` (`myaimistral.php`) |
| PrestaShop | 1.6 a 9.99.99 |
| PHP | 7.0.0 o superior (se comprueba en la instalación, constante `MIN_PHP_VERSION`) |
| Base de la API | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Prefijo de configuración | `MYPRESTA_MYAIMISTRAL_` |
| Tablas | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| Prefijo CSS | `.mam-` |
| Parámetros de URL | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to` y `stats_*` en History |

Carpetas: `controllers/admin`, `controllers/front`, `src` (clases con autocarga `OpenAIService` y `Studio` en el espacio de nombres `MyAIMistral`), `lib` (comprobador de actualizaciones, ayuda de sección, compatibilidad con PrestaShop 9), `views/templates`, `views/js`, `views/css`, `translations`.

El módulo no tiene overrides ni plantillas de front. La ayuda de los campos se escribe con el helper `fieldHelp($does,$how,$effect)`, que construye el texto "What it does / How to configure / Effect" de cada `desc` de HelperForm.

### 6.2 Controladores de administración, hooks y enrutamiento

| Clase del controlador | Nombre de pestaña | Finalidad |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Redirige a `AdminModules&configure=myaimistral`. |
| `AdminMyAIMistral` | Mass Content Creator | Páginas Generate (productos y categorías). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Entrada de ajustes. |
| `AdminMyAIMistralCron` | Cron Job Settings | Formularios de cron. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Página Images y las acciones de fotos `searchImages`, `extractImages`, `saveImages`. |

Los controladores de administración redirigen a `AdminHome` cuando el módulo está inactivo.

Hooks registrados en la instalación: `displayBackOfficeHeader` (recursos y valores de `Media::addJsDef` como `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (icono de la barra superior y desplegable), `displayAdminProductsExtra` y `actionProductFormBuilderModifier` (pestaña de producto), `actionProductGridDataModifier` (lista de productos), `dashboardZoneTwo` (panel del PrestaShop Dashboard), `displayAdminProductsMainStepLeftColumnMiddle` y `displayAdminProductsMainStepLeftColumnBottom` (vacíos), `displayHeader` y `displayFooter` (vacíos).

La navegación dentro de la página del módulo usa parámetros de URL:

| Parámetro | Valores | Significado |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (página del módulo); las demás pestañas son controladores | La pestaña principal de la página de configuración del módulo. |
| `mam_sub` | general, openai, studio, templates, playground (settings); products, categories (Generate) | La subpestaña. `openai` es la pestaña Mistral. |
| `mcg_preset` | today, 7, 30, 90, month, all | Periodo predefinido del Dashboard. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Intervalo personalizado del Dashboard. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | véase History | Filtros de History. `clear_log` borra el log. |

### 6.3 Contrato de cron

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Regla | Comportamiento |
|---|---|
| Interruptor | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` no debe ser 0. |
| Autenticación | `secret` debe ser igual a `SECRET` o `CAT_SECRET`. Cualquiera sirve para cualquiera de las dos acciones. |
| Sustituciones opcionales (productos) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. Reemplazan los valores guardados solo para esa llamada. |
| Sustituciones opcionales (categorías) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Campos permitidos | Productos: name, description, description_short, meta_title, meta_description, tags. Categorías: name, description, meta_title, meta_description, additional_description. |
| Objetivos | `pendingMistral`: ninguna fila de log correcta para el elemento. `pendingField`: ninguna fila de log correcta de tipo `product_FIELD` o `category_FIELD`. `emptyField`: el campo está vacío en el idioma. Las filas con estado `error` no cuentan. |
| Orden y límite | `ORDER BY id ASC LIMIT n`. Las consultas de categorías empiezan después de `PS_HOME_CATEGORY`. |
| Debug | Cuando `debug` es 1, se imprimen el SQL, los elementos seleccionados y los prompts finales, y no se guarda nada. Un valor de debug guardado igual a 1 también detiene el guardado programado. |
| Recorte | name 128, descripción corta 799, metatítulo 69, metadescripción 159. Las etiquetas pasan por `Tag::addTags`. |
| Secretos | `ensureLongSecrets()` sustituye los secretos de menos de 24 caracteres. |
| Log | Cada elemento guardado escribe una fila con `method` `cron` y el valor antiguo y el nuevo. |

El filtro de categorías del cron de productos se construye como `... AND p.id_product IN (...) OR p.id_category_default IN (...)` sin paréntesis, de modo que los productos con una categoría por defecto marcada se saltan las demás condiciones. El filtro de Generate – Products usa paréntesis y no se ve afectado.

### 6.4 Controlador AJAX

`/module/myaimistral/ajax` es un controlador de módulo de front. Cada llamada lleva `secret_token` (el valor de `TOKEN`) y responde JSON `{status, msg, date}`.

| Acción | Finalidad |
|---|---|
| `initiatePrompt` | Playground y barra superior. Puede llevar `id_category`, `id_cms` o `id_manufacturer` para sustituir `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}`. |
| `updateProduct` | Genera un campo de un producto. Comportamientos: `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (sin guardar). `keep` responde con el estado `skipped`. |
| `updateCategory` | Lo mismo para categorías (`single_category` no guarda nada). |
| `generateSeoPack` | Escribe nombre, descripciones y campos meta en una sola petición. |
| `generateAltTexts` | Escribe textos alternativos de imágenes. Sin botón en la interfaz. |
| `initiateProductRestore` | Restaura un valor anterior desde una fila de log. |
| `updateSettings` | Guarda Max Tokens, Temperature, Top P y las penalizaciones. |

El token se imprime en las páginas del back office y el controlador no comprueba la sesión de un empleado. Trate el token como un secreto.

`Studio::gate()` aplica las normas de la casa, el presupuesto mensual (cuenta las filas que no son errores) y la comprobación de palabras prohibidas. `OpenAIService` llama a Mistral con cURL, mantiene el tiempo de espera entre 10 y 600 segundos, reintenta hasta seis veces sin los parámetros que la API rechaza (recordados en `MODEL_CAPS`) y relaja la verificación SSL solo en localhost. El controlador ajax amplía el `max_execution_time` de PHP para que coincida con el tiempo de espera.

### 6.5 Claves de configuración

Todas las claves empiezan por `MYPRESTA_MYAIMISTRAL_`.

| Sufijo de la clave | Por defecto | Finalidad |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | aleatorio | Secreto de AJAX. |
| `SECRET` | aleatorio | Secreto del cron de productos. |
| `CAT_SECRET` | aleatorio | Secreto del cron de categorías. |
| `API_KEY` | un solo espacio | Clave de Mistral. |
| `MODEL` | mistral-small-latest | Modelo activo. |
| `EXTRA_MODELS` | vacío | Modelos añadidos por el comerciante, uno por línea. |
| `MODEL_CAPS` | vacío | Parámetros rechazados por modelo. |
| `TEMPERATURE` | 0.7 | Temperatura de muestreo. |
| `MAX_TOKENS` | 3200 | Límite de respuesta. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Penalizaciones. |
| `TIMEOUT` | 120 | Segundos, de 10 a 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vacío | Textos de Studio. |
| `BUDGET` | 0 | Límite mensual de peticiones. |
| `QUALITY` | 1 | Comprobación de palabras prohibidas. |
| `IMAGEFINDER_ENABLE` | 1 | Interruptor del buscador de fotos. |
| `IMAGEFINDER_PROMPT` | texto integrado | Instrucción del buscador de fotos. |
| `ENABLE_CRON` | 0 | Interruptor de cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Recordatorio del intervalo (6 es Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, idioma por defecto de la tienda, vacío, 0, vacío, vacío | Formulario del cron de productos. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, idioma por defecto de la tienda, vacío, 0 | Formulario del cron de categorías. |

Los filtros de la página Generate usan el mismo prefijo: `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, además de `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` y `EXISTING` del antiguo formulario de categorías. Se escriben en cada petición del controlador Generate y no se eliminan al desinstalar. El valor de Product IDs se inserta en la consulta tal como se escribió, con los espacios eliminados, así que reserve esa página para empleados de confianza.

### 6.6 Base de datos

| Tabla | Columnas | Notas |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 filas en la instalación. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, valores de campo `old_*` y `new_*`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Las columnas de tokens se añaden a demanda mediante `ensureUsageColumns()`. Ambas tablas se eliminan al desinstalar. |

Los valores de `type` son, por ejemplo, `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` y `error`. Los valores de `method` son `initiatePrompt`, `updateProduct`, `updateCategory` y `cron`.

### 6.7 Bloques del front-end

| Elemento | Notas |
|---|---|
| Clases | Los estilos de administración empiezan por `.mam-` (navegación, dashboard, tarjetas, chips, mosaicos, cajón de ayuda). El panel de producto usa `.myaimistral-ui` y los botones de los campos usan `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, botones del panel de producto, ejecutor masivo, New product, restore, pestañas, desplegable de la barra superior. Atributos de datos del panel de producto: `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | Los botones de campo en las páginas de producto y de categoría. Lee `window.myaimistralField`. |
| `views/js/image-finder.js` | Búsqueda e importación de fotos. |
| `views/js/admin-products-bulk.js` | El botón de la lista de productos. Lee `myaimistralAdminLink`. |
| Estilos | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Ampliar

- Nuevas plantillas de prompt: inserte una fila en `myaimistral_prompt` con `status` 1.
- Nuevos marcadores: amplíe los constructores de prompts de producto y de categoría en `controllers/front/ajax.php` y en `controllers/front/cron.php`. Los marcadores de tienda se tratan en `applyShopShortcodes()`.
- Nuevos modelos: añádalos en Settings – Mistral, o añada el nombre a la lista integrada de `myaimistral.php`.
- Otro proveedor: cambie la URL base y el cuerpo de la petición en `src/OpenAIService.php`. Todo lo demás habla solo con esa clase.
- Traducciones: use `$this->l()` en el módulo y `trans()` en los controladores en PrestaShop 8 y 9. Las cadenas están en `translations/`.

## 7. Ayuda

Página del producto: https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

Para obtener ayuda con el módulo, inicie sesión en mypresta.eu, abra **contact** y elija **Support for paid modules**. Describa el problema, sus versiones de PrestaShop y PHP y el texto del mensaje que ve. No envíe nunca la clave de API ni un secreto de cron.
