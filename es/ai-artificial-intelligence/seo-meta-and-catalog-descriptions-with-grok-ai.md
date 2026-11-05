---
title: "My AI Grok - AI content generation - documentación y manual de usuario"
description: "Una guía para comerciantes que ya tienen el módulo: conecte su cuenta de Grok (xAI), genere textos del catálogo desde el back office y resuelva los problemas cuando algo no funcione."
sidebar:
  label: "My AI Grok - AI content generation - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo SEO meta and catalog descriptions with Grok AI en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Requisitos

Este capítulo enumera lo que su tienda y su servidor necesitan antes de que el módulo pueda redactar textos por usted.

- **PrestaShop:** versiones de la 1.6 a la 9.x.
- **PHP:** versión 7.0 o superior. Con un PHP más antiguo, la instalación se rechaza con un mensaje.
- **Extensiones de PHP:** cURL. El módulo se comunica con Grok mediante cURL.
- **Conexión saliente:** el servidor debe poder abrir conexiones seguras (HTTPS) hacia `https://api.x.ai/v1`. Si un cortafuegos las bloquea, toda generación falla.
- **Otros módulos:** ninguno. El módulo funciona por sí solo.
- **Una cuenta de xAI:** necesita su propia cuenta en https://console.x.ai para obtener una clave de API de Grok. Las llamadas a Grok las factura xAI a su cuenta, no el módulo.
- **Catálogos grandes:** el módulo escribe un campo de un producto por petición. Por tanto, una ejecución masiva larga tarda lo que tardan todas esas peticiones juntas. Utilice los límites de lote en las pantallas Generate y Cron, y mantenga el tiempo de espera de la API lo bastante alto para los modelos lentos (véase la sección 3.4).

## 2. Instalación

### 2.1 Subir, instalar y activar

1. En el back office abra **Modules** y después **Module Manager**.
2. Suba el ZIP del módulo, o búsquelo en la lista si ya está en el servidor.
3. Haga clic en **Install**. La instalación comprueba la versión de PHP, crea los datos del módulo y después lo activa.
4. Si la instalación se detiene con un mensaje, lea la sección 5.1.

### 2.2 Qué aparece en el menú

- Aparece una nueva entrada llamada **AI Content Generator** bajo **Modules**. Al hacer clic se abre la pantalla **Dashboard** del módulo.
- Las demás pantallas del módulo (Settings, Generate, New product, Cron, History, Images, Updates) se alcanzan desde la barra de navegación en la parte superior del módulo, no desde el menú de la izquierda.
- En la página de edición del producto aparece un bloque **My AI Grok** en la pestaña **Modules**, y junto a los campos de texto aparecen pequeños botones **Generate with AI** (véase la sección 3.16).
- Puede aparecer un acceso directo con una varita mágica en la barra superior de todas las páginas del back office (véase **Admin Top Bar CTA** en la sección 3.4).

También puede llegar a los ajustes desde **Modules**, **Module Manager**, el nombre del módulo, **Configure**.

### 2.3 Caché

La instalación no vacía la caché de PrestaShop. Si la entrada del menú o el bloque del producto no aparecen justo después de instalar, vacíe usted mismo la caché en **Advanced Parameters**, **Performance** y vuelva a cargar la página.

### 2.4 Desinstalación y reinstalación

- **Qué desaparece:** la entrada de menú **AI Content Generator** y sus pantallas ocultas, las 16 plantillas de prompt ya preparadas junto con las que haya añadido, toda la History (cada prompt guardado, respuesta y recuento de tokens) y los ajustes guardados del módulo (clave de API, modelo, reglas de Studio, opciones de cron, secretos).
- **Qué permanece:** todos los textos ya escritos en productos y categorías. El módulo nunca elimina los textos generados.
- **Restos:** algunas elecciones recordadas de las pantallas Generate (filtros como el último idioma o estado elegido) pueden seguir guardadas en la tienda. No tienen ningún efecto.
- **Reinstalación:** una instalación nueva parte de los valores por defecto indicados en el capítulo 3. Su clave de API, las reglas de Studio, las plantillas propias y la History no se restauran, así que anote o exporte antes lo que necesite.

## 3. Configuración y trabajo en el back office

Este es el capítulo principal. Empieza con todo el proceso de trabajo y después describe cada pantalla en el orden de la barra de navegación.

Las capturas de pantalla proceden de un back office en inglés. En este capítulo los nombres de botones, campos y mensajes aparecen en negrita tal como figuran en la interfaz en inglés; las explicaciones están en español.

### 3.1 Todo el proceso, paso a paso

1. **Conecte Grok.** Abra **Settings** y después **Grok**. Pegue su clave de API de https://console.x.ai y elija un modelo. Guarde.
2. **Defina su estilo de la casa (opcional).** Abra **Settings** y después **Studio**. Rellene la voz, el público, el tono, un glosario de nombres que deben conservarse, las palabras prohibidas, un presupuesto mensual y la puerta de calidad. Deje vacío lo que no necesite.
3. **Pruebe con seguridad.** Use **Settings** y después **Playground** para enviar una instrucción libre y leer la respuesta. En la página de un producto use la pestaña **Simulate** y **Try**. En estos dos lugares no se guarda nada en el catálogo.
4. **Rellene un producto.** Abra el producto, vaya a la pestaña **Modules**, **My AI Grok**, **Generate**, elija el idioma y pulse **Fill** junto al campo. O use los botones **Generate with AI** junto a los campos propios del producto y guarde después el producto.
5. **Rellene muchos productos.** Abra **Generate**, **Products**. Filtre la lista, pulse **Go to next step**, elija una plantilla o escriba una instrucción, elija qué generar, cómo tratar el texto existente y en qué idiomas, y pulse **Run on the list below**. Haga lo mismo con las categorías en **Generate**, **Categories**.
6. **Lotes sin supervisión.** Abra **Cron**, guarde sus opciones y copie la dirección en el programador de tareas de su servidor (véanse las secciones 3.12 y 4.2).
7. **Auditar y deshacer.** **History** muestra cada llamada con su prompt, respuesta, estado y tokens. En un producto, la pestaña **History** le permite recuperar un texto anterior con **Restore**.

El texto generado se escribe directamente en el catálogo en cuanto llega cada respuesta. Antes de una primera ejecución grande, pruebe con unos pocos productos mediante **Simulate** o los filtros **Product IDs** y **Product Limit**.

### 3.2 Navegación y el panel Help

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard: la barra de navegación está en la parte superior de todas las pantallas del módulo.*

La barra muestra el nombre del módulo con su versión y estos elementos, en este orden:

| Elemento | Qué encontrará allí |
|---|---|
| **Dashboard** | Gráficos de peticiones, tokens y errores. |
| **Settings** | Cinco subpestañas: **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Dos subpestañas: **Products** y **Categories** para ejecuciones masivas. |
| **New product** | Crea un producto nuevo a partir de un breve resumen. |
| **Cron** | Construye direcciones que el servidor puede llamar de forma programada. |
| **History** | La lista completa de llamadas con filtros. |
| **Images** | Interruptor e instrucción para la búsqueda de imágenes de producto. |
| **Updates** | Comprueba si hay publicada una versión más reciente del módulo. |

Pase el ratón sobre un elemento para leer una breve explicación. Un botón redondo **Help** en el borde de la pantalla abre un panel lateral con ayuda sobre la página en la que está. Ciérrelo con la cruz.

Cada campo del módulo se explica en pantalla en tres partes: **What it does**, **How to configure** y **Effect**. Las tablas siguientes reformulan esos textos con palabras sencillas y añaden el valor que tiene el campo justo tras la instalación.

### 3.3 Dashboard

Abra **AI Content Generator** bajo **Modules**, o el elemento **Dashboard** de la barra.

- **Intervalos predefinidos de fechas:** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. La página se abre en **30 days**.
- **From** y **To:** elija sus propias fechas y pulse **Apply**. Si From es posterior a To, las fechas se intercambian.
- **Active service:** muestra Grok y el modelo seleccionado en Settings.
- **Tarjetas:** **Requests** (cada llamada guardada), **Success**, **Errors**, **Tokens sent** (tamaño de los prompts) y **Tokens received** (tamaño de las respuestas).
- **Gráficos:** **Requests and errors**, **Tokens sent and received** y **Requests by model**. Para intervalos de más de cuatro meses aproximadamente, los días se agrupan por semanas.

| Control | Tras instalar | Qué hace |
|---|---|---|
| **Presets** | 30 days | Cuenta las generaciones de Grok guardadas en History dentro de las fechas elegidas. La clave de API y el modelo no se eligen aquí, sino en Settings. |
| **From / To / Apply** | últimos 30 días | Dibuja solo ese fragmento. Desde esta página no se genera ni cambia nada en el catálogo, y la History no se borra. |

### 3.4 Settings – General

Abra **Settings** y después **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General: interruptores para toda la tienda y el tiempo de espera de la API.*

