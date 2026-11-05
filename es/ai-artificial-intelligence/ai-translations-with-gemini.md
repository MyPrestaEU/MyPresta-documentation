---
title: My AI Claude - AI content generation - documentación y manual de usuario
description: Guía de configuración, uso diario y resolución de problemas para propietarios de tiendas que ya tienen My AI Claude instalado y quieren conectarlo a su cuenta de Anthropic Claude y trabajar con su catálogo.
sidebar:
  label: My AI Claude - AI content generation - documentación y manual de usuario
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with Gemini en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-gemini.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-gemini/)
>
> ---


## 1. Requisitos

My AI Claude se ejecuta dentro del back office de PrestaShop y envía sus prompts a Anthropic Claude. Necesita lo siguiente.

| Elemento | Requisito | Notas |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 y 9 (de 1.6 a 9.99.99) | Funciona en la página de producto clásica y en la nueva. |
| PHP | 7.0 o superior | Con una versión inferior la instalación se detiene y muestra un mensaje con la versión de PHP de su servidor. |
| Extensiones de PHP | cURL, JSON, mbstring, DOM, fileinfo, GD | Estándar en la mayoría de los hostings. cURL habla con Claude, DOM lee la página de origen en **New product**, GD redimensiona las fotos importadas. |
| Ajuste de PHP | `allow_url_fopen` activado | Solo lo necesita **New product** (lectura de la dirección de la página de origen). |
| Otros módulos | Ninguno | No hace falta instalar ningún otro módulo. |
| Base de datos | Sin requisitos adicionales | El módulo usa la versión de MySQL o MariaDB en la que ya funciona PrestaShop. |
| Cuenta fuera de la tienda | Una cuenta de Anthropic con acceso a la API y saldo | Cree la clave en https://console.anthropic.com/settings/keys. Anthropic factura cada generación según los tokens utilizados. |
| Red | El servidor puede abrir conexiones HTTPS | La tienda contacta con `api.anthropic.com` en cada generación. La comprobación de actualizaciones contacta con el servidor de MyPresta.eu. La función Images abre páginas web públicas. |
| Navegador | JavaScript activado | Todos los botones del módulo son scripts que se ejecutan en el back office. |

**Tiempo y memoria.** Una generación es una petición a Claude y tarda desde unos segundos hasta aproximadamente un minuto. El límite de espera se define en **Settings, General** en **API timeout (seconds)** (120 segundos al inicio, cualquier valor de 10 a 600). Configure el límite de tiempo de PHP de su servidor por encima de ese valor. Una ejecución masiva envía una petición por producto, por campo y por idioma, una tras otra, y solo funciona mientras su página permanece abierta en el navegador. El módulo no inicia ningún proceso en segundo plano y no necesita memoria adicional más allá de una página normal del back office.

## 2. Instalación

### 2.1 Subir e instalar

1. Abra **Modules → Module Manager** (PrestaShop 1.6: **Modules and Services**).
2. Haga clic en **Upload a module** (PrestaShop 1.6: **Add a new module**).
3. Seleccione el archivo ZIP del módulo y espere a que termine la subida.
4. Haga clic en **Install** cuando PrestaShop lo ofrezca.
5. Espere la confirmación. La instalación crea la entrada de menú, dos tablas de base de datos y las plantillas de prompt predefinidas (véase 3.6).

El instalador no limpia la caché. Si la entrada de menú no aparece, abra **Advanced Parameters → Performance**, haga clic en **Clear cache** y recargue la página.

Tras la instalación el módulo no hace nada hasta que introduzca su clave de Anthropic. Vaya al capítulo 3, sección 3.1.

### 2.2 Dónde aparece el módulo

El módulo añade una entrada de menú llamada **AI Content Generator** dentro de **Modules**. Haga clic en ella para abrir el módulo en su **Dashboard**. Las demás pantallas se alcanzan desde el menú horizontal de la parte superior de la página del módulo:

**Dashboard**, **Settings** (con las subpáginas **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

El módulo añade también un panel **Modules → My AI Claude** en cada página de producto, pequeños botones **Generate with AI** junto a los campos de texto de los formularios de producto y categoría, un acceso directo en la barra superior del back office y un botón **My AI Claude** sobre la lista de productos. Las secciones 3.16 y 3.17 describen cada uno.

Si un empleado que no es superadministrador no puede abrir la entrada de menú, dé al perfil de ese empleado acceso a las pantallas del módulo en **Advanced Parameters → Team → Permissions**.

### 2.3 Desactivar y desinstalar

- **Desactive** el módulo en el Module Manager para ocultar sus pantallas. Mientras esté desactivado, cualquier dirección del módulo le devuelve al dashboard principal de PrestaShop. Todos los datos se conservan.
- **Desinstalar** elimina las entradas de menú, la tabla con las plantillas de prompt, la tabla con el historial de generaciones y todos los ajustes del módulo (clave de API, modelo, reglas de Studio, ajustes de cron y secretos de cron). La History desaparece con sus puntos de restauración, y también las cifras del Dashboard.
- La desinstalación deja todo lo que el módulo ya escribió en su tienda: textos de productos y categorías, fotos importadas y productos creados con **New product**.
- La desinstalación deja también algunas selecciones de pantalla guardadas de los filtros de **Generate** y los ajustes de la comprobación de actualizaciones de MyPresta.
- **Reinstalar** empieza desde cero: la clave de API está vacía, los secretos son nuevos (las direcciones de cron cambian, así que actualice el programador de su servidor), la History está vacía y las plantillas predefinidas vuelven a su redacción original.

## 3. Configuración y trabajo diario en el back office

### 3.1 Todo el proceso, paso a paso

1. Cree una clave de API de Anthropic en https://console.anthropic.com/settings/keys y asegúrese de que la cuenta tenga saldo.
2. Abra **AI Content Generator → Settings → Claude**. Pegue la clave en **Anthropic Claude API KEY**, elija un **Model** y haga clic en **Save**.
3. Abra **Settings → Playground**, escriba una pregunta corta y haga clic en **Generate**. Una respuesta en la página confirma que la clave funciona.
4. Opcional: abra **Settings → Studio** y describa la voz de su marca, el público, el tono, los términos preferidos y las palabras prohibidas. Estas reglas se añaden a cada generación.
5. Abra **Settings → Prompt templates** y lea las plantillas predefinidas. Edite las que quiera conservar y desactive las demás.
6. Abra un producto, vaya a **Modules → My AI Claude**, pulse **Try** en la tarjeta de descripción para leer un resultado sin modificar el producto y luego pulse **Fill** para escribirlo en el producto.
7. Abra **History** y compruebe la entrada. Pulse **Restore** en el panel del producto si quiere recuperar el texto anterior.
8. Para muchos productos, abra **Generate → Products**, filtre la lista, escriba o elija un prompt y haga clic en **Run on the list below**. Pruebe primero con una lista pequeña.
9. Para ejecuciones automáticas por el servidor, configure **Cron** (sección 3.12).
10. Vigile el coste y el volumen en **Dashboard** y **History**. Defina un **Monthly generation budget** en **Studio** para limitar el uso.

### 3.2 Abrir el módulo y moverse por él

Haga clic en **AI Content Generator** dentro de **Modules**. El menú superior del módulo contiene **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** y **Updates**. Algunas páginas tienen una segunda fila: **Settings** tiene **General**, **Claude**, **Studio**, **Prompt templates** y **Playground**; **Generate** tiene **Products** y **Categories**.

Los nombres en negrita son las etiquetas del back office en inglés, y las capturas de pantalla de este manual muestran el back office en inglés. Si su back office está en otro idioma, busque las entradas equivalentes en el mismo lugar.

Cada página del módulo tiene un botón redondo **Help** en la esquina inferior derecha. Abre un panel lateral con una breve explicación de la página en la que se encuentra.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

El Dashboard muestra cuánto se ha usado el módulo. La primera línea indica el servicio y el modelo activos.

Elija el periodo con uno de los botones **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**, o escriba sus propias fechas en **From** y **To** y haga clic en **Apply**. La página se abre con **30 days**.

| Elemento | Significado | Notas |
|---|---|---|
| Requests | Número de llamadas hechas a Claude en el periodo | Cuenta cada fila de la History: ejecuciones masivas, panel de producto, Playground, barra superior, cron. |
| Success | Llamadas que devolvieron texto | |
| Errors | Llamadas que fallaron | El motivo se guarda en la fila de la History. |
| Tokens sent | Tokens de sus prompts | Los tokens son la unidad por la que factura Anthropic. |
| Tokens received | Tokens de las respuestas | |
| Requests and errors | Gráfico por día | Los periodos largos se agrupan por semana. |
| Tokens sent and received | Gráfico por día | |
| Requests by model | Gráfico | Muestra qué modelos hicieron el trabajo. |

El módulo añade también un bloque al dashboard principal de PrestaShop. Las cifras completas y los gráficos están en esta página.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Abra **Settings → General**, cambie los campos y haga clic en **Save**. El mensaje **Settings Updated** lo confirma.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Live mode | No | Una etiqueta para usted que marca la tienda como en producción. No activa ni desactiva ninguna función. |
| Debug mode | No | Escribe líneas técnicas sobre las llamadas fallidas en el registro de PrestaShop (**Advanced Parameters → Logs**). Actívelo cuando el soporte pida detalles y luego desactívelo. |
| API timeout (seconds) | 120 | Cuánto espera la tienda a Claude antes de rendirse. Los valores por debajo de 10 pasan a 10, los superiores a 600 pasan a 600, y un valor vacío o no válido pasa a 120. Aumente el valor para descripciones largas. |
| Product Edit History | Yes | Muestra la pestaña **History** en el panel del producto y permite restaurar allí el texto anterior. Si está desactivado, la pestaña desaparece. Las generaciones se siguen guardando en la History principal. |
| Admin Top Bar CTA | Yes | Muestra el pequeño icono de My AI Claude en la barra superior del back office (sección 3.17). |
| Product edit page Form | Yes | Muestra el panel **Modules → My AI Claude** en la página de producto. Si este interruptor y **Product Edit History** están desactivados, el panel queda vacío. |
| AI Image Finder | Yes | Permite la pestaña **Photos** en la página de producto. El mismo interruptor está en la página **Images**. |
| AI Image Search Prompt | Texto predefinido | La instrucción usada para encontrar páginas con fotos de un producto. El mismo campo está en la página **Images** (sección 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Esta página conecta la tienda con su cuenta de Claude. La primera vez que la abra, el módulo puede mostrar un aviso de que se han eliminado espacios en blanco del campo de la clave. Es normal.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Anthropic Claude API KEY | Vacío | El secreto que permite a la tienda llamar a su cuenta de Claude. Pegue la clave de https://console.anthropic.com/settings/keys. Los espacios se eliminan al guardar. Deje el campo intacto para conservar la clave almacenada. Si falta la clave, cada llamada falla y el error aparece en **History**. |
| Model | claude-sonnet-4-5 | El modelo de Claude que escribe el texto. Nombres integrados: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest, además de los nombres que usted añada. Un modelo que su clave no puede usar devuelve un error en lugar de texto. |
| Add a Claude model | Vacío | Escriba el nombre exacto del modelo de su cuenta de Claude y haga clic en **Add model**. El nombre aparece en la lista **Model**. Junto a cada nombre añadido hay un enlace **Remove**. Los nombres integrados no se pueden eliminar. |
| Max Tokens | 3200 | Límite superior de la longitud de la respuesta, contado en tokens. Use unos 256 para una meta descripción y 1000 o más para una descripción completa. Un valor bajo corta la respuesta. Un valor vacío se sustituye por 256. |
| Temperature | 0.7 | Cuán variada es la redacción, de 0 a 1. Más bajo es más estable, más alto es más creativo. Introduzca 0.1 para el estilo más estable, porque un simple 0 se interpreta como el valor inicial 0.7. |
| Top P | 1 | Se guarda junto con los demás campos, pero My AI Claude no lo envía a Claude. Cambiarlo no tiene efecto. |
| Frequency Penalty Value | 0 | Se guarda, pero no se envía a Claude. Cambiarlo no tiene efecto. |
| Presence Penalty Value | 0 | Se guarda, pero no se envía a Claude. Cambiarlo no tiene efecto. |

Haga clic en **Save** al final del formulario. Aparece una confirmación cuando los valores son válidos. El mensaje **Anthropic Claude API KEY field is invalid!** significa que el campo de la clave está vacío y aún no hay ninguna clave guardada.

Si un modelo rechaza uno de los ajustes (por ejemplo la temperatura), el módulo elimina ese ajuste, lo intenta de nuevo y lo recuerda para ese modelo. No tiene que hacer nada.

Los valores de muestreo (Max Tokens, Temperature) los usan las ejecuciones masivas, el panel de producto, el Playground, la barra superior y el cron. **Images** usa sus propios valores fijos.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Una plantilla es una instrucción guardada que puede elegir en las ejecuciones masivas, el panel de producto, la barra superior y el cron. La instalación crea 16 plantillas, todas activadas.

| Plantilla | Finalidad | Notas |
|---|---|---|
| Product name 1, Product name 2 | Nombres de producto más cortos o mejores | Name 2 usa la marca y la categoría predeterminada. |
| Product description 1 to 6 | Descripciones de producto | Description 1 construye un diseño HTML con encabezados y pide faltas de ortografía deliberadas. Elimine esa frase antes de usarla. Description 3 pide además ideas de H1, palabras clave, un meta título y una meta descripción, que acaban todos en el campo de descripción. |
| Product description 7 - using product images | Descripción con fotos incrustadas | Usa los enlaces de las imágenes del producto. |
| Product meta title 1 to 3 | Meta títulos | Meta title 1 pide el idioma inglés y 60 caracteres. |
| Product meta description 1 to 3 | Meta descripciones | Meta description 1 pide el idioma inglés y 160 caracteres. Meta descriptions 2 y 3 son idénticas y mencionan un smartwatch, así que reescríbalas para sus propios productos. |
| Product tags | Cinco etiquetas en una línea | Pide el idioma inglés. |

Varias plantillas piden inglés en el propio texto. Si vende en otro idioma, edite esas plantillas y elimine la línea.

La lista muestra **ID**, **Title**, **Prompt**, **Status** (haga clic en el interruptor para activar o desactivar), **Timestamp** y las acciones de fila para editar o eliminar. Seleccione varias filas y use la acción masiva **Delete** (la pregunta **Are you sure you want to delete the selected prompts?** pide confirmación). Las plantillas más recientes están arriba y la lista muestra 50 filas por página.

Para crear una plantilla, haga clic en el botón **new** de la barra de herramientas. Para modificar una, haga clic en la acción de edición de su fila.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Status | Enabled en una plantilla nueva | Solo las plantillas activadas aparecen en los selectores del módulo. |
| Prompt title | Vacío (obligatorio) | El nombre que ve en los selectores y en la lista. |
| Prompt content | Vacío (obligatorio) | La instrucción enviada a Claude. Puede usar marcadores como `{product_name}` (sección 3.18). Las comillas dobles se sustituyen por comillas simples al guardar. |

Haga clic en **Save Prompt** para guardar la plantilla. Los mensajes son **Prompt template successfully added!** y **Prompt template successfully updated!**. Una plantilla eliminada muestra **Prompt template removed.**. Haga clic en **Go Back to Module Settings** para salir del formulario sin guardar.

Una plantilla le dice a Claude qué escribir. El módulo añade además las reglas de **Studio** y el idioma de la ejecución (la sección 3.8 describe las reglas de Studio).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

El Playground es un cuadro de texto libre para probar un prompt. Escriba su prompt y haga clic en **Generate**. La respuesta aparece en la página. No se escribe nada en ningún producto ni categoría.

La llamada se guarda en la History como generación general, por lo que cuenta para el Dashboard y para el presupuesto mensual. Use el Playground para comprobar la clave de API, el modelo y el efecto de las reglas de Studio.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio contiene las reglas que se añaden a cada generación: ejecuciones masivas, panel de producto, categorías, cron, Playground y barra superior. Incluso con todos los campos de Studio vacíos, el módulo indica a Claude en qué idioma escribir (el idioma de esa ejecución).

| Campo | Al inicio | Qué hace |
|---|---|---|
| Brand voice | Vacío | Describe cómo suena su tienda. Claude lo sigue en cada texto. |
| Audience | Vacío | Describe al cliente para el que escribe. |
| Tone | Vacío | El ánimo del texto, por ejemplo cálido, técnico o neutro. |
| Glossary | Vacío | Términos que Claude debe mantener exactamente como usted los escribe. Uno por línea. |
| Forbidden words | Vacío | Palabras que Claude no debe usar. Una por línea. A Claude se le indica que no las use, y cuando el quality gate está activado, se rechaza una respuesta que aún contenga alguna. |
| Monthly generation budget | 0 | Número máximo de generaciones correctas en el mes natural en curso. 0 significa sin límite. Cuando se alcanza el número, las nuevas llamadas se detienen con el mensaje **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Las llamadas fallidas no se cuentan. |
| Quality gate | Yes | Comprueba cada respuesta en busca de palabras prohibidas antes de guardarla. Una respuesta rechazada no se escribe y muestra **The reply was rejected because it contains a forbidden word from the studio settings.** |

Haga clic en **Save studio**. El mensaje **Studio settings saved.** lo confirma.

El presupuesto cuenta todas las filas correctas de la History del mes: ejecuciones masivas, panel de producto (**Try** incluido), Playground, barra superior y cron. **New product** no se cuenta.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Abra **Generate → Products**. La página funciona en dos pasos: primero un filtro elige los productos y luego un panel ejecuta Claude sobre esa lista.

**Paso 1 – el filtro.** Rellene los campos y haga clic en **Go to next step**. El formulario siempre se abre con los valores que se muestran a continuación.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Product Categories | Nada marcado | Marque categorías para limitar la lista a los productos que contienen. Vacío significa todas las categorías. |
| Brand | All | Limita la lista a una marca. |
| Product status | Active | Active, Disabled o Both. |
| Product stock | All products | **Only in stock products** conserva los productos con cantidad superior a cero. |
| Update only | Update all | Tres opciones: solo los productos que aún no tienen entrada en la History, solo los que ya la tienen, o todos los productos. Cualquier entrada cuenta, incluidas las llamadas fallidas y las ejecuciones **Try**. |
| Product IDs | Vacío | Una lista de ID de producto. |
| Product Reference | Vacío | Limita la lista a los productos con esta referencia. |
| Product Add Date From, Product Add Date To | Vacío | Limita la lista por la fecha de creación del producto. |
| Minimum product ID, Maximum product ID | Vacío | Limita la lista a un rango de ID. |
| Product Limit | Vacío | El número máximo de productos en la lista. |

**Paso 2 – el panel Mass product generation.** Los productos coincidentes aparecen en una tabla con **ID**, **Reference** y **Result**. Sobre la tabla configura la ejecución.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Template | Nada elegido | Elige una plantilla activada y copia su texto en el cuadro del prompt. Después puede editar el texto. |
| Prompt | Vacío | La instrucción para Claude, con marcadores como `{product_name}`. Si el cuadro está vacío, el módulo usa un encargo integrado para cada campo: una descripción HTML con introducción y lista de características, un resumen corto en texto plano de menos de 400 caracteres, un meta título de unos 70 caracteres y una meta descripción de unos 160 caracteres. |
| What to generate | Descriptions | **Descriptions** (descripción larga y corta), **Meta title and meta description** o **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** o **Add below**. |
| Languages | El idioma actual marcado | Marque cada idioma que quiera escribir. |

Haga clic en **Run on the list below**. Una línea de estado muestra el progreso (por ejemplo `3 / 40` con el nombre del campo) y termina con **Finished N products.** Cada fila muestra el campo, el resultado y el mensaje, por ejemplo **Content successfully generated and updated to product.** o **Product skipped.**

Reglas de una ejecución:

- La ejecución envía una petición por producto, por campo y por idioma, una tras otra. Cuente las peticiones antes de empezar, porque cada una se factura.
- Mantenga la página abierta. Cerrarla o recargarla detiene la ejecución. Los productos ya escritos permanecen escritos.
- Un fallo en una fila no detiene las demás. El motivo está en la fila y en **History**.
- Límites al guardar: nombre de producto 128 caracteres, descripción corta 800, meta título 69, meta descripción 159. El texto más largo se recorta.
- El texto se guarda directamente en el producto. Use el panel de producto (sección 3.16) para restaurar un texto anterior.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Abra **Generate → Categories**. El primer formulario tiene **Categories** (un árbol, vacío significa todas) y **Category status** (Active, Disabled o Both, Active al inicio). Haga clic en **Go to next step**. La lista puede incluir las categorías Root y Home, así que marque las categorías que quiera.

Bajo el filtro aparece el panel **Run on the categories below** con una tabla de **ID** y **Result**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Prompt | Vacío | La instrucción para Claude. Use marcadores de categoría como `{category_name}`, `{category_description}` y `{category_parent_name}`. Los marcadores de producto no se rellenan aquí. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. |
| Existing text | Replace | **Replace** o **Skip if filled**. |
| Language | El idioma actual | Un idioma por ejecución. |

Haga clic en **Run on the categories below**. Cada fila muestra el resultado, por ejemplo **Content successfully generated and updated to category.** o **Category skipped.**

Bajo el panel la página muestra un segundo formulario llamado **Generate category content**. Su botón no inicia ninguna ejecución. Use **Run on the categories below** e ignore el segundo formulario. El botón **Go Back to Category Filter** vuelve al filtro.

Los límites al guardar son los mismos que para los productos: nombre 128 caracteres, meta título 69, meta descripción 159. El campo **Additional description** existe solo en las versiones de PrestaShop que lo tienen. En caso contrario, la fila muestra un error.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** crea un producto completo a partir de una descripción breve. Claude escribe un borrador, usted lo lee y después el módulo crea el producto en su catálogo.

| Campo | Al inicio | Qué hace |
|---|---|---|
| What is the product? | Vacío | Describa el producto en unas pocas frases: qué es, para quién es, las características principales. Es el único campo obligatorio. El texto se recorta a 8000 caracteres. |
| Optional source URL | Vacío | La dirección de una página sobre el producto. El módulo lee su título, meta descripción y precio y se los da a Claude. |
| Language | El idioma predeterminado de la tienda | El idioma del borrador. |
| Default category ID | 2 | El ID de la categoría en la que se coloca el producto. 2 es la categoría Home de una tienda estándar. |

1. Rellene los campos y haga clic en **Generate data**. El borrador aparece en la página como un bloque de datos (nombre, descripciones, campos meta, etiquetas, características, precio). Todavía no se ha guardado nada.
2. Lea el borrador. Si no es correcto, cambie la descripción y haga clic en **Generate data** de nuevo.
3. Haga clic en **Create product** solo cuando acepte el borrador. La página muestra entonces **Product #** seguido del número del nuevo producto. Encuentre el producto en **Catalog → Products**.

El nuevo producto se crea con estos ajustes: activo, disponible para pedido, precio visible, visible en el catálogo y la búsqueda, estado nuevo, la primera regla de impuestos de la tienda, un stock de 100 unidades y el precio del borrador (0 cuando el borrador no tiene ninguno). Claude rellena además el nombre, las descripciones, los campos meta, las etiquetas, las características y la referencia (máximo 32 caracteres). Después abra el producto, compruebe el precio, el impuesto, el stock y las fotos, y añada fotos con la pestaña **Photos** del panel del producto.

Si no hay ninguna clave guardada, la página muestra **Add an API key in the module settings first.** Esta página no aplica las reglas de Studio ni el presupuesto mensual, y sus llamadas no aparecen en **History** ni en el **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Cron permite que su servidor genere texto según un calendario sin que nadie haga clic. La página construye la dirección que el servidor debe abrir. No inicia ningún programador. Usted crea la tarea programada en su hosting o servidor, y cada llamada procesa un lote y se detiene.

La página tiene dos formularios: el cron de productos y el cron de categorías. El formulario de productos se describe a continuación. El de categorías tiene la misma lógica, con su propio secreto y sus propios ajustes.

Bajo la introducción de cada formulario la página muestra la dirección del cron. La dirección de productos tiene este aspecto: `https://your-shop/module/myaiclaude/cron?secret=...`. La de categorías termina en `&entity=category`.

**Complete la dirección antes de usarla.** Añada `&action=generateProductContent` al final de la dirección de productos y `&action=generateCategoryContent` al final de la de categorías. Sin ello la dirección responde **Invalid action!** y no hace nada.

Ejemplo para productos:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

La dirección usa las opciones que guardó en el formulario: campo, destino, número de productos, idioma y plantilla. Puede sobrescribirlas en la dirección (la sección 6.3 enumera los parámetros).

**Formulario del cron de productos**

| Campo | Al inicio | Qué hace |
|---|---|---|
| Enable Cron Feature | No | Interruptor general de ambas direcciones de cron (productos y categorías). Cuando está desactivado, la dirección responde **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Texto aleatorio | La contraseña larga de la dirección. Sin la correcta, la dirección responde **The token does not exist or it's wrong!** El botón **Generate Token** no funciona en esta versión (sección 5.5). Escriba su propio secreto de al menos 24 letras y dígitos, guarde y copie la nueva dirección en su programador. |
| Update Field | description | El único campo escrito por esta dirección: name, description, description_short, meta_title, meta_description o tags. Para varios campos cree varias tareas. |
| Selected Products | pendingClaude | **pendingClaude** toma los productos que aún no tienen ninguna generación correcta de My AI Claude (cualquier campo). **pendingField** toma los productos sin generación correcta para este campo, lo que le permite ejecutar una tarea para la descripción y otra para el nombre sobre los mismos productos. **emptyField** toma los productos cuyo campo elegido está vacío. |
| Product Categories | Nada marcado | Limita la ejecución a los productos de las categorías marcadas. |
| Product ID list | Vacío | Solo estos ID de producto, separados por comas. Las letras se descartan al guardar. |
| Language | El idioma predeterminado de la tienda | La versión de idioma que se escribe. Otros idiomas necesitan su propia tarea. |
| Product to update | 5 | Cuántos productos procesa una llamada. Empiece con 5 o 10 para que una respuesta lenta no alcance el límite de tiempo del servidor. La siguiente llamada continúa con los productos que aún coinciden. |
| Prompt Template | Nada guardado | La instrucción guardada que se usa para cada producto de la ejecución. Elija una y haga clic en **Save**. Sin una plantilla guardada, la dirección responde **All must include all mandatory parameters!** |
| Enable Debug | No | Al abrir la dirección en un navegador, muestra el plan, la consulta a la base de datos y el prompt final, y no guarda nada. Desactívelo antes de que el programador use la dirección. |
| CRON JOB interval | Every Hour | Una nota para usted sobre el ritmo de su programador (de cada minuto a cada 6 horas). No programa nada y no cambia la dirección. |
| Product Cron Job command | La dirección | La dirección del cron. Añada la parte `&action=` como se describe arriba. |

Haga clic en **Save** bajo el formulario. El formulario de categorías tiene los campos **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** y el secreto, y su propio botón **Save**.

Lo que hace cada llamada:

- Sustituye el campo elegido. El cron no tiene opción de conservar ni de añadir texto.
- Aplica las reglas de Studio y el presupuesto mensual. Cuando se alcanza el presupuesto, la llamada responde **Error!Monthly generation budget reached.**
- Escribe una fila de History por cada texto, para que pueda restaurarlo o revisarlo.
- Ambos secretos abren ambas acciones. El cron permanece apagado hasta que **Enable Cron Feature** sea **Yes**.

Pruebe con **Enable Debug** en **Yes** y la dirección abierta en un navegador. Cuando el plan sea correcto, póngalo en **No**, guarde y cree la tarea.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

La History es el registro de todo lo que se envió a Claude. La página se abre en **This month**.

**Filtros.** Botones rápidos: **Today**, **7 days**, **30 days**, **This month**, **All time**. Campos: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Haga clic en **Filter**.

**Tarjetas.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Paneles de desglose.** **By day**, **By model**, **By type**, **By language**, **By employee**. Cada uno muestra llamadas, tokens enviados, tokens recibidos y total. Las filas sin empleado (todas las llamadas de cron) aparecen como Unknown.

**Lista del historial de prompts.**

| Columna | Significado | Notas |
|---|---|---|
| ID | Número de fila | |
| Status | Insignia **Success** o **Error** | |
| Prompt | El texto enviado | Recortado a 180 caracteres en la lista. |
| Reply / Error | La respuesta o el mensaje de error | Recortado a 180 caracteres en la lista. |
| Provider | El servicio, el modelo, el número de estado de error cuando Claude devolvió uno, y el tiempo en segundos | |
| Sent, Received, Total | Tokens | |
| Entity ID | El producto o la categoría | Vacío en las llamadas de Playground y de la barra superior. |
| Type | Qué se generó | Véase la tabla siguiente. |
| Timestamp | Fecha y hora | |

Haga clic en la acción de ver de una fila para ver el prompt y la respuesta completos y el enlace **Back to the list**. La lista muestra 50 filas por página.

| Type | Significado | Notas |
|---|---|---|
| general | Playground y barra superior | Sin producto ni categoría. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Un campo de producto | Escrito por las ejecuciones masivas, el panel de producto, los botones con logo y el cron. |
| product_seo_pack | El paquete SEO del panel de producto | Nombre, descripciones y campos meta en una sola petición. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Un campo de categoría | |
| error | Una llamada fallida | El motivo está en **Reply / Error**. |

**Clear list** en la barra de herramientas elimina **todas** las filas tras la confirmación y muestra **Log list successfully deleted.** No se puede deshacer. También elimina los puntos de restauración de cada producto, vacía el Dashboard, reinicia el contador del presupuesto mensual y cambia qué productos cuentan como ya procesados en **Update only** y en los destinos del cron. Exporte o anote antes lo que necesite.

Cuando no hay filas en el periodo elegido, la página muestra **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Esta página controla la pestaña **Photos** de la página de producto. El formulario se llama **AI Image Finder**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| AI Image Finder | Yes | Activa la pestaña **Photos** en la página de producto. Si está desactivado, la pestaña le indica que lo active en **Settings → General**. |
| AI Image Search Prompt | Texto predefinido | La instrucción enviada a Claude para encontrar páginas web que muestren el producto. Use `{product_name}` y `{product_description}` como marcadores. Mantenga la petición de exactamente cinco direcciones de página devueltas como lista, porque el módulo lee esa lista. |

El prompt predefinido pide exactamente cinco direcciones de páginas que muestren el producto, como lista JSON, usando el nombre y la descripción del producto.

Haga clic en **Save**. El mensaje **Settings saved.** lo confirma. La página y la pestaña de **Settings → General** comparten el mismo interruptor y el mismo prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

La página **Updates** comprueba si existe una versión más reciente de My AI Claude. La comprobación envía el nombre del módulo, su versión y la dirección de la tienda al servidor de MyPresta.eu.

| Campo | Al inicio | Qué hace |
|---|---|---|
| Manual Check | Botón **Check Now** | Ejecuta la comprobación ahora. La respuesta es **Module is up to date!** o **New version available!** |
| Automatic Notifications | Enabled | Cuando está activado, el módulo comprueba aproximadamente cada tres días y muestra un aviso en el back office cuando existe una versión nueva. |
| Product Page | Un enlace | Abre la página del módulo en MyPresta.eu. |

Haga clic en **Save**. El mensaje **Update settings saved.** lo confirma.

### 3.16 Página de producto – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Abra cualquier producto, vaya a la pestaña **Modules** y busque **My AI Claude**. El panel tiene las pestañas **Generate**, **Simulate**, **Photos** y **History**. Guarde un producto nuevo una vez antes de usar el panel, porque el panel trabaja sobre un producto guardado.

**Generate y Simulate.**

1. Elija la etiqueta del idioma, o **Every language**. Al inicio está seleccionado el primer idioma de la tienda.
2. En **If the field already has text** elija **Replace**, **Add above**, **Add below** o **Skip if filled**. Al inicio está seleccionado **Replace**.
3. Pulse **Fill** en una tarjeta: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** o **Tags**. El texto se escribe directamente en el producto.
4. La tarjeta **SEO pack** tiene **Fill all**. Una sola petición devuelve el nombre, ambas descripciones y ambos campos meta. Sobrescribe esos campos, incluido el nombre. El mensaje **SEO pack saved. Refresh the product to see it.** lo confirma. Si Claude no devuelve un paquete utilizable, el panel dice **The model did not return a usable SEO pack.**
5. Abra **Use your own instruction or a saved prompt** para filtrar y elegir **Standard brief** o una plantilla activada, o escriba su propio texto en el cuadro **Instruction**. Con el cuadro vacío se usa el encargo estándar de la tarjeta.
6. La respuesta y el recuento de tokens aparecen bajo las tarjetas.

En la pestaña **Simulate** las mismas tarjetas tienen **Try**. **Try** muestra la respuesta y deja el producto sin cambios. Aun así se guarda en la History y cuenta para el presupuesto, y hace que el producto cuente como ya procesado para **Update only** y para el cron.

**Después de Fill, recargue la página del producto.** El formulario abierto sigue teniendo el texto antiguo. Si pulsa **Save** en PrestaShop sin recargar, PrestaShop sobrescribe el texto nuevo con el antiguo.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Abra la pestaña **Photos** y haga clic en **Find pages**. Mensajes: **Looking for photos…** y **Reading photos…**.
2. Marque las fotos que quiera. La página muestra **Tick the photos you want, then add them to this product.**
3. Haga clic en **Add selected to this product**. Aparece el mensaje **Adding the photos to this product…** y después el número de imágenes importadas.
4. Recargue la página del producto para ver las fotos.

El buscador lee hasta 5 páginas y ofrece hasta 24 fotos. La primera foto marcada se convierte en la portada del producto. Las fotos se descargan en su tienda y se redimensionan a todos los tamaños de imagen de su tienda. Compruebe que tiene derecho a usarlas. Cuando el buscador está desactivado, la pestaña le pide que lo active en **Settings → General**.

**History.** La pestaña muestra **When**, **Type**, **Status** y un botón **Restore** para las últimas 50 entradas de este producto. La línea de introducción dice **Earlier writes for this product. Restore puts the previous text back…** Sin entradas dice **No generations for this product yet.** Haga clic en **Restore** y confirme. Aparece el mensaje **Content successfully restored. Refresh this page to see changes.** Una fila sin valor anterior muestra **Error! This log entry has no previous value to restore.** La pestaña aparece solo cuando **Product Edit History** está activado.

### 3.17 Otros lugares donde aparece el módulo

**Botones Generate with AI junto a los campos.** Aparece un pequeño botón con el logo junto a estos campos.

| Lugar | Campos | Qué ocurre |
|---|---|---|
| Formulario de producto | Description, Short description, Meta title, Meta description | Claude escribe en el campo del formulario abierto. |
| Formulario de categoría | Description, Additional description, Meta title, Meta description | Claude escribe en el campo del formulario abierto. |

Si la tienda tiene más de un idioma, el botón pregunta si escribir el idioma actual o todos los idiomas. El texto aparece en el campo, pero no se guarda. La nota **Text is in the field. Save the product to keep it.** (para categorías: **Save the category**) se lo recuerda. En un elemento nuevo y sin guardar, el botón dice **Save the product once before generating.** (para categorías: **Save the category once…**). Cada uso se guarda en la History y hace que el producto cuente como ya procesado.

**Acceso directo de la barra superior.** El icono mágico de la barra superior del back office abre una pequeña ventana llamada **My AI Claude** con una lista **Template**, un cuadro de texto, **Generate** y un botón de cierre. Funciona como el Playground y no guarda nada. El interruptor es **Admin Top Bar CTA** en **Settings → General**.

**Lista de productos.** Un botón **My AI Claude** en la barra de herramientas sobre la lista de productos abre **Generate → Products**.

### 3.18 Marcadores para los prompts

Los marcadores son palabras entre llaves que el módulo sustituye por datos reales antes de enviar el prompt. Funcionan en las plantillas, en el cuadro de prompt de las ejecuciones masivas, en el panel de producto y en el cron.

| Marcador | Funciona para | Se sustituye por |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Productos | El nombre, la descripción, la descripción corta y las etiquetas actuales en el idioma de la ejecución. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Productos | Referencia, código EAN-13 y peso. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Productos | Marca, categoría predeterminada con su descripción y todas las categorías. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Productos | Combinaciones, nombres de características y valores de características. |
| `{product_images}` | Productos | Enlaces a las fotos del producto. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Categorías | Nombre, descripción y nombre de la categoría padre. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | En todas partes | Nombre de la tienda, dirección, idioma, país y moneda. |

Un marcador que no tiene datos se sustituye por un texto vacío.

## 4. Escaparate

My AI Claude no añade nada que sus clientes puedan ver o usar. No tiene página de front office, bloque, widget ni ajuste para el cliente. Los textos que escribe solo se hacen visibles porque están guardados en sus productos y categorías, y usted los ve a través de su tema habitual.

El módulo tiene dos direcciones que pertenecen al dominio de la tienda pero no están pensadas para los clientes.

| Dirección | Quién la usa | Qué devuelve |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | El programador de su servidor | Una respuesta en texto plano como **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** o uno de los mensajes de la tabla siguiente. |
| `…/module/myaiclaude/ajax` | Las propias pantallas del módulo en el back office | Nada útil cuando se abre a mano. Solo responde a peticiones que llevan el secreto de las pantallas. |

| Mensaje de la dirección de cron | Significado | Qué hacer |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** está en **No**. | Póngalo en **Yes** y guarde. |
| The token does not exist or it's wrong! | El secreto de la dirección no coincide con ningún secreto guardado. | Copie de nuevo la dirección desde la página **Cron**. |
| Invalid action! | Falta la parte `&action=` o está mal escrita. | Añada `&action=generateProductContent` o `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | Falta una opción obligatoria, casi siempre la plantilla de prompt. | Elija una plantilla en el formulario y haga clic en **Save**. |
| updatedField parameter is wrong! | El campo no es uno de los campos permitidos. | Elija el campo en el formulario y guarde. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | El destino de la dirección está mal escrito. | Use uno de los tres valores. |
| No valid product IDs provided. | La **Product ID list** no tiene números. | Corrija la lista o vacíela. |
| Error!… | Claude o la tienda devolvieron un error. El texto después de la palabra Error lo explica. | Lea el texto, vea el capítulo 5. |

Los hooks del módulo para el escaparate están vacíos, por lo que no añade ninguna salida a las páginas de su tienda.

## 5. Resolución de problemas

### 5.1 Menú y pantallas

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| **AI Content Generator** no está en el menú. | No se limpió la caché, el módulo está desactivado o el empleado no tiene acceso. | **Advanced Parameters → Performance → Clear cache**. Compruebe **Modules → Module Manager**. Compruebe **Advanced Parameters → Team → Permissions**. |
| Cualquier dirección del módulo vuelve al dashboard principal. | El módulo está desactivado. | Actívelo en **Module Manager**. |
| El panel **Modules → My AI Claude** de la página de producto está vacío. | **Product edit page Form** y **Product Edit History** están ambos desactivados. | Active al menos uno en **Settings → General**. |
| El panel de producto no funciona en un producto nuevo. | El producto aún no está guardado. | Guarde el producto una vez y luego use el panel. |
| Falta la pestaña **History** en el panel de producto. | **Product Edit History** está desactivado. | Actívelo en **Settings → General**. |
| El bloque de My AI Claude en el dashboard principal de PrestaShop muestra cifras vacías o a cero. | El bloque de la página principal no contiene los datos del informe. | Abra **AI Content Generator → Dashboard** para ver las cifras reales. |

### 5.2 Conexión con Claude

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| El mensaje dice que la clave de API de Anthropic Claude no está definida (**The Anthropic Claude API key is not set. Add it in the module settings.**). | No hay ninguna clave guardada. | **Settings → Claude**, pegue la clave en **Anthropic Claude API KEY**, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | El campo de la clave está vacío y no hay ninguna clave guardada. | Pegue la clave y guarde. |
| El mensaje empieza con **Anthropic Claude API Error** seguido de un texto de Anthropic. | Claude rechazó la llamada. Los motivos típicos son una clave incorrecta, un modelo que su cuenta no puede usar, falta de saldo o demasiadas peticiones. | Lea el texto después de los dos puntos. Compruebe la clave, el saldo y el modelo en su cuenta de Anthropic. Elija otro **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude respondió demasiado despacio. | Aumente **API timeout (seconds)** en **Settings → General** (máximo 600) o reduzca **Max Tokens**. Inténtelo más tarde. |
| Un mensaje que empieza con **cURL Error** | El servidor no puede alcanzar a Claude, o un cortafuegos lo bloquea. | Pida a su hosting que permita HTTPS saliente hacia `api.anthropic.com`. |
| Falta un modelo nuevo de Claude en la lista **Model**. | La lista solo contiene los nombres integrados y los que usted añadió. | Escriba el nombre exacto en **Add a Claude model** y haga clic en **Add model**. |
| Tras **Remove**, la lista **Model** muestra un modelo que no pertenece a Claude. | Al eliminar el modelo añadido activo, la tienda cambia a un nombre de reserva que Claude no conoce. | Elija un modelo de Claude en **Model** y haga clic en **Save**. |
| El módulo dice **OpenAi Settings Updated** u **OpenAi Model field is invalid!**, la columna **Provider** de la History muestra `openai`, la ayuda de la página habla de una cuenta de OpenAI y el ejemplo de **Add a Claude model** menciona un nombre GPT. | Son textos sobrantes de la versión anterior del módulo. | Nada. El módulo habla solo con Claude. Lea los textos como Claude. |
| El botón **Module settings** de los formularios de filtro de **Generate** abre una página equivocada. | El botón apunta a los ajustes de otro módulo (My ChatGPT), no a My AI Claude. | Abra **Settings** en el menú superior del módulo. |
| El registro de PrestaShop se llena de líneas sobre la lista de modelos. | **Debug mode** está activado. | Desactive **Debug mode** en **Settings → General**. |

### 5.3 Problemas de generación

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| **Error! Prompt is missing or too short!** | El prompt tiene menos de 4 caracteres. | Escriba un prompt más largo o elija una plantilla. |
| **Error! Product not found!** | El producto ya no existe. | Recargue la lista. |
| **The model hit the token limit … Increase "Max Tokens" …** | La respuesta consumió todos los tokens antes de generar texto. | Aumente **Max Tokens** en **Settings → Claude**. |
| **The model returned an empty response.** | Claude no devolvió texto. | Inténtelo de nuevo, reformule el prompt o aumente **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude rechazó el tema. | Reformule el prompt. |
| El texto se corta a mitad de frase. | **Max Tokens** es demasiado bajo. | Aumente **Max Tokens**. Use 1000 o más para una descripción completa. |
| La descripción contiene faltas de ortografía, encabezados no deseados, ideas de H1 o listas de palabras clave. | La plantilla predefinida lo pide. | Edite la plantilla en **Settings → Prompt templates** (sección 3.6). |
| El texto está en inglés aunque la tienda esté en otro idioma. | Una plantilla predefinida pide inglés, o se seleccionó el idioma equivocado. | Edite la plantilla y marque el idioma correcto en la ejecución. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | El **Quality gate** encontró una palabra de **Forbidden words**. | Ejecute de nuevo, elimine la palabra de **Studio** o desactive **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | El número de generaciones de este mes alcanzó **Monthly generation budget**. | Aumente el valor en **Settings → Studio** o póngalo en 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop rechazó el texto, por ejemplo un nombre de producto con caracteres no permitidos. | Lea los detalles en la fila y en **History**. Edite el prompt y ejecute de nuevo. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Su versión de PrestaShop no tiene ese campo. | Elija otro campo. |
| Una fila dice **Product skipped.** o **Category skipped.** | Está seleccionado **Skip if filled** y el campo ya tiene texto. | Elija **Replace** para sobrescribir. |
| Después de **Fill**, vuelve el texto antiguo. | El formulario se guardó sin recargar la página. | Recargue la página del producto después de cada **Fill** y luego continúe. |
| Una ejecución masiva se detuvo. | La página se cerró o se recargó. | Empiece de nuevo con **Update only** en la opción de productos aún no actualizados. Las llamadas fallidas cuentan allí como actualizadas. |
| La página de categorías tiene un segundo formulario con **Generate content** que no hace nada. | Ese formulario no está conectado. | Use **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | La fila de la History no tiene texto anterior. | Edite el campo a mano. |
| El resultado de **Try** no aparece en el producto, pero existe una fila de History. | **Try** nunca escribe en el producto. | Pulse **Fill** para escribirlo. |

### 5.4 Fotos y productos nuevos

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| La pestaña **Photos** le pide activar el buscador. | **AI Image Finder** está desactivado. | Actívelo en **Settings → General** o en **Images**. |
| **Claude API key is not configured. Please check module settings.** | No hay ninguna clave guardada. | **Settings → Claude**. |
| **The search failed.** | Claude o la red no respondieron. | Haga clic de nuevo en **Find pages**, compruebe la clave y el tiempo de espera. |
| **No photos were found on the suggested pages.** | Las páginas no tenían fotos utilizables. | Cambie el nombre o la descripción del producto, o edite **AI Image Search Prompt**. |
| **URL not allowed (private network).** | La dirección apunta a una red privada o local. | Use solo páginas web públicas. |
| **No images selected** | No se marcó nada. | Marque al menos una foto. |
| **No images could be imported. Details: …** | Las fotos no se pudieron descargar o no eran imágenes válidas. | Lea los detalles. Pruebe con otras fotos. |
| La foto de portada cambió. | La primera foto marcada se convierte en la portada. | Reordene las fotos en la página de producto. |
| **Add an API key in the module settings first.** (**New product**) | No hay ninguna clave guardada. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude devolvió un texto que no es un borrador válido. | Haga clic de nuevo en **Generate data**. Describa el producto con más detalle. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | La descripción está vacía, el borrador está incompleto o PrestaShop no pudo guardar el producto. | Rellene **What is the product?**, genere de nuevo, compruebe el ID de categoría. |

### 5.5 Problemas de cron

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| La dirección responde **Invalid action!** | La dirección de cron copiada de la página no tiene la parte `&action=`. | Añada `&action=generateProductContent` (productos) o `&action=generateCategoryContent` (categorías). |
| La dirección responde **Cron Job feature is disabled…** | **Enable Cron Feature** está desactivado. | Ponga **Yes** y **Save**. |
| **Generate Token** no hace nada. | El botón no está conectado en esta versión. | Escriba un secreto de al menos 24 letras y dígitos en **Cron Job Secret Token** y **Save**. Un secreto más corto se sustituye por uno aleatorio la próxima vez que se abra una página de administración. |
| La dirección responde **All must include all mandatory parameters!** | El formulario nunca se guardó, así que no hay plantilla almacenada. | Elija un **Prompt Template** y luego **Save**. |
| La dirección responde **No products to update.** aunque hay productos que necesitan texto. | **Selected Products** los excluye. **pendingClaude** omite todo producto con una generación correcta, incluidas las ejecuciones **Try**. | Use **emptyField** o **pendingField**, o defina la **Product ID list**. |
| El texto de un producto se reescribió de nuevo. | El cron siempre sustituye el campo. | Use **emptyField** para tocar solo los campos vacíos. |
| **Error!Monthly generation budget reached.** | Se agotó el presupuesto mensual. | Aumente el presupuesto en **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop rechazó el texto del producto N. | Corrija ese producto o exclúyalo y ejecute de nuevo. |
| El comando de la página no cambia al cambiar el formulario. | El comando muestra solo la dirección base. | Añada `&action=` usted mismo. Los valores del formulario se leen de los ajustes guardados. |
| El intervalo del formulario no tiene efecto. | Es una nota para usted. | Cree el calendario en el panel de su hosting. |

### 5.6 History y datos

| Síntoma | Causa | Qué pulsar |
|---|---|---|
| El Dashboard y la History están vacíos tras **Clear list**. | **Clear list** elimina todas las filas. | No hay nada que restaurar. Planifique las exportaciones antes de vaciar. |
| **This log entry no longer exists.** | La fila se eliminó. | Vuelva a la lista. |
| **Update only** no muestra productos. | El filtro usa las entradas de la History, y todos los productos ya tienen una. | Elija **Update all**. |
| Algunos productos quedan fuera de **Update only**. | Las llamadas fallidas y las ejecuciones **Try** también cuentan como entradas. | Elija **Update all**. |

## 6. Para desarrolladores

### 6.1 Visión general

My AI Claude (`myaiclaude`, versión 1.1.0, autor MyPresta.eu) es un módulo de PrestaShop para la pestaña `front_office_features`. Es compatible con PrestaShop 1.6 a 9.99.99 y PHP 7.0 y superior. Llama a la API Messages de Anthropic Claude en `https://api.anthropic.com/v1` (endpoint `/messages`) y escribe los resultados en productos y categorías.

- La clase `myaiclaude` en `myaiclaude.php` contiene la instalación, la desinstalación, las páginas de configuración y los hooks.
- La clase `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) es el cliente. Envía `model`, `max_tokens`, `messages`, un `system` opcional y un `temperature` opcional, con las cabeceras `x-api-key` y `anthropic-version: 2023-06-01`. Top P y las dos penalizaciones se guardan pero no se envían. Asigna `input_tokens` y `output_tokens` a los tokens enviados y recibidos. `listModels()` responde siempre que la lista de modelos la proporciona el catálogo del módulo, de modo que la lista de modelos es el conjunto integrado más los nombres guardados en `EXTRA_MODELS`. El timeout se limita a 10–600 segundos. Cuando la API responde 400 y nombra un parámetro, el cliente descarta ese parámetro, reintenta y recuerda la decisión por modelo en `MODEL_CAPS`.
- La clase `MyAIClaude\Studio` (`src/Studio.php`) envuelve los prompts con la línea de idioma, voz, público, tono, glosario y términos prohibidos, aplica el presupuesto mensual y la puerta de palabras prohibidas, y construye el prompt del paquete SEO.
- Las pestañas de la página de configuración usan los parámetros de URL `mac_tab` (`dashboard`, `settings`, `updates`) y `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). El valor `openai` de `mac_sub` abre la pestaña Claude. El Dashboard usa `mcg_preset` y las fechas `mac_from` y `mac_to`.
- Las clases CSS del back office usan el prefijo `.mac-`.
- Los trabajos masivos ejecutan un elemento por petición AJAX desde `back.js`.

### 6.2 Archivos

| Ruta | Finalidad | Notas |
|---|---|---|
| `myaiclaude.php` | Clase del módulo | Instalación, desinstalación, formularios, hooks, ubicación de la pestaña. |
| `autoload.php` | Cargador del espacio de nombres `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | Cliente de la API y reglas de Studio | |
| `controllers/admin/AdminMyAIClaude*.php` | Controladores del back office | Véase 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Controladores front | AJAX y cron. |
| `lib/updateChecker.php` | Comprobación de actualizaciones de MyPresta | Contacta con `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Textos del panel **Help** | |
| `lib/prestashop9compatibility.php` | Ayudantes de compatibilidad | |
| `lib/searchTool` | Ayudante de autocompletado para formularios de administración | |
| `views/templates/` | Plantillas Smarty | Hooks, páginas de administración, paneles masivos. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Estilos con el prefijo `.mac-` | |
| `translations/` | 34 archivos de idioma | |
| `upgrade/index.php` | Marcador de posición | El módulo no tiene scripts de actualización. |

### 6.3 Controladores

| Controlador | Menú o ruta | Función |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** dentro de **Modules** | Redirige al Dashboard. Padre de las pestañas ocultas. |
| AdminMyAIClaude | Pestaña oculta **Mass Content Creator** | Generate: productos y categorías. |
| AdminMyAIClaudeProductCreator | Pestaña oculta **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Pestaña oculta **Module Settings** | Redirige a la pestaña Settings. |
| AdminMyAIClaudeCron | Pestaña oculta **Cron Job Settings** | Los dos formularios de cron. |
| AdminMyAIClaudeUsage | Pestaña oculta **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Pestaña oculta **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Acciones `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Requiere `secret_token` igual a `TOKEN`. No está vinculado a una sesión de empleado. Ninguna pantalla de esta versión llama a `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Requiere `secret` igual a `SECRET` o `CAT_SECRET` y `ENABLE_CRON=1`. Parámetros: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Los parámetros que faltan se leen de los ajustes guardados. |

Las pestañas hijas se crean con `active=0` bajo `AdminMyAIClaudeMain`. En `displayBackOfficeHeader` el módulo coloca la pestaña principal bajo la pestaña padre Modules, la renombra y regenera los secretos de menos de 24 caracteres. La clase del icono es `icon-openai`. La pestaña Image Finder se registra bajo demanda y se marca con `IMAGEFINDER_TAB_OK`.

El cron de productos acepta los destinos `pendingClaude`, `pendingField` y `emptyField` y cuenta solo las filas del registro cuyo estado no es `error`. El filtro **Update only** de Generate cuenta todas las filas del registro. Las filas de registro del cron usan el método `cron`.

### 6.4 Hooks

| Hook | Comportamiento | Notas |
|---|---|---|
| `displayAdminProductsExtra` | Renderiza el panel **Modules → My AI Claude** | Pestañas Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Carga recursos, coloca el menú, regenera secretos cortos | Se ejecuta en cada página de administración. |
| `displayBackOfficeTop` | Renderiza el acceso directo de la barra superior | |
| `dashboardZoneTwo` | Renderiza `dashboard.tpl` en el dashboard de PrestaShop | La plantilla se renderiza sin sus variables de informe. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Registrados, devuelven una cadena vacía | |
| `actionProductFormBuilderModifier` | Registrado, no hace nada | |
| `displayHeader`, `displayFooter` | Registrados, vacíos | El escaparate no recibe ninguna salida. |

El módulo no tiene método `enable()` ni `disable()`. `displayCustomTop` y `top.tpl` existen, pero no se llaman.

### 6.5 Overrides

El módulo no tiene directorio `override` y no modifica ningún archivo del núcleo. Las fotos de producto se escriben con las clases de imagen de PrestaShop y el módulo escribe productos y categorías con los objetos de PrestaShop (`Product`, `Category`, `Tag::addTags`).

### 6.6 Base de datos

Tablas (prefijo como en su tienda, motor como PrestaShop):

| Tabla | Columnas | Notas |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (clave primaria), `status`, `title`, `prompt`, `date_generated` | Contiene las 16 plantillas instaladas y las suyas. |
| `myaiclaude_log` | Prompt, respuesta, estado, tipo, modelo, ID de producto o categoría, idioma, empleado, recuentos de tokens, duración, fecha | Una fila por llamada. Las columnas de tokens se añaden bajo demanda en instalaciones antiguas. |

Las escrituras de productos y categorías tocan las tablas del núcleo de los datos editados (`product`, `product_lang`, `category_lang`, `tag`, `image` y las tablas relacionadas). La desinstalación elimina las dos tablas del módulo.

### 6.7 Claves y traducciones

Las claves de configuración usan el prefijo `MYPRESTA_MYAICLAUDE_`.

| Clave (tras el prefijo) | Al inicio | Significado |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Etiqueta y registro de depuración. |
| `TIMEOUT` | 120 | Timeout de la API. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Interruptores de la página General. |
| `IMAGEFINDER_PROMPT` | Texto predefinido | Usa `{product_name}` y `{product_description}`. |
| `API_KEY` | Un solo espacio | Clave de Anthropic. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, vacío, vacío | Modelo activo, modelos añadidos, compatibilidad de parámetros aprendida. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Campos de muestreo. Los tres últimos no se envían. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Vacío | Campos de texto de Studio. |
| `BUDGET`, `QUALITY` | 0, 1 | Presupuesto mensual y quality gate. |
| `TOKEN` | 32 caracteres aleatorios | Secreto de AJAX. |
| `SECRET`, `CAT_SECRET` | 32 caracteres aleatorios | Secretos de cron de productos y categorías. |
| `ENABLE_CRON` | 0 | Interruptor del cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Notas de intervalo. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, vacío, idioma predeterminado, vacío, 0, vacío | Formulario guardado del cron de productos. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, vacío, idioma predeterminado, 0, vacío | Formulario guardado del cron de categorías. |

Las pantallas de Generate guardan también sus últimas opciones de filtro en claves como `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` y varias claves `PROD_*`. La desinstalación no las elimina, ni tampoco `mypresta_updates`, `update_myaiclaude` y `updatev_myaiclaude` de la comprobación de actualizaciones. La desinstalación elimina las demás claves y las claves antiguas del proveedor anterior.

Los textos de ayuda de los campos de los formularios se construyen con `fieldHelp()` en las tres partes **What it does**, **How to configure** y **Effect**. Las cadenas pasan por el sistema de traducción de PrestaShop (dominios de traducción del módulo y del controlador). Para añadir un idioma, coloque un archivo `translations/<iso>.php`. Los textos del panel Help proceden de `lib/sectionHelp.php`. Las respuestas del cron, los prompts de Studio y los textos de prompt predeterminados son cadenas simples en inglés en el código.

### 6.8 Ampliar

- Añada modelos con el campo **Add a Claude model**, o añadiendo el id a `EXTRA_MODELS`.
- Añada prompts como plantillas, o envíe su propio texto a través de las acciones `ajax` con el secreto.
- Los marcadores se sustituyen en `controllers/front/ajax.php`. Los marcadores `{cms_title}`, `{brand_name}`, `{brand_description}` y `{brand_short_description}` se reconocen cuando la petición lleva un ID de página CMS o de marca. Ninguna pantalla de esta versión envía esos ID.
- Construya su propio calendario con la dirección del cron y sus parámetros (sección 6.3).
- El módulo no renderiza ninguna plantilla del escaparate, por lo que un tema no tiene nada que sobrescribir.

## 7. Ayuda

Página del módulo: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

Para obtener soporte:

1. Inicie sesión en mypresta.eu.
2. Vaya a **contact**.
3. Elija **Support for paid modules**.
4. Escriba el nombre del módulo (My AI Claude), su versión (1.1.0), sus versiones de PrestaShop y PHP, y qué hizo antes de que apareciera el problema. Añada el texto del mensaje que ve.