Estos interruptores deciden lo que ven los empleados en el back office. Guardar aquí no cambia por sí solo el texto de los productos. Pulse **Save**; la confirmación dice **Settings Updated**.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Live mode** | Desactivado | Marca el módulo como funcionando en la tienda real y no en una instalación de prueba. Actívelo en la tienda de producción. Déjelo desactivado en una copia de pruebas (staging) si no quiere que el personal trate las herramientas como listas. Desactivado mantiene las mismas herramientas, pero indica que no es la instalación de producción. |
| **Debug mode** | Desactivado | Escribe detalles de diagnóstico adicionales cuando falla una llamada a Grok. Actívelo solo mientras investiga un error y luego desactívelo. Activado añade mensajes técnicos al registro de PrestaShop (**Advanced Parameters**, **Logs**). Desactivado limita el registro al historial normal de generación. Los clientes nunca ven esto. |
| **API timeout (seconds)** | 120 | Cuántos segundos puede durar una llamada a Grok antes de que el módulo desista. Use 120 para descripciones normales. Súbalo hacia 600 para paquetes SEO largos o modelos lentos. No baje de 10. Los valores inferiores a 10 se guardan como 10 y los superiores a 600 como 600; un valor vacío o no numérico se guarda como 120. Un tiempo de espera corto falla rápido y registra un error. Uno largo espera a un modelo lento en lugar de abortar una buena respuesta. |
| **Product Edit History** | Activado | Muestra en la página del producto las escrituras anteriores de la IA para poder restaurar un valor antiguo. Actívelo si los editores deben poder deshacer una generación. Activado añade una pestaña **History** con **Restore** al bloque del módulo en el producto. Desactivado la oculta. Las filas pasadas permanecen en History en ambos casos. |
| **Admin Top Bar CTA** | Activado | Coloca un acceso directo en la barra superior del back office que abre el generador. Actívelo en tiendas donde el personal genera textos a menudo. Desactívelo si la barra ya está saturada. Activado muestra el botón en todas las páginas del back office. Desactivado elimina solo ese botón. El menú del módulo permanece. |
| **Product edit page Form** | Activado | Muestra el panel del generador en la página de edición del producto: las pestañas **Generate**, **Simulate** y **Photos** del bloque **My AI Grok**. Actívelo para los editores del catálogo. Desactívelo si solo van a usarse la generación masiva y cron. |
| **AI Image Finder** | Activado | Permite que un editor pida al modelo páginas que probablemente contengan fotos del producto actual. Actívelo si quiere ese botón en la página del producto. Usted sigue eligiendo qué imágenes se importan. Desactivado oculta el contenido de la pestaña **Photos**. No se descarga nada hasta que alguien confirma una imagen. |
| **AI Image Search Prompt** | Pide exactamente 5 direcciones de páginas | La instrucción que se envía cuando alguien busca imágenes de producto. `{product_name}` y `{product_description}` se sustituyen por el producto actual. Mantenga la petición de una lista de direcciones de páginas. Cambie la redacción si quiere sitios de fabricantes o una cantidad distinta. Un prompt más preciso devuelve páginas más relevantes. Uno vago devuelve enlaces sin relación. No se guarda nada hasta que elija imágenes. |

El mismo interruptor **AI Image Finder** y el mismo prompt existen también en la pantalla **Images** (sección 3.14); ambos lugares cambian el mismo ajuste.

### 3.5 Settings – Grok

Abra **Settings** y después **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok: clave de API, modelo y valores de muestreo.*

Este formulario contiene la cuenta de Grok que se usa en toda generación, incluidos cron y los botones del producto. Los campos de muestreo cambian cuán variada es la redacción. No cambian qué productos se actualizan.

Mensajes que puede ver tras **Save**: **OpenAi Settings Updated** (éxito; la denominación es un resto, pero la pantalla pertenece a Grok), **Grok API KEY field is invalid!** (no hay clave guardada y la pegada tiene menos de 10 caracteres) y **OpenAi Model field is invalid!** (el nombre del modelo es demasiado corto). Una clave con espacios alrededor se limpia automáticamente y puede ver **Grok API Key has been automatically cleaned (whitespace removed).**

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Grok API KEY** | vacío | El secreto que permite a esta tienda llamar a su cuenta de Grok. Pegue la clave de https://console.x.ai. Los espacios se eliminan al guardar. Deje el campo sin tocar para conservar la clave ya guardada. Una clave válida permite las generaciones de Grok. Una clave vacía o incorrecta hace fallar esas llamadas y el error se escribe en History. |
| **Model** | grok-4.7 | El modelo de Grok que escribe el texto. Los nombres integrados son grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning y grok-4.20-0309-reasoning. Permanecen en la lista. Los nombres que añada en la fila siguiente pueden eliminarse. La siguiente generación usa ese modelo. Un modelo al que su clave no tenga acceso devuelve un error en lugar de texto. |
| **Add a Grok model** | sin modelos adicionales | Añade un identificador de modelo de Grok que no está en la lista integrada para poder seleccionarlo arriba. Escriba el identificador exacto de su cuenta de Grok (por ejemplo grok-4.6) y haga clic en **Add model**. El nuevo identificador aparece en la lista **Model** y se convierte en el modelo activo. **Remove** junto a un identificador añadido elimina solo los identificadores añadidos aquí. Los integrados no se pueden eliminar. Si elimina el modelo activo, pasa a estar activo grok-4.7. Mensajes: **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Límite máximo de la longitud de la respuesta, contado en tokens y no en palabras. Use aproximadamente 256 para una meta descripción y 1000 o más para una descripción HTML completa. Un límite bajo corta la respuesta. Uno alto permite textos más largos y cuesta más en la factura del proveedor. No cambia el prompt. |
| **Temperature** | 0.7 | Con qué libertad elige palabras el modelo. Más baja es más estable, más alta es más variada. Manténgase entre 0 y 1. Use aproximadamente 0,2 para fichas técnicas y metatextos, y 0,7 para descripciones. Cambie este valor o **Top P**, no ambos. Un valor bajo repite una estructura parecida. Uno alto produce redacciones más distintas y más riesgo de desviarse del encargo. |
| **Top P** | 1 | Otra forma de limitar lo sorprendente que puede ser la siguiente palabra. 1 considera todo el rango. Deje 1 si ya ha ajustado **Temperature**. Use un valor menor, como 0,9, solo si quiere un vocabulario más acotado. Los valores más bajos hacen las respuestas más seguras y repetitivas. |
| **Frequency Penalty Value** | 0 | Reduce las líneas que repiten la misma frase dentro de una respuesta. Use 0 salvo que las descripciones copien siempre la misma frase. Pruebe de 0,3 a 0,6. Manténgase entre -2 y 2. Un valor positivo hace menos probable la redacción repetida. No tiene en cuenta otros productos. |
| **Presence Penalty Value** | 0 | Empuja la respuesta hacia temas nuevos en lugar de quedarse en palabras ya usadas. Use 0 por defecto. Pruebe un número positivo pequeño si cada párrafo trata el mismo punto. Manténgase entre -2 y 2. Algunos modelos más recientes ignoran este campo. |

El módulo recuerda por sí solo cuáles de estos valores rechaza un modelo y deja de enviárselos, de modo que no verá un error por ello.

### 3.6 Settings – Studio

Abra **Settings** y después **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio: reglas de la casa añadidas a cada prompt.*

Studio se aplica sobre cada prompt, incluidos los botones del producto, la generación masiva y cron. Los campos vacíos se omiten. Un presupuesto de 0 significa sin límite mensual. El módulo también indica al modelo en qué idioma escribir, según el idioma del producto, la categoría o la pantalla en uso. Pulse **Save studio**; la confirmación dice **Studio settings saved.** El texto ya guardado en el catálogo no se reescribe.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Brand voice** | vacío | Dice al modelo quién habla, para que los textos de producto encajen con la tienda y no con un asistente genérico. Escriba un resumen breve, por ejemplo: taller especializado, frases cortas, sin exageraciones. Toda generación posterior parte de esta voz. Cambiarla no reescribe el texto ya guardado. |
| **Audience** | vacío | Nombra al lector para el que el modelo debe escribir. Use una frase sencilla como instaladores profesionales o compradores primerizos. Las respuestas usan un vocabulario y ejemplos dirigidos a ese lector. |
| **Tone** | vacío | Fija el ánimo de la redacción: formal, cálido, técnico, etc. Basta una o dos palabras. Déjelo vacío para que decida el prompt. No cambia el modelo ni la temperatura. |
| **Glossary** | vacío | Una lista de marcas, materiales y grafías que el modelo debe copiar exactamente. Ponga un término por línea, en la forma que quiera conservar. El texto nuevo prefiere esas grafías. Los términos que no figuren pueden reformularse. |
| **Forbidden words** | vacío | Palabras y frases que no deben aparecer en una respuesta guardada. Una palabra o frase por línea. La lista solo se comprueba cuando la **Quality gate** está activada. Una respuesta que contenga una de estas líneas se rechaza y no se escribe en el producto. El intento queda guardado de todos modos en History como error. |
| **Monthly generation budget** | 0 | Limita cuántas generaciones correctas puede ejecutar la tienda en el mes natural en curso. Introduzca un número entero. Use 0 para no tener límite. El contador vuelve a empezar el primer día del mes. Al alcanzar el límite, las nuevas generaciones se detienen con un mensaje de presupuesto hasta el mes siguiente. Las llamadas fallidas no se cuentan. Los números negativos se guardan como 0. |
| **Quality gate** | Activado | Comprueba la respuesta del modelo con la lista de prohibidas antes de guardar nada. Actívela después de rellenar **Forbidden words**. Desactívela si solo quiere guardar la lista para más adelante. Activado bloquea una respuesta que coincida. Desactivado guarda la respuesta aunque contenga una palabra de la lista. |

El presupuesto cuenta las filas de History, así que usar **Clear list** en la pantalla History hace que el recuento del mes vuelva a empezar desde cero.

### 3.7 Settings – Prompt templates

Abra **Settings** y después **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates: la lista de instrucciones guardadas.*

Una plantilla es una instrucción guardada. Los editores la eligen en lugar de volver a escribir el mismo resumen. Los marcadores de posición (placeholders) se sustituyen por el producto o la categoría para la que genera. La tienda arranca con 16 plantillas ya preparadas para nombres de producto, descripciones, meta títulos, meta descripciones y etiquetas, todas activadas.

**La lista** muestra **ID**, **Title**, **Prompt**, **Status** (haga clic en la marca o la cruz para activar o desactivar una plantilla) y **Timestamp**. Cada fila tiene **Edit** y **Delete**. Marque varias filas y use la acción masiva **Delete** (se le pregunta: **Are you sure you want to delete the selected prompts?**). El botón **Add new** sobre la lista crea una plantilla.

**El formulario** (**Generate Prompt Template**) tiene tres campos. Pulse **Save Prompt**, o **Go Back to Module Settings** para salir sin guardar. Mensajes: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Las comillas dobles escritas en el prompt se guardan como comillas simples.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Status** | Desactivado en una plantilla nueva | Muestra u oculta esta plantilla en los desplegables usados en la página del producto, en la generación masiva y en cron. Active las plantillas que el personal deba usar. Desactive un borrador en lugar de eliminarlo. Las plantillas activadas aparecen en las listas. Las desactivadas permanecen en esta tabla pero no se ofrecen. |
| **Prompt title** | vacío (obligatorio) | El nombre que ven los editores en el desplegable de plantillas. No se envía al modelo. Use una etiqueta corta como HTML description with features. |
| **Prompt content** | vacío (obligatorio) | La instrucción que se envía al modelo. Escriba el encargo como se lo diría a un redactor y mencione longitud, HTML e idioma si importan. Cuando alguien ejecuta la plantilla, los marcadores se rellenan con el elemento actual y la respuesta se escribe en el campo que haya elegido. |

**Marcadores de posición** (placeholders) que puede escribir en un prompt (se rellenan para cada producto, categoría o página cuando se ejecuta la plantilla):

| Marcador | Se sustituye por |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | Los datos propios del producto en el idioma en que se escribe. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | La marca del producto, el nombre y la descripción de su categoría por defecto y los nombres de todas sus categorías. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | Los atributos de combinación del producto, los nombres de características, los pares nombre y valor de característica y los enlaces a sus imágenes. |
| `{category_name}` `{category_description}` `{category_parent_name}` | La categoría que se escribe y el nombre de su categoría padre. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | Datos de la página de contenido o de la marca abierta cuando usa el acceso directo de la barra superior. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | Datos de toda la tienda: nombre, dominio, idioma, país por defecto y código de la moneda por defecto. |

Use solo los marcadores que tengan sentido donde se ejecutará la plantilla. Un marcador de producto en un encargo de categoría queda como texto escrito.

### 3.8 Settings – Playground

Abra **Settings** y después **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground: un bloc de notas para una instrucción libre.*

El Playground envía una instrucción libre al modelo activo e imprime la respuesta bajo el botón. Puede mencionar el nombre de la tienda, la URL de la tienda, un nombre de producto, una referencia o características del producto para que el módulo sustituya datos del catálogo. La respuesta permanece en esta página. No se guarda ningún campo de producto ni de categoría.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Instruction box** | vacío | Escriba la instrucción en lenguaje llano y pulse **Generate**. El proveedor activo recibe este texto junto con las reglas de Studio. La respuesta aparece bajo el botón con el número de tokens utilizados. El catálogo no se actualiza. |

Si pulsa **Generate** con el cuadro vacío verá **Write a prompt first.** Cada llamada se guarda en History con el tipo **general**.

### 3.9 Generate – Products

Abra **Generate** y después **Products**. También puede hacer clic en el botón **My AI Grok** que aparece junto a las acciones masivas de la lista de productos.

La generación masiva tiene dos pasos: un filtro que construye una lista y una ejecución sobre esa lista.

**Paso 1: Filter products to update.** Este paso solo construye la lista de productos. No se escribe nada en los productos hasta que elija un alcance e idiomas en la pantalla siguiente y pulse **Run**. Estos filtros no se guardan como ajustes de la tienda. Pulse **Go to next step** cuando esté listo. Deje un filtro vacío para ignorarlo.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Product Categories** | ninguna marcada | Limita la lista de productos a los que están en las categorías marcadas (o tienen una de ellas como categoría por defecto). Marque las categorías que desee. Deje el árbol vacío si la categoría no debe importar. |
| **Brand** | Select brand (no filter) | Conserva los productos de un fabricante. Elija una marca, o deje la primera opción vacía si deben incluirse todas las marcas. |
| **Product status** | Active | Conserva los productos a la venta, los desactivados o ambos. Elija **Active** para el catálogo en vivo, **Disabled** para borradores o **Both**. |
| **Product stock** | All products | Omite opcionalmente los productos sin existencias. **Only in stock products** quita de la lista los productos sin cantidad disponible. **All products** deja el stock fuera del filtro. |
| **Update only** | Update all | Usa el historial de generación para incluir los productos que este módulo nunca ha escrito (**Products that have not been updated with OpenAi content**), solo los que sí (**Products that already have been updated with OpenAi content**), o todos (**Update all**). Elija “aún no actualizados” para una primera pasada y “ya actualizados” cuando quiera reescribir. Un producto cuenta como ya actualizado cuando History contiene alguna entrada para él, incluso un intento fallido. |
| **Product IDs** | vacío | Restringe la lista a identificadores de producto concretos. Escriba los identificadores separados por comas, por ejemplo 12,45,103. |
| **Product Reference** | vacío | Restringe la lista a códigos de referencia concretos. Escriba una o más referencias separadas por comas. |
| **Product Add Date From** | vacío | La fecha de creación más temprana que puede tener un producto para ser incluido. Los productos creados antes de ese momento se excluyen. |
| **Product Add Date To** | vacío | La fecha de creación más tardía que puede tener un producto para ser incluido. Los productos creados después de ese momento se excluyen. |
| **Minimum product ID** | vacío | El identificador de producto más bajo que puede aparecer en la lista. Escriba un número entero. |
| **Maximum product ID** | vacío | El identificador de producto más alto que puede aparecer en la lista. Escriba un número entero. |
| **Product Limit** | vacío (sin límite) | Limita cuántos productos se cargan en la lista de generación. Use un número pequeño, como 20, en un catálogo grande. La pantalla siguiente nunca muestra más que esa cifra, de modo que una ejecución no pueda recorrer por accidente todo el catálogo. |

**Paso 2: Mass product generation.** La pantalla siguiente muestra una tabla con los productos coincidentes (**ID**, **Reference**, **Result**) con los controles de ejecución encima.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products: plantilla, alcance, texto existente, idiomas y la lista sobre la que se ejecuta.*

Escribe los productos filtrados uno a uno con el modelo activo. Cada producto de la tabla se actualiza en los idiomas marcados. Los productos que no estaban en el filtro no se tocan. Una fila muestra su resultado en cuanto ese producto termina.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Template** | **Choose a template** (ninguna) | Rellena el cuadro del prompt a partir de una plantilla guardada en Settings. Elija un título, o deje la primera opción y escriba su propio prompt en el cuadro de abajo. El modelo recibe el texto del cuadro con los marcadores de producto sustituidos para cada fila. El título en sí no se envía. Si el cuadro queda vacío, se usa un breve encargo ya preparado para cada campo. |
| **What to generate** | Descriptions | **Descriptions** escribe la descripción larga y la corta. **Meta title and meta description** escribe ambos campos meta. **Descriptions and meta together** escribe los cuatro. Los campos fuera de esa elección se quedan como están. Cada campo tiene su propia petición. |
| **Existing text** | Replace | **Replace** sobrescribe el campo. **Skip if filled** deja un campo rellenado y no llama al modelo para él. **Add above** y **Add below** conservan el texto antiguo y añaden el nuevo antes o después. Replace cambia el valor guardado. Skip protege los campos rellenados. Add conserva ambas versiones en el mismo campo. |
| **Languages** | está marcado el idioma de su propia sesión del back office | Marque cada idioma que desee escribir. Desmarque un idioma para no tocarlo. Cada idioma marcado se genera por separado. Los idiomas sin marcar conservan su texto actual. |
| **Run on the list below** | – | Inicia la ejecución. Una línea de estado muestra el progreso (por ejemplo 3 / 24 seguido del nombre del campo) y termina con **Finished N products.** Si no hay ningún idioma marcado verá **Select at least one language.** |

Cada fila de la columna **Result** informa de una línea por campo e idioma, por ejemplo el nombre del campo seguido de **success**, **skipped** o **error** y un mensaje breve. **skipped** con **Product skipped.** significa que el campo ya tenía texto y se eligió **Skip if filled**. Las líneas **error** llevan el motivo; el mismo fallo queda guardado en History.

Mantenga esta pestaña del navegador abierta hasta que la ejecución diga **Finished**. La ejecución la dirige la página: envía una petición cada vez, y cerrar o recargar la pestaña la detiene. Los productos ya terminados permanecen escritos. Un texto muy largo se acorta para ajustarse a los límites de PrestaShop: nombres a 128 caracteres, descripciones cortas a 800, meta títulos a 69 y meta descripciones a 159.

### 3.10 Generate – Categories

Abra **Generate** y después **Categories**. Funciona como la pantalla de productos, con menos filtros.

**Paso 1: Filter categories to update.** Este paso solo construye la lista de categorías. No se envía nada al modelo hasta que escriba un prompt en la pantalla siguiente e inicie la ejecución. Los filtros de aquí no se guardan como ajustes de la tienda. Pulse **Go to next step**.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Categories** | ninguna marcada | Elige las categorías que aparecerán en la lista del paso siguiente. Marque una o más categorías. Deje el árbol vacío para incluir todas las categorías que coincidan con el estado de abajo. |
| **Category status** | Active | Conserva las categorías activas, las desactivadas o ambas (**Active**, **Disabled**, **Both**). El paso siguiente enumera solo las categorías con ese estado. |

**Paso 2: Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories: la instrucción, el campo, el texto existente, el idioma y la lista de categorías.*

Escribe un campo para cada categoría de la lista filtrada. Cada categoría de la lista se actualiza en ese idioma. Los demás campos y los demás idiomas se quedan como están.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Instruction box** (encima de la lista de campos) | vacío | La instrucción que se envía para cada categoría. Describa el tono, la longitud y el HTML. Use `{category_name}` cuando quiera el nombre de la categoría en el encargo. Cada categoría se genera a partir de este mismo texto. Si se deja vacío se usa un breve encargo ya preparado. |
| **Field selector** | Description | El campo de categoría que escribe esta ejecución: **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. Solo se guarda ese campo. Los demás campos de categoría se quedan como están. Si su PrestaShop no tiene el campo Additional description para categorías verá **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** sobrescribe el campo. **Skip if filled** lo deja y no llama al modelo para esa categoría. |
| **Language selector** | el idioma de su back office | La versión de idioma que se escribirá. Elija un idioma. Ejecute de nuevo para otro idioma. Solo cambia ese idioma. |
| **Run on the categories below** | – | Inicia la ejecución. Los resultados aparecen por fila, como en la pantalla de productos. |

Bajo la lista, la pantalla muestra también un segundo formulario llamado **Generate category content**. Para generar, use el botón **Run on the categories below** situado encima. Ese segundo formulario solo recuerda sus opciones y le devuelve al filtro de categorías (véase la sección 5.12).

### 3.11 New product

Abra **New product**. Esta pantalla convierte un breve resumen en un borrador de producto y puede insertar ese borrador en el catálogo.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product: resumen, página de origen opcional, idioma y categoría por defecto.*

**Generate data** muestra el borrador y no guarda un producto. **Create product** añade un producto activo en ese idioma y categoría, copia del borrador el nombre, las descripciones, los metadatos, las etiquetas, las características, el precio y la referencia, le da un stock inicial de 100 unidades y lo coloca en la categoría elegida.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **What is the product?** | vacío | El resumen que el modelo amplía en un nombre, descripciones, metadatos, etiquetas, características, referencia y precio. Describa el producto en unas pocas frases. Mencione materiales, público y nombres que deban conservarse. Un resumen más rico produce un borrador más ajustado. Un cuadro vacío se rechaza con **Prompt is required**. |
| **Optional source URL** | vacío | Añade al resumen texto leído de una página pública para que el borrador pueda seguir una página de producto existente. Pegue una dirección web completa, o déjelo vacío. Una página legible se añade como contexto adicional. Una página que la tienda no pueda leer se ignora y se usa solo el resumen. |
| **Language** | el idioma por defecto de la tienda | El idioma de la tienda en el que se guarda el texto del nuevo producto. Esta pantalla no rellena los demás idiomas. El nombre, las descripciones, los metadatos y las etiquetas se guardan solo en ese idioma. |
| **Default category ID** | 2 | El identificador de categoría que se asigna como categoría por defecto del producto. Escriba el identificador numérico de **Catalog**, **Categories**. 2 suele ser Home. El nuevo producto se coloca en esa categoría. |
| **Generate data** | – | Pide el borrador al modelo y lo imprime como texto estructurado bajo los botones. Si la respuesta no puede leerse verá **Failed to parse AI response. Please try again.** |
| **Create product** | – | Inserta el borrador. Si tiene éxito, el cuadro muestra **Product #** seguido del identificador del nuevo producto. Pulsarlo antes de generar muestra **Generate the product first.** |

El producto se crea sin fotos, con la primera regla de impuestos de la tienda y un precio tomado del borrador; ábralo después para comprobar el precio, el impuesto, las fotos y el stock. Si no hay una clave de API guardada, la pantalla muestra **Add an API key in the module settings first.**

### 3.12 Cron

Abra **Cron**. Esta pantalla construye direcciones que su servidor llama de forma programada para rellenar campos de productos o categorías en pequeños lotes. Nada se ejecuta por sí solo. La tienda no hace nada hasta que el servidor solicita la dirección.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron: el panel de la dirección de categorías, y después el formulario de productos con su dirección e interruptores.*

**Qué contiene la pantalla, de arriba abajo:** un panel **Category cron** con la dirección de categorías; el formulario **CRON JOB Settings – Generate product content using Grok**; el formulario **CRON JOB Settings - Generate category content using Grok**; y un panel **Cron parameters** con la dirección de productos, el campo elegido, el objetivo y el tamaño del lote.

**Importante:** las direcciones que muestra esta pantalla terminan en el secreto. Para que la llamada haga algún trabajo debe añadir la acción a la dirección. Las formas completas de la dirección están en la sección 4.2. Además, **Enable Cron Feature** debe estar en **Yes**; de lo contrario, toda llamada de cron, para productos y para categorías, responde que la función está desactivada.

**Formulario de productos** (pulse **Save** al final del formulario):

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Enable Cron Feature** | No | Permite que el servidor genere texto de forma programada, sin que un empleado vaya haciendo clic por el catálogo. Actívelo solo después de guardar el secreto, el campo, el idioma y el prompt de abajo. El servidor sigue teniendo que llamar a la dirección. Activado hace que la dirección guardada haga el trabajo. Este interruptor condiciona también la dirección de categorías. |
| **Cron Job Secret Token** | un valor aleatorio largo creado en la instalación | Una contraseña larga que debe estar presente en la dirección de productos. Sin ella, la tienda rechaza la llamada. Conserve el valor generado. Si lo sustituye, copie la nueva dirección en el programador del servidor. Quien no conozca este secreto no puede ejecutar el cron de productos. Cambiarlo invalida de inmediato la dirección antigua. Use al menos 24 caracteres (véase la sección 5.10). |
| **Update Field** | description | El único campo de producto que reescribe este comando de cron: **name**, **description**, **description_short**, **meta_title**, **meta_description** o **tags**. Para rellenar la descripción y los metadatos, cree dos comandos de cron con dos campos distintos. Cada ejecución escribe solo ese campo en el idioma elegido abajo. |
| **Selected Products** | pendingGrok | Decide qué productos siguen esperando. **pendingGrok** toma los productos que este módulo nunca ha escrito correctamente en ningún campo. **pendingField** toma los productos aún no escritos para este campo concreto, de modo que pueda ejecutar varios trabajos de cron (por ejemplo descripción y nombre) sobre los mismos productos. **emptyField** toma solo los productos cuyo campo elegido está vacío en el idioma elegido. Cada ejecución omite los productos que ya no coinciden, así que un catálogo terminado deja de cambiar. Los intentos fallidos anteriores no cuentan como escritos y se reintentan. |
| **Product Categories** | ninguna marcada | Limita el cron a los productos que están en las categorías marcadas. Marque una o más categorías. Deje el árbol vacío para ignorar la categoría y usar solo los demás filtros. Consulte la sección 5.10 antes de marcar categorías. |
| **Product ID list** | vacío | Restringe la ejecución a una lista explícita de identificadores de producto. Escriba los identificadores separados por comas, por ejemplo 12,45,103. Las letras y otros caracteres se descartan al guardar. Solo esos productos pueden actualizarse con este comando. |
| **Language** | el idioma por defecto de la tienda en el momento de la instalación | La versión de idioma del campo de producto que escribe este cron. Elija un idioma de la tienda. Los demás idiomas necesitan su propio comando de cron. |
| **Product to update** | 5 products | Cuántos productos coincidentes se procesan cada vez que se llama a la dirección (de 2 a 1000). Empiece con 5 o 10 para que un modelo lento no alcance el límite de tiempo del servidor. Súbalo cuando una ejecución termine sin problemas. |
| **Prompt Template** | ninguna seleccionada | La instrucción guardada que se envía al modelo para cada producto de esta ejecución. Elija una plantilla activada de Settings. Los marcadores de esa plantilla se rellenan por producto. Elija una plantilla antes de la primera llamada. Cambiar la plantilla más tarde solo afecta a la ejecución siguiente. |
| **Enable Debug** | No | Muestra lo que haría el cron cuando abre la dirección en un navegador, sin guardar productos. Actívelo mientras comprueba el comando. Desactívelo antes de que el programador del servidor use la misma dirección. Activado imprime el plan y no escribe texto en el catálogo. |
| **CRON JOB interval** | Every Hour | El ritmo que piensa usar en el servidor (de **Every 1 Minute** a **Every 6 Hours**). Ajústelo al programador que vaya a crear. El módulo no inicia el programador por sí mismo y no impone este valor. |
| **Product Cron Job command** | – | Muestra la dirección base. Cópiela, añada la acción como se describe en la sección 4.2 y pegue el resultado en el programador de su servidor. Puede crear tantos comandos de cron como quiera. |

**El formulario de categorías** tiene la misma lógica con su propio secreto y su propio lote:

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Cron Job Secret Token** | un valor aleatorio largo creado en la instalación | Una contraseña larga que debe estar presente en la dirección de categorías. Es independiente del secreto de productos. Conserve el valor generado. Las llamadas sin este secreto se rechazan. Cambiarlo invalida de inmediato la dirección antigua de categorías. |
| **Update Field** | description | El único campo de categoría que reescribe este comando: **name**, **description**, **meta_title** o **meta_description**. El nombre, la descripción y los metadatos necesitan cada uno su propio comando si quiere rellenarlos todos. |
| **Selected categories** | pendingGrok | Las mismas tres opciones que para productos (**pendingGrok**, **pendingField**, **emptyField**), aplicadas a categorías. Cada ejecución omite las categorías que ya no coinciden. |
| **Language** | el idioma por defecto de la tienda en el momento de la instalación | La versión de idioma del campo de categoría que escribe este cron. Los demás idiomas necesitan su propio comando. |
| **Categories to update** | 5 categories | Cuántas categorías coincidentes se procesan cada vez que se llama a la dirección. Empiece con 5 o 10. |
| **Prompt Template** | ninguna seleccionada | La instrucción guardada que se envía al modelo para cada categoría de esta ejecución. Escriba el encargo para una categoría, no para un producto (por ejemplo con `{category_name}`). |
| **Enable Debug** | No | Muestra lo que haría el cron de categorías cuando abre la dirección en un navegador, sin guardar categorías. Desactívelo antes de que el programador use la dirección. |
| **CRON JOB interval** | Every Hour | El ritmo que piensa usar en el servidor. Es solo un recordatorio. |
| **Category Cron Job command** | – | Muestra la dirección base que debe copiar. Añada la acción como se describe en la sección 4.2. |

El cron de categorías nunca toca la propia categoría raíz (home).

### 3.13 History

Abra **History**. Esta pantalla es un informe de cada llamada a Grok y funciona como su registro de auditoría.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History: filtros, totales, tablas de desglose y la lista de llamadas.*

Acote las tarjetas, las tablas de desglose y la lista del historial a un fragmento de generaciones. Haga clic en un intervalo de fechas predefinido o establezca **From** y **To**. Después, si lo desea, limite por modelo, tipo, estado, idioma, empleado, un identificador de producto o categoría, o una palabra que deba aparecer en el prompt o en la respuesta. Pulse **Filter**. Solo quedan visibles las filas coincidentes. El historial guardado no se borra y no se cambia ningún producto.

| Control | Tras instalar | Qué hace |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | del primer día del mes a hoy | Un intervalo de fechas personalizado. |
| **Model** | Any | Solo las llamadas hechas con ese modelo. |
| **Type** | Any | Solo ese tipo de llamada (véase la tabla de abajo). |
| **Status** | Any | **Success** o **Error**. |
| **Language** | Any | Solo las llamadas de ese idioma. |
| **Employee** | Any | Solo las llamadas iniciadas por ese empleado. Las llamadas iniciadas por cron no tienen empleado. |
| **Product / category ID** | vacío | Solo las filas de ese identificador (un producto, categoría, página de contenido o marca con ese número). |
| **Prompt or reply contains** | vacío | Solo las filas en las que el prompt, la respuesta o el texto del error contienen la palabra. |
| **Filter** | – | Aplica los filtros. |

**Tarjetas:** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** y **Average time**. Un guion significa que Grok no devolvió un recuento de tokens para esa llamada.

**Tablas de desglose:** **By day**, **By model**, **By type**, **By language**, **By employee**, cada una con **Group**, **Calls**, **Sent**, **Received** y **Total**. Un número pequeño junto a Calls es el número de errores de ese grupo.

**La lista** se titula **Prompt history** y muestra 50 filas por página con las columnas **ID**, **Status** (una insignia verde **Success** o una roja **Error**), **Prompt**, **Reply / Error**, **Provider** (servicio, modelo y tiempo empleado, más un código de estado de Grok cuando lo hay), **Sent**, **Received**, **Total**, **Entity ID**, **Type** y **Timestamp**. La acción de fila **View** abre el prompt y la respuesta completos con los tokens, y **Back to the list** vuelve. Si la fila se eliminó entretanto, verá **This log entry no longer exists.**

| Valor de tipo | Significado |
|---|---|
| **general** | Una instrucción libre del Playground o del acceso directo de la barra superior. |
| **singleCategory**, **singleCMS**, **singleBrand** | El acceso directo de la barra superior se usó mientras estaba abierta una categoría, una página de contenido o una marca. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | Un campo de producto se escribió (o se intentó) mediante un botón, una ejecución masiva o cron. |
| **product_seo_pack** | El paquete SEO escribió nombre, descripciones y metadatos de una vez. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | Se escribió un campo de categoría. |
| **error** | Una llamada de producto fallida. |

El botón de la barra de herramientas **Clear list** borra definitivamente todas las filas de History y lo confirma con **Log list successfully deleted.** Eso también elimina los puntos de restauración de las páginas de producto y reinicia el recuento del presupuesto mensual, así que úselo con cuidado.

### 3.14 Images

Abra **Images**. Esta pantalla activa o desactiva la búsqueda de imágenes en la página del producto y guarda la instrucción que se envía al modelo.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images: el interruptor AI Image Finder y su prompt.*

Estos dos campos controlan la búsqueda de imágenes en la página del producto. Guardarlos no descarga imágenes ni cambia el texto de los productos. Pulse **Save**; la confirmación dice **Settings saved.**

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **AI Image Finder** | Activado | Muestra u oculta la búsqueda de imágenes en la página de edición del producto. Actívelo cuando los editores deban buscar fotos del producto actual. Desactívelo para quitar ese botón. Activado muestra la búsqueda. Desactivado la oculta. Una imagen solo se importa después de que alguien la confirme. |
| **AI Image Search Prompt** | Pide exactamente 5 direcciones de páginas | La instrucción que se envía cuando alguien busca imágenes de producto. Los marcadores del nombre y de la descripción del producto se sustituyen por el producto actual. Mantenga la petición de una lista de direcciones de páginas (la pantalla lo llama una matriz JSON de URL de páginas). Cambie la redacción si quiere sitios de fabricantes o un número distinto de enlaces. Un prompt más preciso devuelve páginas más relevantes. Uno vago devuelve enlaces sin relación. No se guarda nada hasta que un editor elige una imagen. |

### 3.15 Updates

Abra **Updates** (en el extremo derecho de la barra).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates: comprobación manual, notificaciones automáticas y el enlace a la página del producto.*

La pantalla se titula **MyPresta Updates**. Consulta en MyPresta.eu si hay una versión más reciente del módulo y puede avisarle en el back office. El catálogo y los textos generados se quedan como están.

| Campo | Tras instalar | Qué hace |
|---|---|---|
| **Manual Check** | – | Contacta una vez con los servidores de actualización de MyPresta.eu y compara la versión remota con la de esta tienda. Haga clic en **Check Now** después de instalar o cuando sospeche que hay una versión nueva. Junto al botón aparece **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Activado | Comprueba periódicamente (aproximadamente cada 3 días) si hay actualizaciones en el back office. Establézcalo en **Enabled** para recibir un aviso cuando exista una versión más reciente. Los empleados verán entonces una notificación con un enlace a más detalles. Establézcalo en **Disabled** si gestiona las actualizaciones solo de forma manual. Guarde con **Save**; la confirmación es **Update settings saved.** |
| **Product Page** | enlace | Abre en una pestaña nueva la página oficial de producto de MyPresta para este módulo. |

### 3.16 Trabajar en la página de edición del producto

Abra un producto (**Catalog**, **Products**, el producto), después la pestaña **Modules** y a continuación **My AI Grok**. El bloque tiene hasta cuatro pestañas: **Generate**, **Simulate**, **Photos** y **History**. Las pestañas que vea dependen de **Product edit page Form** y **Product Edit History** en la sección 3.4. El producto debe haberse guardado al menos una vez.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Página de edición del producto, pestaña Generate: chips de idioma, comportamiento del texto existente y una tarjeta por campo.*

**Pestaña Generate.** Cada botón escribe un campo del producto y el texto se guarda en el producto de inmediato.

- **Language:** un chip por cada idioma activo, más **Every language**, que ejecuta cada idioma uno tras otro.
- **If the field already has text:** **Replace**, **Add above**, **Add below** o **Skip if filled**. Se comportan como se describe en la sección 3.9.
- **Tarjetas de campo:** **Description** (texto largo con una breve introducción y una lista de características), **Short description** (un resumen corto y sencillo, de menos de unos 400 caracteres), **Name**, **Meta title** (unos 70 caracteres), **Meta description** (unos 160 caracteres) y **Tags** (una lista separada por comas). Pulse **Fill** en la tarjeta.
- **SEO pack:** **Fill all** rellena el nombre, ambas descripciones y ambos campos meta en una sola petición. Solo está disponible en la pestaña Generate. Después, actualice la página del producto para ver los nuevos valores.
- **Use your own instruction or a saved prompt:** abra esta sección para filtrar sus plantillas guardadas por título o texto, elegir una (el primer mosaico **Standard brief** usa un encargo ya preparado para el campo que pulse) o escribir su propio texto en **Instruction**. Déjelo vacío para usar el encargo estándar. Si ninguna plantilla coincide con el filtro verá **No prompt matches that filter.**
- El resultado también se imprime en un panel bajo las tarjetas, con el número de tokens.

Tras un **Fill**, recargue la página del producto para ver el nuevo texto en el formulario.

**Pestaña Simulate.** Pruebe primero un campo. La respuesta permanece en esta página y el producto no se modifica. Tiene los mismos chips de idioma y tarjetas de campo, pero cada tarjeta tiene **Try** en lugar de **Fill**. Cada Try sigue creando una fila en History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Pestaña Simulate: **Try** muestra la respuesta sin guardar.*

**Pestaña Photos.** Cuando **AI Image Finder** está activado, Grok busca fotos de este producto.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Pestaña Photos: buscar páginas, marcar fotos, añadirlas al producto.*

1. Pulse **Find pages**. Grok sugiere páginas web y el módulo lee fotos de hasta cinco de ellas (hasta 24 fotos).
2. Marque las fotos que desee.
3. Pulse **Add selected to this product**. Las fotos se descargan y se adjuntan; la primera foto que marcó pasa a ser la portada. No se guarda nada antes de este paso.

Las direcciones de redes privadas nunca se abren. Si el buscador está desactivado, la pestaña indica que debe activar **AI Image Finder** en Settings, General, y abrir de nuevo el producto.

**Pestaña History.** Enumera las escrituras anteriores de este producto con **When**, **Type**, **Status** y un botón **Restore**. **Restore** pregunta **Restore the previous value?** y, una vez confirmado, recupera el texto anterior y le indica que actualice la página. La History de toda la tienda no se borra. **Restore** solo se ofrece para filas correctas que guardaron un valor anterior. La pestaña muestra **No generations for this product yet.** cuando la lista está vacía.

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*Pestaña History: escrituras anteriores con un botón Restore.*

### 3.17 Otros lugares donde aparece el módulo

- **Botones Generate with AI junto a los campos.** En el formulario de edición del producto aparece un pequeño botón junto a la descripción, la descripción corta, el meta título y la meta descripción de cada idioma. En el formulario de edición de la categoría aparece junto a la descripción, la descripción adicional, el meta título y la meta descripción. Haga clic en él. Si la tienda tiene más de un idioma, se le pide elegir **Current language**, **All languages** o **Cancel**. El texto se coloca en el campo del formulario. Guarde el producto o la categoría para conservarlo. Se usa un encargo ya preparado para ese campo y sus reglas de Studio siguen aplicándose. Si el elemento nunca se guardó verá **Save the product once before generating.** (o **Save the category once before generating.**). El interruptor **Product edit page Form** oculta solo el bloque del módulo en la pestaña **Modules**; no elimina estos pequeños botones.
- **Acceso directo de la barra superior.** Con **Admin Top Bar CTA** activado, un icono de varita mágica en la barra superior abre una ventana pequeña: elija un **Template** (opcional), escriba la instrucción y pulse **Generate**. Cuando está en la pantalla de edición de una categoría, página de contenido o marca, se rellenan los marcadores correspondientes. La respuesta se muestra en la ventana y no se guarda nada.
- **Lista de productos.** Un botón **My AI Grok** junto a las acciones masivas abre **Generate**, **Products**.

## 4. Front de la tienda

El módulo no tiene ninguna pantalla de cara al cliente. No muestra nada en la cabecera, el pie ni en ninguna página de producto, categoría o pedido, y el tema no tiene nada que mostrar ni que sobrescribir. Los clientes nunca ven ninguna herramienta de generación de texto; solo ven el texto que usted ya ha guardado en el catálogo.

### 4.1 Direcciones que usa el propio módulo

Dos direcciones web de su tienda pertenecen al módulo. La primera nunca la abre usted mismo.

- La **dirección del generador** la llaman los botones dentro del back office (Fill, Try, Run, Playground, etc.). Está protegida por un secreto integrado en las páginas del back office.
- La **dirección de cron** la llama el programador de su servidor, o usted en un navegador mientras prueba. Se describe a continuación.

### 4.2 Dirección de cron

La dirección tiene la forma de la dirección de su tienda, seguida de la ruta del módulo, el secreto y la acción. Sustituya los marcadores por sus propios valores. Use el secreto que ve en la pantalla **Cron** y no lo publique nunca.

Para productos:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

Para categorías:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

La dirección que muestra la pantalla Cron termina después del secreto (el panel de categorías añade un final distinto que la tienda no usa). Añada usted mismo la parte `action`. Sin acción, la tienda responde **Invalid action!**

El lote usa las opciones guardadas en la pantalla Cron: campo, regla de selección, idioma, plantilla, tamaño del lote y depuración. Cada llamada actualiza un lote y después se detiene. Cada escritura correcta aparece también en History con el método **cron**.

Para programarlo en un servidor Linux, cree una tarea cron que recupere la dirección, por ejemplo cada diez minutos:

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Mantenga la dirección entre comillas, porque contiene un ampersand. En Windows use el Programador de tareas con una tarea que abra la dirección. Para probar, cambie **Enable Debug** a **Yes**, guarde y abra la dirección en un navegador: la página imprime el plan (los parámetros, los productos o categorías seleccionados y la instrucción final) y no guarda nada. No comparta esa salida, porque contiene los parámetros de su dirección. Vuelva a poner la depuración en **No** antes de que el programador use la dirección.

### 4.3 Qué responde la dirección de cron

| Lo que ve | Qué hacer |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Ponga **Enable Cron Feature** en **Yes** en la pantalla Cron y guarde. |
| **The token does not exist or it's wrong!** | Falta el secreto o no coincide. Vuelva a copiar el secreto desde la pantalla Cron. |
| **Invalid action!** | Falta la parte `action` o está mal escrita. Use una de las dos formas de la sección 4.2. |
| **All must include all mandatory parameters!** | Un valor como el campo, el objetivo, el tamaño del lote, el idioma o la plantilla está vacío. Abra la pantalla Cron, rellénelo y guarde. |
| **No valid product IDs provided.** | La Product ID list no contiene ningún número utilizable. Corrija o vacíe la lista y guarde. |
| **No products to update.** o **No categories to update.** | Ya nada coincide con la regla. Es el final normal de un trabajo terminado. Cambie la regla de selección o los filtros para procesar más. |
| **N products have been updated.** o **N categories have been updated.** | El lote ha terminado. El programador tomará el siguiente lote en su próxima llamada. |
| **Error!** seguido de un mensaje (por ejemplo **Monthly generation budget reached.** o **Reply rejected by the studio quality gate.**) | Lea el mensaje y siga el capítulo 5. La ejecución se detiene en el primer error. |
| **Error! The model returned an empty response.** | Suba **Max Tokens** en Settings, Grok, o pruebe otro modelo. |
| **Error! Could not save product** seguido de un identificador | No se pudo guardar el producto con el nuevo texto, por ejemplo porque PrestaShop rechazó el texto. Revise ese producto y ejecute de nuevo. |

## 5. Problemas

### 5.1 La instalación se rechaza

- **Síntoma:** **This module requires PHP 7.0.0 or newer. This server is running PHP** seguido de su versión, o **Could not create the module database tables.**
- **Causa:** el PHP del servidor es demasiado antiguo, o el usuario de la base de datos no puede crear tablas.
- **Qué hacer:** pida a su proveedor de alojamiento que cambie a PHP 7.0 o superior, o que dé al usuario de la base de datos permiso para crear tablas, e instale de nuevo.

### 5.2 Falta la entrada del menú o el bloque del producto

- **Síntoma:** no aparece **AI Content Generator** bajo **Modules**, o no aparece el bloque **My AI Grok** en la pestaña **Modules** del producto.
- **Causa:** una caché obsoleta, falta de permisos del perfil de su empleado o un interruptor desactivado.
- **Qué hacer:** vacíe la caché en **Advanced Parameters**, **Performance**. En **Advanced Parameters**, **Team**, **Permissions** compruebe que su perfil puede abrir las pantallas del módulo. Si el menú sigue sin aparecer, desinstale e instale de nuevo el módulo. Para el bloque del producto, compruebe **Product edit page Form** y **Product Edit History** en Settings, General, y guarde el producto una vez para que tenga un identificador.

### 5.3 La clave se rechaza o falta

- **Síntoma:** **Grok API KEY field is invalid!** al guardar, o **The Grok API key is not set. Add it in the module settings.** al generar, o una fila de error en History tras cada intento.
- **Causa:** el campo de la clave está vacío o es demasiado corto, o la clave se copió con una errata o se ha revocado en xAI.
- **Qué hacer:** abra **Settings**, **Grok**, pegue una clave nueva de https://console.x.ai y pulse **Save**. Después abra **History**, filtre **Status** por **Error** y abra la fila más reciente para leer la respuesta exacta de Grok.

### 5.4 El modelo se rechaza

- **Síntoma:** **OpenAi Model field is invalid!**, o errores en History que dicen que el modelo no existe o que no tiene acceso.
- **Causa:** el nombre del modelo es demasiado corto, está mal escrito o su cuenta de xAI no puede llamar a ese modelo.
- **Qué hacer:** en **Settings**, **Grok** elija uno de los modelos integrados, o añada el identificador exacto de su cuenta de xAI con **Add model**, y guarde.

### 5.5 La llamada supera el tiempo de espera

- **Síntoma:** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** o, en una pantalla, **The request timed out or the shop blocked it.**
- **Causa:** un modelo lento, una respuesta muy larga, un servicio de xAI saturado o un servidor que bloquea peticiones largas.
- **Qué hacer:** suba **API timeout (seconds)** en **Settings**, **General** (hasta 600), baje **Max Tokens** para los campos cortos o pruebe un modelo más rápido. Para cron, baje **Product to update** para que un lote quepa en el límite de tiempo del servidor.

### 5.6 La respuesta está vacía o cortada

- **Síntoma:** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** o **The response was blocked by the provider content filter. Try rewording the prompt.** o **The model returned an empty response.**
- **Qué hacer:** suba **Max Tokens** en **Settings**, **Grok**. Si la respuesta fue bloqueada, reformule la instrucción. Después, inténtelo de nuevo.

### 5.7 Se ha alcanzado el presupuesto mensual

- **Síntoma:** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **Qué hacer:** abra **Settings**, **Studio**, suba **Monthly generation budget** o póngalo en 0, y guarde. Las llamadas fallidas no se cuentan.

### 5.8 Una respuesta se rechaza por una palabra prohibida

- **Síntoma:** **The reply was rejected because it contains a forbidden word from the studio settings.** (cron muestra **Reply rejected by the studio quality gate.**). El producto queda sin cambios y History muestra una fila de error.
- **Qué hacer:** ejecute de nuevo la generación (la redacción difiere cada vez), acorte **Forbidden words** en **Settings**, **Studio**, o ponga **Quality gate** en **Disabled**.

### 5.9 Se omite un campo o el texto es incorrecto

- **Síntoma:** una fila dice **skipped** con **Product skipped.** (o **Category skipped.**), o el texto se añadió al antiguo en lugar de sustituirlo.
- **Causa:** **Existing text** estaba en **Skip if filled**, **Add above** o **Add below**.
- **Qué hacer:** elija **Replace** y ejecute de nuevo. Para deshacer una escritura no deseada en un producto, use la pestaña **History** del producto y pulse **Restore**.

### 5.10 Cron no hace nada, se repite o la dirección deja de funcionar

- **Síntoma:** el programador se ejecuta pero no se escribe nada, o se reescriben los mismos productos, o una dirección que ayer funcionaba ahora responde **The token does not exist or it's wrong!**
- **Cron desactivado:** **Cron Job feature is disabled.** Ponga **Enable Cron Feature** en **Yes** en la pantalla Cron y guarde.
- **Sin acción en la dirección:** obtiene **Invalid action!** Añada la acción como se muestra en la sección 4.2.
- **Depuración activada:** la depuración imprime el plan y nunca guarda. Ponga **Enable Debug** en **No** y guarde.
- **Sin plantilla:** si **Prompt Template** está vacío, la instrucción enviada está vacía. Elija una plantilla activada y guarde.
- **Secreto sustituido:** el botón **Generate Token** junto al secreto no tiene función en esta versión, así que escriba o pegue usted mismo un secreto aleatorio largo. Un secreto de menos de 24 caracteres se sustituye por uno aleatorio nuevo la próxima vez que se abra cualquier página del back office, y la dirección antigua deja de funcionar. Vuelva a copiar el secreto desde la pantalla Cron.
- **Los mismos productos una y otra vez:** cuando marca **Product Categories**, los productos cuya categoría por defecto está marcada se seleccionan en cada llamada, incluso si la regla de selección dice que ya no están pendientes. Deje el árbol de categorías vacío y limite el cron con **Product ID list**, o use la pantalla **Generate** para el trabajo limitado por categorías.
- **Errores del servidor:** los errores de cron se imprimen solo en la respuesta de la dirección; no se guardan en History. Ejecute la dirección en un navegador con la depuración activada para leerlos.

### 5.11 Una ejecución masiva se detiene a medias

- **Síntoma:** la línea de estado deja de moverse, o algunas filas no tienen resultado.
- **Causa:** se cerró o recargó la pestaña del navegador, el ordenador entró en suspensión o una llamada superó el tiempo de espera.
- **Qué hacer:** pulse **Run** de nuevo. Elija **Skip if filled** en **Existing text** para no pagar dos veces por los campos terminados. Las filas con un error indican el motivo; el mismo motivo está en History.

### 5.12 El formulario Generate category content no hace nada

- **Síntoma:** tras pulsar **Generate content** en el formulario bajo la lista de categorías, llega al filtro de categorías y no se escribe nada.
- **Qué hacer:** use el botón **Run on the categories below** situado encima de ese formulario. En las pantallas de filtros de productos y categorías, el botón **Module settings** no abre los ajustes de este módulo; use el elemento **Settings** de la barra de navegación.

### 5.13 Problemas con las fotos del producto (Photos)

- **Síntoma:** **Find pages** no muestra fotos, o ve **No images could be imported.** seguido de detalles.
- **Causa:** Grok sugirió páginas sin fotos utilizables, la página bloqueó la descarga de la tienda, la dirección apuntaba a una red privada o el archivo no era una imagen válida.
- **Qué hacer:** pulse **Find pages** de nuevo, reformule **AI Image Search Prompt** en la pantalla **Images** (por ejemplo pidiendo sitios de fabricantes) o suba las fotos a mano.

### 5.14 La pantalla New product falla

- **Síntoma:** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** o **Failed to create product**.
- **Qué hacer:** guarde la clave de API en **Settings**, **Grok**, escriba un resumen y pulse **Generate data** de nuevo. Suba **Max Tokens** si la respuesta parece cortada. Si **Create product** falla, compruebe si el borrador tiene el nombre vacío.

### 5.15 No es posible restaurar

- **Síntoma:** **Error! This log entry has no previous value to restore.** o **Error! Nothing to restore for this entry.**
- **Causa:** esa fila no guardó un valor anterior (por ejemplo un prompt libre, o un campo que estaba vacío).
- **Qué hacer:** use otra fila del mismo producto, o corrija el texto a mano.

### 5.16 La pantalla dice que el token no es válido

- **Síntoma:** **Error! Invalid token!** al pulsar un botón tras una pausa larga.
- **Causa:** la página del back office se abrió antes de que se renovara el secreto interno del módulo.
- **Qué hacer:** recargue la página e inténtelo de nuevo.

### 5.17 El texto es más corto de lo esperado

- **Causa:** PrestaShop limita algunos campos. El módulo acorta un nombre a 128 caracteres, una descripción corta a 800, un meta título a 69 y una meta descripción a 159.
- **Qué hacer:** use una instrucción más concisa, por ejemplo pidiendo un título de menos de 60 caracteres.

### 5.18 Registro técnico y depuración

- **Síntoma:** necesita más detalles sobre una llamada fallida, o el registro de PrestaShop crece.
- **Qué hacer:** active **Debug mode** en **Settings**, **General**, repita la acción, lea las nuevas entradas en **Advanced Parameters**, **Logs** y vuelva a desactivar la depuración. Ponga también **Enable Debug** de la pantalla Cron de nuevo en **No** tras las pruebas.

### 5.19 Notificaciones de actualización

- **Síntoma:** **Check Now** no muestra **Module is up to date!** ni **New version available!**
- **Causa:** su servidor no puede alcanzar el servidor de actualizaciones de MyPresta.eu, que se consulta con un límite de tiempo corto.
- **Qué hacer:** permita las conexiones salientes o inténtelo más tarde. El módulo funciona sin esta comprobación.

## 6. Para desarrolladores

### 6.1 Resumen

- **Clase principal:** `myaigrok` (archivo `myaigrok.php`), extiende `Module`, versión `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Nombre en la lista de módulos:** `My AI Grok - AI content generation`. **Autor:** `MyPresta.eu`. **Tab:** `front_office_features`.
- **Compatibilidad:** PrestaShop 1.6 hasta 9.99.99 (`ps_versions_compliancy`). PHP mínimo 7.0.0 (`MIN_PHP_VERSION`); `install()` rechaza un PHP más antiguo con un mensaje traducido.
- **Clases:** el espacio de nombres `MyAIGrok\` lo carga `autoload.php` (sin Composer). `MyAIGrok\OpenAIService` es un cliente cURL para `https://api.x.ai/v1` (`/chat/completions`, `/models`); `MyAIGrok\Studio` aplica el estilo de la casa, el presupuesto mensual y la puerta de calidad. El comprobador de actualizaciones `myaigrokUpdate` (en `lib/updateChecker.php`) extiende `myaigrok`.
- **Flujo de datos:** los ajustes viven en `ps_configuration` (prefijo `MYPRESTA_MYAIGROK_`). Los botones del back office y las ejecuciones masivas llaman al controlador front `ajax`; los programadores llaman al controlador front `cron`. Ambos leen los ajustes, pasan el prompt por `Studio::gate()` (comprobación del presupuesto y `Studio::decorate()`), lo envían con `OpenAIService::createChatCompletion()`, comprueban la respuesta con `Studio::inspect()`, escriben el texto en el objeto de producto o categoría e insertan una fila en `myaigrok_log`.
- **Llamadas al proveedor:** se envían los parámetros de modelo `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty`; los parámetros que un modelo rechaza se aprenden y se guardan en `MYPRESTA_MYAIGROK_MODEL_CAPS`. La verificación de certificados solo se desactiva cuando la propia tienda funciona en localhost.

### 6.2 Archivos

| Ruta | Finalidad |
|---|---|
| `myaigrok.php` | Clase del módulo: instalación, desinstalación, hooks, pantallas de Settings (HelperForm), Dashboard, colocación del menú, pestaña Modules del producto. |
| `autoload.php` | Cargador de clases para el espacio de nombres `MyAIGrok\`. |
| `src/OpenAIService.php` | Cliente cURL para Grok: chat completions, lista de modelos, tiempos de espera, adaptación de parámetros. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, prompts del paquete SEO y de los textos alt. |
| `controllers/admin/AdminMyAIGrok.php` | Pantallas Generate (filtros de productos y categorías, paneles masivos). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | Pantalla New product y sus acciones Ajax. |
| `controllers/admin/AdminMyAIGrokCron.php` | Formularios de Cron. |
| `controllers/admin/AdminMyAIGrokUsage.php` | Informe y lista de History. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Pantalla Images y acciones de búsqueda e importación de imágenes. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Redirigen a la página de configuración del módulo. |
| `controllers/front/ajax.php` | Punto final de generación usado por el back office. |
| `controllers/front/cron.php` | Punto final de cron. |
| `lib/sectionHelp.php` | Contenido del panel lateral Help. |
| `lib/updateChecker.php` | Comprobación de actualizaciones de MyPresta.eu (`dev.mypresta.eu/update/get.php`; envía el nombre del módulo, la versión, un marcador de la clave de licencia y la dirección de la tienda). |
| `lib/prestashop9compatibility.php` | Ayudas de compatibilidad (cifrado de tokens para PS 9). |
| `lib/searchTool/` | Pequeña ayuda de autocompletado cargada en la página de configuración. |
| `views/templates/hook/*.tpl` | Plantillas de hooks y pantallas (nav, subnav, dashboard, usage, generadores masivos, playground, pestañas de producto, paneles de cron). |
| `views/templates/admin/product_creator.tpl` | Pantalla New product. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Scripts del back office. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Estilos del back office. |
| `translations/{iso}.php` | Archivos de traducción (muchos idiomas). |

### 6.3 Controladores

| Controlador | Padre y ruta | Notas |
|---|---|---|
| `AdminMyAIGrokMain` | Hijo de la pestaña padre Modules (`AdminParentModulesSf`, si no `AdminParentModules`, si no `AdminModules`), nombre de menú **AI Content Generator** | Redirige a `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Hijo oculto (`active = 0`) de Main | Redirige a `mds_tab=settings`. |
| `AdminMyAIGrok` | Hijo oculto de Main | `mds_sub=products` o `categories`; acciones de envío `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Hijo oculto de Main | Acciones Ajax `generateProductData`, `extractImages`, `createProduct`, `generateImages` (marcador). |
| `AdminMyAIGrokCron` | Hijo oculto de Main | Envío `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Hijo oculto de Main | Filtros `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`; `clear_log` borra todas las filas; acción de fila `view`. |
| `AdminMyAIGrokImageFinder` | Hijo oculto de Main | Acciones `searchImages`, `extractImages`, `saveImages`; hosts de redes privadas rechazados; hasta 5 páginas y 24 fotos. |

Los permisos son los derechos estándar de pestaña del back office de estos controladores. Todo controlador de administración redirige a `AdminHome` cuando el módulo está desactivado. `AdminModules` con `configure=myaigrok` acepta `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` es la pestaña Grok) y `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) además de `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`): requiere `secret_token` igual a `MYPRESTA_MYAIGROK_TOKEN`; de lo contrario, `Error! Invalid token!`. No hay comprobación de empleado; el token de la página es la única protección. Acciones: `initiatePrompt`, `updateSettings` (escribe las claves de muestreo), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (sin botón en la interfaz). `updateProduct` y `updateCategory` aceptan los valores de `behavior` `replace`, `keep`, `keep_top`, `keep_end` y `single_product` / `single_category` (simulación, no se guarda nada).

**Front `cron`** (`module/myaigrok/cron`): el constructor hace todo el trabajo. Termina con un mensaje cuando `ENABLE_CRON` es 0 y después requiere `secret` igual a `MYPRESTA_MYAIGROK_SECRET` o a `MYPRESTA_MYAIGROK_CAT_SECRET` (cualquiera de los dos secretos se acepta para cualquiera de las dos acciones). `action` debe ser `generateProductContent` o `generateCategoryContent`; de lo contrario, `Invalid action!`. El parámetro `entity` que se muestra en la dirección de categorías de la pantalla Cron no se lee. Los parámetros opcionales sobrescriben las opciones guardadas: para productos `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`; para categorías `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Objetivos permitidos: `pendingGrok`, `pendingField`, `emptyField`; un valor incorrecto responde `productTarget parameter is wrong! Allowed values: ...`, un campo incorrecto `updatedField parameter is wrong!`. La condición de la lista de categorías para productos se añade como `p.id_product IN (...) OR p.id_category_default IN (...)` sin paréntesis, por lo que se combina con las demás condiciones según la precedencia de SQL (véase la sección 5.10). Los errores de cron se imprimen (echo) y la petición termina; no se escriben en `myaigrok_log`.

Recursos referenciados pero no incluidos en el paquete: `views/js/admin.js` y `views/css/admin.css` (controladores Main y Settings, inalcanzables porque antes redirigen) y `views/js/product_creator.js` y `views/css/product_creator.css` (pantalla New product; la pantalla usa `back.js`). Las funciones `generateTokenAndFill()` y `generateCategoryTokenAndFill()` que llaman los botones **Generate Token** no están definidas en ningún script incluido. Los botones **Module settings** de los formularios de filtro de Generate enlazan a `configure=mychatgpt`.

### 6.4 Hooks

Registrados en `install()`:

| Hook | Comportamiento |
|---|---|
| `displayAdminProductsExtra` | Renderiza el bloque My AI Grok (`product-tab-wrapper.tpl`) en la pestaña Modules del producto. No devuelve nada cuando tanto `PRODUCT` como `PRODUCT_LOG` son 0. |
| `displayBackOfficeHeader` | Llama a `ensureLongSecrets()` y `placeModuleMenu()`, añade CSS y JS, publica variables JS, registra una sola vez la pestaña Image Finder (`IMAGEFINDER_TAB_OK`), carga `product-fields.js` en las páginas de producto y categoría y el script del botón de la lista de productos. |
| `displayBackOfficeTop` | Publica `admin_controller_url` y los identificadores de la categoría, página CMS o marca que se está editando, y devuelve el generador de la barra superior cuando `TOPCTA` es 1. |
| `dashboardZoneTwo` | Renderiza `dashboard.tpl`. Se vuelve a registrar en `displayBackOfficeHeader` si falta. |
| `displayHeader`, `displayFooter` | Registrados; los métodos están vacíos. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Registrados; los métodos devuelven una cadena vacía o nada. |

El módulo no sobrescribe ni `enable()` ni `disable()`. Desactivar el módulo solo hace que sus controladores de administración redirijan al panel de PrestaShop. El método `hookActionProductGridDataModifier` existe pero no está registrado. El módulo no expone hooks propios.

### 6.5 Overrides

El módulo no tiene overrides.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Se rellena con 16 plantillas en la instalación. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pares `old_` y `new_` para name, description, description_short, meta_title, meta_description y tags, `date_updated`. Claves sobre `id_product` y `status`. |

Las tres columnas de tokens las añade `ensureUsageColumns()` en el primer uso cuando una tabla antigua no las tiene. La desinstalación elimina ambas tablas, todas las pestañas de administración (incluida la antigua `AdminMyAIGrokChangelog`) y las claves principales de configuración. El texto generado de productos y categorías no se toca.

### 6.7 Claves y traducciones

Todas las claves empiezan por `MYPRESTA_MYAIGROK_`. Valores tras la instalación:

| Clave | Valor |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (limitado a 10–600 al guardar) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 cada una |
| `IMAGEFINDER_PROMPT` | Prompt por defecto que pide 5 URL de páginas como matriz JSON |
| `TOKEN`, `SECRET`, `CAT_SECRET` | 32 caracteres aleatorios; `ensureLongSecrets()` regenera cualquiera de menos de 24 caracteres |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | un solo espacio, `grok-4.7`, vacío, vacío |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vacío |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, vacío, idioma por defecto de la tienda, vacío, 0, vacío, vacío |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, vacío, idioma por defecto de la tienda, 0 |
| `IMAGEFINDER_TAB_OK` | Se establece tras la primera carga del back office |

Las pantallas Generate también guardan sus últimos valores de filtro bajo `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. La desinstalación no las elimina. El comprobador de actualizaciones usa `mypresta_updates`, `update_myaigrok` y `updatev_myaigrok`. Cada carga de la página de configuración en el back office elimina las claves obsoletas `GEMINI_API_KEY`, `GEMINI_MODEL` y `ACTIVE_SERVICE`.

**Traducciones:** para añadir un idioma, cree `translations/{iso}.php`. Las cadenas del módulo usan `$this->l()` y `{l s='...' mod='myaigrok'}`. Los controladores de administración usan `trans()` con dominios como `Admin.MyAIGrok` y `Admin.MyAIGrokCron` en PrestaShop 8 y 9, y el `l()` del módulo en 1.6 y 1.7. Estas cadenas no están traducidas: los mensajes construidos en `back.js` y los textos de reserva de `product-fields.js`, las respuestas de texto plano de cron, los textos de error de Image Finder y New product, y los prompts en inglés construidos por `Studio`. Las descripciones de los campos (What it does / How to configure / Effect) las construye `fieldHelp()` en `myaigrok.php` y el contenedor `help()` de cada controlador de administración; los textos del generador masivo y del Playground están en las plantillas; los textos del panel Help están en `lib/sectionHelp.php`.

### 6.8 Ampliar

- Añada o edite plantillas de prompt en `myaigrok_prompt` (o en la pantalla Prompt templates); los marcadores se sustituyen en `ajax.php` y `cron.php`.
- Añada identificadores de modelo con **Add a Grok model**; se guardan en `EXTRA_MODELS`.
- Dé forma a la salida con las reglas de Studio; se aplican en `Studio::decorate()`.
- Llame al punto final de cron con sobrescrituras de parámetros para ejecutar trabajos distintos sin tocar el formulario guardado.
- El front office no renderiza ninguna plantilla del módulo, por lo que el tema no tiene nada que sobrescribir.

## 7. Ayuda

Página de producto del módulo: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

Para contactar con el soporte sobre el módulo:

1. Inicie sesión en su cuenta de cliente en mypresta.eu.
2. Vaya al formulario de contacto.
3. Elija el tema **Support for paid modules**.
4. Describa lo que hizo y lo que vio. Añada el número de versión que aparece junto al nombre del módulo en la parte superior de sus pantallas y, si una generación falló, el texto del error de la columna **Reply / Error** de **History**.
