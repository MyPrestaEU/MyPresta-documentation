---
title: "My AI DeepSeek - AI content generation - documentación y manual de usuario"
description: "Manual de configuración, uso diario y resolución de problemas para los propietarios de tiendas que ya tienen instalado el módulo My AI DeepSeek en PrestaShop."
sidebar:
  label: "My AI DeepSeek - AI content generation - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo SEO meta and catalog descriptions with DeepSeek AI en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Requisitos

El módulo escribe los textos del catálogo a través del servicio DeepSeek, por lo que su tienda necesita una conexión operativa con DeepSeek y su propia cuenta de DeepSeek.

- **PrestaShop:** versiones de la 1.6 a la 9.99.99.
- **PHP:** 7.0 o superior. En una versión de PHP anterior, la instalación se rechaza con un mensaje que indica la versión requerida y la detectada.
- **Extensión de PHP:** cURL. El servidor de la tienda debe poder abrir conexiones HTTPS salientes hacia `https://api.deepseek.com/v1`. Si su hosting bloquea las conexiones salientes, pídale que las permita.
- **Otros módulos:** ninguno. El módulo no depende de ningún otro módulo.
- **Cuenta de DeepSeek:** necesita una clave de API. Créela en https://platform.deepseek.com/api_keys. El uso lo factura DeepSeek a su cuenta, no MyPresta.eu.
- **Idioma del back office:** en este manual las pantallas se muestran en inglés y las capturas proceden del back office en inglés. Los nombres en negrita son los nombres que ve en pantalla.
- **Catálogos grandes:** cada campo generado es una solicitud a DeepSeek y tarda unos segundos. Un proceso sobre cientos de productos tarda mucho, y la pestaña del navegador debe permanecer abierta durante todo el proceso en las pantallas Generate. Para catálogos grandes prefiera la pantalla Cron, que trabaja en segundo plano en lotes pequeños.

## 2. Instalación

### 2.1 Subir e instalar

1. Abra **Modules**, luego **Module Manager**.
2. Haga clic en **Upload a module** y seleccione el archivo ZIP. No lo descomprima antes.
3. Cuando termine la subida, haga clic en **Install** (si se muestra el botón) y después en **Configure**.

La instalación guarda los ajustes predeterminados, crea las tablas del módulo, añade 16 plantillas de prompt ya preparadas y agrega el módulo al menú del back office.

### 2.2 Qué aparece en el menú

Se añade una nueva entrada de menú **AI Content Generator**. Su primera página es **Dashboard**. Dentro del módulo se mueve entre pantallas con la barra de navegación situada en la parte superior de cada página:

| Elemento de navegación | Qué abre |
|---|---|
| **Dashboard** | Gráficos de solicitudes, errores y tokens. |
| **Settings** | Cinco secciones: **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Dos listas: **Products** y **Categories**. |
| **New product** | Crea un borrador de producto a partir de una breve descripción. |
| **Cron** | Genera direcciones de tareas programadas para productos y categorías. |
| **History** | Cada solicitud con su prompt, respuesta, estado y tokens. |
| **Images** | Interruptor y prompt de la búsqueda de fotos de producto. |
| **Updates** | Comprueba si hay publicada una versión más reciente. |

Al pasar el ratón por un elemento de navegación se muestra una breve pista con la forma What it does / How to configure / Effect.

### 2.3 Caché

La instalación no vacía la caché de PrestaShop. Si tras la primera instalación falta la entrada **AI Content Generator** en el menú, vacíe la caché en **Advanced Parameters**, **Performance** y vuelva a cargar el back office.

### 2.4 Desinstalación y reinstalación

- **Se elimina:** la entrada de menú, la lista de plantillas de prompt, la tabla History con todas sus filas y los ajustes principales del módulo, incluida la clave de API.
- **Se conserva:** todo texto ya escrito en productos y categorías. El módulo nunca elimina textos del catálogo.
- **Posibles restos:** pueden quedar en la configuración de la tienda algunos valores de filtro guardados de las pantallas Generate. No causan ningún problema.
- **Reinstalación:** una instalación nueva parte de los valores predeterminados. Las plantillas de prompt, History y la clave de API desaparecen, así que anote sus propias plantillas y sus reglas de Studio antes de desinstalar.

## 3. Configuración y trabajo diario en el back office

### 3.1 Todo el proceso de un vistazo

El módulo no tiene pasos del lado del cliente. Sus empleados inician cada acción en el back office.

1. **Una vez:** pegue la clave de API de DeepSeek y elija un modelo en **Settings**, **DeepSeek**. Opcionalmente rellene **Studio** (voz de marca, palabras prohibidas, límite mensual).
2. **Un solo producto:** abra un producto, vaya a la pestaña **Modules**, **My AI DeepSeek**. Use **Generate** para escribir campos, **Simulate** para probar primero, **Photos** para encontrar imágenes y **History** para restaurar un texto anterior.
3. **Muchos productos o categorías:** abra **Generate**, filtre la lista, elija un prompt y un alcance y pulse **Run**. Cada fila muestra su propio resultado cuando termina.
4. **Sin supervisión:** abra **Cron**, guarde una definición de lote, copie la dirección y entréguela al programador de tareas del servidor.
5. **Control:** **History** muestra cada solicitud. **Dashboard** muestra los totales. Nada se pierde: el texto anterior de cada campo escrito se conserva para **Restore** en el producto.
6. **Producto nuevo a partir de una idea:** **New product** crea un borrador y, cuando usted lo acepta, un producto real.

Cada solicitud se guarda en **History** con su estado **Success** o **Error**. Una respuesta que infringe la lista **Forbidden words**, o que llega después de agotarse el **Monthly generation budget**, no se escribe en el producto.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Abra **AI Content Generator**, luego **Dashboard**. La página representa en gráficos las solicitudes a DeepSeek, los tokens y los errores guardados en **History** para el rango que elija. Desde esta página no se genera ni se cambia nada en el catálogo.

| Elemento | Valor inicial | Qué hace |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | el módulo se abre con un rango predeterminado | Rangos de fechas rápidos. Haga clic en uno para redibujar la página. |
| **From** / **To** y **Apply** | vacío | Su propio rango. Las tarjetas y los gráficos lo siguen. |
| Línea **Active service** | – | Muestra qué servicio utiliza el módulo. |
| Tarjetas **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Número de llamadas guardadas, de llamadas fallidas, tamaño de los prompts y tamaño de las respuestas dentro del rango. |
| Gráficos **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Curvas día a día y un desglose por modelo. |

La página aparece también como un pequeño bloque en el **Dashboard** estándar de PrestaShop, con accesos rápidos a **Generate**, **History** y **Cron**.

### 3.3 Settings – General

Abra **Settings**, luego **General**. Estos interruptores deciden cuánto puede durar una llamada y qué herramientas ven los empleados. Guardar aquí no cambia ningún texto de producto.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Live mode** | Disabled | Marca el módulo como en funcionamiento en la tienda real y no en una configuración de prueba. Actívelo en la tienda de producción. En una copia de staging déjelo desactivado si no quiere que el personal considere las herramientas listas. Las herramientas funcionan igual en ambos estados. |
| **Debug mode** | Disabled | Escribe detalles de diagnóstico adicionales cuando falla una llamada a DeepSeek. Actívelo solo mientras investiga un error y luego desactívelo. Los mensajes técnicos van al registro de PrestaShop. Los clientes nunca los ven. |
| **API timeout (seconds)** | 120 | Cuántos segundos puede durar una llamada a DeepSeek antes de que el módulo se rinda. Use 120 para descripciones normales. Súbalo hacia 600 para paquetes SEO largos o para el modelo de razonamiento. No baje de 10. Un tiempo de espera corto falla rápido y escribe un error en History. Un tiempo de espera largo espera una respuesta lenta. |
| **Product Edit History** | Enabled | Muestra en la página del producto las escrituras anteriores de la IA para que un editor pueda recuperar un valor antiguo. Desactivado oculta esa lista. Las filas pasadas permanecen en **History** en ambos casos. |
| **Admin Top Bar CTA** | Enabled | Añade un acceso directo en la barra superior del back office que abre el generador en cualquier página. Desactivado elimina solo ese botón. El menú del módulo permanece. |
| **Product edit page Form** | Enabled | Muestra el panel del generador y los botones Generate with AI en la página de edición de producto (PrestaShop 1.7, 8 y 9). Desactívelo si solo se van a usar la generación masiva y cron. |
| **AI Image Finder** | Enabled | Permite a un editor pedir al modelo páginas que probablemente contengan fotos del producto actual. No se descarga nada hasta que alguien confirma una imagen. Desactivado oculta la búsqueda, y la pestaña **Photos** explica entonces cómo activarla. |
| **AI Image Search Prompt** | instrucción en inglés ya preparada | La instrucción que se envía cuando alguien busca imágenes de producto. El nombre y la descripción del producto se rellenan para el producto actual. Mantenga la petición de una lista de direcciones de páginas. Un prompt más preciso da páginas más relevantes. |

Pulse **Save**. Aparece una confirmación en verde. Los mismos dos campos de imagen existen en **Images**.

### 3.4 Settings – DeepSeek

Abra **Settings**, luego **DeepSeek**. Esta es la cuenta y el muestreo que usa cada generación: los botones del producto, las ejecuciones masivas, cron y el playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **DeepSeek API KEY** | vacío | El secreto que permite a esta tienda llamar a su cuenta de DeepSeek. Pegue la clave de https://platform.deepseek.com/api_keys. Los espacios se eliminan al guardar (verá un aviso de que la clave se ha limpiado). Deje el campo sin tocar para conservar la clave guardada. Una clave vacía o incorrecta hace que las llamadas fallen y el error se escribe en History. |
| **Model** | `deepseek-chat` | El modelo que escribe el texto. Modelos integrados: `deepseek-chat` (rápido, la opción normal) y `deepseek-reasoner` (modelo de razonamiento, más lento). También se muestran los modelos que usted añada. La siguiente generación usa el modelo seleccionado. Un modelo que su clave no puede utilizar devuelve un error de API en lugar de texto. |
| **Add a DeepSeek model** | fila vacía | Escriba un id de modelo y pulse el botón de añadir de esta fila. Verá **Model added.** Los modelos integrados no se pueden eliminar (**Built-in models cannot be removed.**). Un modelo que ya está integrado responde **That model is already built in.** Los modelos que usted añadió se pueden eliminar desde la misma fila (**Model removed.**). |
| **Max Tokens** | 3200 | Límite superior de la longitud de la respuesta, contado en tokens y no en palabras. Use unos 256 para una meta descripción y 1000 o más para una descripción HTML completa. Un límite bajo corta la respuesta. Un límite alto permite un texto más largo y cuesta más. Con `deepseek-reasoner` parte del límite se gasta en razonamiento, así que dele un valor mayor. |
| **Temperature** | 0.7 | Con cuánta libertad elige palabras el modelo. Manténgase entre 0 y 1. Use unos 0.2 para especificaciones y textos meta y unos 0.7 para descripciones. Cambie Temperature o Top P, no ambos. |
| **Top P** | 1 | Otra manera de limitar lo sorprendente que puede ser la siguiente palabra. Deje 1 si ya ha fijado Temperature. Un valor menor, como 0.9, da un vocabulario más acotado. |
| **Frequency Penalty Value** | 0 | Reduce las líneas que repiten la misma frase dentro de una respuesta. Pruebe de 0.3 a 0.6 solo si las descripciones siguen copiando una misma frase. Rango –2 a 2. |
| **Presence Penalty Value** | 0 | Empuja la respuesta hacia temas nuevos. Use 0 por defecto. Un número positivo pequeño ayuda cuando cada párrafo repite el mismo punto. Rango –2 a 2. |

Pulse **Save**. Los campos de muestreo no cambian qué productos se actualizan.

> El modelo de razonamiento puede ignorar Temperature, Top P y las dos penalizaciones. Si un cambio en estos campos no tiene efecto visible con `deepseek-reasoner`, cambie a `deepseek-chat`.

### 3.5 Settings – Studio

Abra **Settings**, luego **Studio**. Studio añade sus reglas de la casa sobre cada prompt: los botones del producto, las ejecuciones masivas y cron. Los campos vacíos se omiten. El texto ya guardado en el catálogo no se reescribe cuando cambia una regla.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Brand voice** | vacío | Indica al modelo quién habla, de modo que el texto del producto encaje con su tienda y no con un asistente genérico. Escriba una breve descripción, por ejemplo: taller especializado, frases cortas, sin exageraciones. |
| **Audience** | vacío | Nombra al lector para el que se escribe el texto, por ejemplo instaladores profesionales o compradores primerizos. |
| **Tone** | vacío | Fija el ambiente: formal, cálido, técnico, etcétera. Basta con una o dos palabras. No cambia el modelo ni la temperatura. |
| **Glossary** | vacío | Nombres de marca, materiales y grafías que el modelo debe copiar exactamente. Un término por línea. Los términos que no figuren pueden seguir reformulándose. |
| **Forbidden words** | vacío | Palabras y frases que no deben aparecer en una respuesta guardada. Una por línea. Solo se usa cuando **Quality gate** está activado. Una respuesta que contenga una línea de la lista se rechaza y no se escribe en el producto. El intento queda en History como error. |
| **Monthly generation budget** | 0 | Limita cuántas generaciones correctas puede ejecutar la tienda en el mes natural en curso. Introduzca un número entero. 0 significa sin límite. El contador vuelve a empezar el primer día del mes. Tras alcanzar el límite verá **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Las llamadas fallidas no se cuentan. |
| **Quality gate** | Enabled | Comprueba la respuesta del modelo con **Forbidden words** antes de guardar nada. Activado bloquea una respuesta coincidente. Desactivado la guarda aunque contenga una palabra de la lista. |

Pulse **Save studio**. Verá **Studio settings saved.**

### 3.6 Settings – Prompt templates

Abra **Settings**, luego **Prompt templates**. Una plantilla es una instrucción guardada. Los editores la eligen en lugar de escribir de nuevo la misma descripción. Solo se ofrecen las plantillas activadas en la página del producto, en la generación masiva y en cron.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

La instalación añade **16 plantillas**: Product name 1 y 2; Product description 1 a 7 (la número 7 usa las imágenes del producto); Product meta title 1 a 3; Product meta description 1 a 3; Product tags.

**Columnas de la lista:** ID, **Title**, **Prompt**, **Status** (haga clic en la marca para alternar Enabled/Disabled), **Timestamp**. Acciones de fila: **Edit** y **Delete**. Acción en bloque: **Delete** para las filas marcadas (confirmación: *Are you sure you want to delete the selected prompts?*).

Use el botón **+** de la cabecera de la lista para crear una plantilla. El formulario **Generate Prompt Template** tiene estos campos:

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Status** | interruptor Enabled / Disabled | Muestra u oculta la plantilla en las listas usadas en la página del producto, en la generación masiva y en cron. Desactive un borrador en lugar de borrarlo. |
| **Prompt title** | vacío (obligatorio) | El nombre que los editores ven en la lista de plantillas, por ejemplo HTML description with features. No se envía al modelo. |
| **Prompt content** | vacío (obligatorio) | La instrucción que se envía al modelo. Escríbala como si diera instrucciones a un redactor e indique longitud, HTML e idioma si importan. Puede usar los marcadores `{product_name}`, `{product_brand}`, `{product_features}` y `{product_tags}`. Se sustituyen por el producto para el que genera. |

Pulse **Save Prompt**. Mensajes: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Si el formulario está incompleto verá **Failed to edit prompt template! Please fill the form with the right informations!** El botón **Go Back to Module Settings** vuelve a la lista.

Escriba las plantillas de categoría sin marcadores de producto. Las pantallas de categorías no los insertan.

### 3.7 Settings – Playground

Abra **Settings**, luego **Playground**. Es un bloc de pruebas que llama al modelo activo e imprime la respuesta bajo el botón. No se cambia ningún producto, categoría ni campo meta.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| Cuadro de texto grande (**Ask the model anything about your catalog**) | vacío | La instrucción para esta única llamada. Escríbala en lenguaje sencillo. Puede mencionar el nombre de la tienda, la dirección de la tienda, el nombre de un producto, una referencia o características del producto si quiere que la respuesta se base en datos del catálogo. Sus reglas de Studio también se añaden. |
| **Generate** | – | Envía la instrucción. La respuesta aparece debajo del botón. |

### 3.8 Generate – Products

Abra **Generate**, luego **Products**. Es una pantalla de dos pasos. El primer paso solo construye una lista. No se envía nada a DeepSeek hasta que pulse **Run** en el segundo paso.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Paso 1 – Filter products to update.** Los filtros no se guardan como ajustes de la tienda. Los filtros vacíos no restringen la lista.

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Product Categories** | ninguna marcada | Conserva los productos de las categorías marcadas. Un árbol vacío deja este filtro desactivado. |
| **Brand** | primera opción (vacía) | Conserva los productos de un fabricante. |
| **Product status** | – | **Active** (a la venta), **Disabled** (borradores) o **Both**. |
| **Product stock** | – | **Only in stock products** elimina los productos sin cantidad. **All products** ignora el stock. |
| **Update only** | – | Usa el historial de generación: productos nunca escritos por este módulo, productos ya escritos o **Update all**. Use "not yet updated" para una primera pasada y "already updated" para reescribir. |
| **Product IDs** | vacío | Números de producto separados por comas, por ejemplo 12,45,103. |
| **Product Reference** | vacío | Uno o varios códigos de referencia separados por comas. |
| **Product Add Date From** / **Product Add Date To** | vacío | Rango de fechas de creación. Vacío significa sin límite en ese lado. |
| **Minimum product ID** / **Maximum product ID** | vacío | Número de producto más bajo y más alto que se incluirá. |
| **Product Limit** | vacío | Limita cuántos productos se cargan en la lista. Use un número pequeño como 20 en un catálogo grande para que una ejecución no recorra por accidente todo el catálogo. |

Pulse **Go to next step**. El botón **Module settings** vuelve a los ajustes del módulo.

**Paso 2 – Run.** Verá **Mass product generation** con la tabla de los productos filtrados (columnas **ID**, **Reference**, **Result**).

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Template** | **Choose a template** | Rellena el cuadro de prompt desde una plantilla activada. Deje la primera opción y escriba su propio prompt si lo prefiere. El título en sí no se envía. |
| Cuadro de prompt | vacío | El texto que se envía para cada fila. Los marcadores de producto se sustituyen por fila. |
| **What to generate** | **Descriptions** | **Descriptions** escribe la descripción larga y la corta. **Meta title and meta description** escribe ambos campos meta. **Descriptions and meta together** escribe los cuatro. Cada campo es una solicitud independiente. Los demás campos permanecen como están. |
| **Existing text** | **Replace** | **Replace** sobrescribe. **Skip if filled** conserva los campos rellenos y no llama a DeepSeek para ellos. **Add above** y **Add below** conservan el texto antiguo y añaden el nuevo. |
| **Languages** | el idioma de su back office, marcado | Marque todos los idiomas que quiera. Los idiomas sin marcar conservan su texto. Cada idioma marcado se genera por separado. |
| **Run on the list below** | – | Inicia la ejecución. Cada fila muestra su resultado en cuanto termina ese producto. Los productos fuera del filtro no se tocan. |

Mantenga abierta la pestaña del navegador hasta que cada fila muestre un resultado. Una fila fallida muestra el motivo; las demás filas continúan.

### 3.9 Generate – Categories

Abra **Generate**, luego **Categories**. Funciona como la pantalla de productos, con menos filtros.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Paso 1 – Filter categories to update.**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Categories** | ninguna marcada | Las categorías ofrecidas en la lista. Deje el árbol vacío para incluir todas las categorías que coincidan con el estado. |
| **Category status** | – | **Active**, **Disabled** o **Both**. |

Pulse **Go to next step**.

**Paso 2 – Mass category generation.**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| Cuadro de prompt | vacío | La instrucción que se envía para cada categoría. Describa el tono, la longitud y el HTML. Los marcadores de producto no están disponibles aquí. |
| Selector de campo | **Description** | El único campo que escribe esta ejecución: **Description**, **Name**, **Meta title**, **Meta description** o **Additional description**. |
| Existing data | **Replace** | **Replace** sobrescribe. **Skip if filled** protege los campos rellenos y no llama a DeepSeek para esa categoría. |
| **Language** | el idioma de su back office | Un idioma por ejecución. Ejecute de nuevo para otro idioma. |
| **Run on the categories below** | – | Inicia la ejecución. La tabla muestra **ID** y **Result** por categoría. |

### 3.10 New product

Abra **New product**. Convierte una breve descripción en un borrador de producto y puede insertar ese producto en el catálogo.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **What is the product?** | vacío | La descripción que el modelo desarrolla en nombre, descripciones, campos meta, etiquetas, características, referencia y precio. Unas pocas frases con materiales, público y nombres que mantener dan un borrador más ajustado. Un cuadro vacío se rechaza. |
| **Optional source URL** | vacío | Una página pública (http o https) que describe el producto. Su texto se añade como contexto. Un cuadro vacío, o una página que la tienda no puede leer, se ignora. |
| **Language** | el idioma de su back office | El idioma en el que se guardan nombre, descripciones, meta y etiquetas. Los demás idiomas no se rellenan aquí. |
| **Default category ID** | 2 | El número de la categoría de **Catalog**, **Categories**. 2 suele ser Home. El producto nuevo se coloca allí. |
| **Generate data** | – | Muestra el borrador como texto. No se guarda ningún producto. |
| **Create product** | – | Añade un producto **activo** en ese idioma y categoría con nombre, descripciones, meta, etiquetas, características, precio y una cantidad de stock del borrador. |

Si no hay clave guardada verá **Add an API key in the module settings first.** Revise el borrador, el precio y el stock antes de vender: el borrador lo escribe un modelo.

### 3.11 Cron

Abra **Cron**. La página genera direcciones a las que llama el programador del servidor. Cada llamada rellena **un lote** y se detiene. La tienda no hace nada hasta que su servidor solicita la dirección.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

La página tiene dos formularios: **CRON JOB Settings – Generate product content using DeepSeek** y el formulario equivalente para categorías. Puede crear variantes de comando ilimitadas, una por campo.

**Formulario de cron de productos**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Enable Cron Feature** | No | Un interruptor para toda la tienda (productos y categorías). Actívelo solo después de guardar el secreto, el campo, el idioma y el prompt de abajo. El servidor sigue teniendo que llamar a la dirección. |
| **Cron Job Secret Token** | generado | Una contraseña larga que debe formar parte de la dirección de productos. Sin ella la tienda rechaza la llamada. Conserve el valor mostrado tras la instalación. Si lo sustituye, copie de inmediato la nueva dirección en el programador del servidor. El botón **Generate Token** del formulario puede no rellenar un valor nuevo; escriba usted mismo una cadena aleatoria larga si necesita rotarlo. |
| **Update Field** | description | El único campo de producto que reescribe este comando: name, description, short description, meta title, meta description o tags. Para rellenar varios campos cree varios comandos. |
| **Selected Products** | pendingDeepSeek | Qué productos siguen esperando. **pendingDeepSeek**: productos nunca editados por este módulo (cualquier campo). **pendingField**: productos para los que aún no se ha generado este campo, para varios comandos sobre los mismos productos. **emptyField**: solo productos cuyo campo está vacío. |
| **Product Categories** | ninguna marcada | Limita la ejecución a las categorías marcadas. Vacío significa que la categoría no es un filtro. |
| **Product ID list** | vacío | Solo estos números de producto, separados por comas. Las letras se descartan al guardar. |
| **Language** | idioma predeterminado de la tienda | Un idioma por comando. Otros idiomas necesitan su propio comando. |
| **Product to update** | 5 products | Tamaño del lote por llamada, de 2 a 1000. Empiece con 5 o 10 para que un modelo lento no alcance el límite de tiempo del servidor. |
| **Prompt Template** | none | Una plantilla activada. Cada producto de la ejecución se escribe a partir de esa descripción. |
| **Enable Debug** | No | **Yes** imprime el plan cuando abre la dirección en un navegador y no guarda nada. Ponga **No** antes de que el programador la use. |
| **CRON JOB interval** | Every Hour | Solo una sugerencia que se usa para construir el texto del comando (de **Every 1 Minute** a **Every 6 Hours**). El módulo no inicia un programador. |
| **Product Cron Job command** | – | El comando terminado para copiar. Guarde primero el formulario. |

El **formulario de cron de categorías** tiene su propio **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (las mismas tres reglas), **Language**, **Categories to update** (tamaño del lote), **Prompt Template** (escriba la descripción para una categoría), **Enable Debug**, **CRON JOB interval** y **Category Cron Job command**. Valores predeterminados: description, pendingDeepSeek, 5 categories, Every Hour.

**Complete la dirección.** La dirección mostrada en la página puede estar incompleta. Compruebe siempre que la dirección final contiene la acción. Use esta forma, sustituyendo los marcadores:

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Use `&action=generateProductContent` para productos y `&action=generateCategoryContent` para categorías. Sin ella la llamada no hace nada. Si su tienda no usa URL amigables, copie la dirección base de la página y añada las partes con `&`. No publique estas direcciones: el secreto que contienen es la única protección.

Primera prueba recomendada: ponga **Enable Debug** en **Yes**, abra la dirección en su navegador y lea el plan. Después póngalo en **No**, programe la dirección y revise **History** tras la primera llamada.

### 3.12 History

Abra **History**. Lista cada prompt, respuesta, estado y recuento de tokens. La página es un informe: filtrarla no borra filas ni cambia productos.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Elemento | Qué hace |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Rangos de fecha predefinidos. |
| **From** / **To** | Rango de fechas propio. |
| **Model**, **Type**, **Status** (**Success** o **Error**), **Language**, **Employee** | Acotan la página a un subconjunto. |
| **Product / category ID** | Solo las solicitudes de ese elemento. |
| **Prompt or reply contains** | Una palabra que debe aparecer en el prompt o en la respuesta. |
| **Filter** | Aplica los filtros. |
| Tarjetas **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Totales de las filas filtradas. Un guion significa que DeepSeek no devolvió un recuento de tokens para esa llamada. |
| Grupos **By day**, **By model**, **By type**, **By language**, **By employee** | Tablas de desglose. |
| Columnas de la lista **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | Una fila por solicitud. Abra una fila para leer el prompt y la respuesta completos y los tokens. **Back to the list** vuelve. |
| **Clear list** | Borra las filas del historial. Verá **Log list successfully deleted.** Los puntos **Restore** de la página del producto desaparecen con ellas. El texto del catálogo no cambia. |

### 3.13 Images

Abra **Images**. Guarda el interruptor y la instrucción de la búsqueda de fotos de producto. Abrir esta página no descarga nada.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **AI Image Finder** | Enabled | Muestra u oculta la búsqueda de fotos en la página de edición de producto. Una imagen solo se importa después de que alguien la confirme. |
| **AI Image Search Prompt** | instrucción en inglés ya preparada | La instrucción que se envía cuando alguien busca. El nombre del producto y la descripción corta se rellenan. Mantenga la petición de una lista simple de direcciones de páginas. |

Pulse **Save**. Son los mismos dos ajustes que en **Settings**, **General**.

### 3.14 Updates

Abra **Updates**. Pregunta a MyPresta.eu si hay publicada una versión más reciente de este módulo.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Elemento | Valor inicial | Qué hace |
|---|---|---|
| **Automatic Notifications** | sigue el ajuste guardado | Permite que el back office le avise cuando existe una versión más reciente. |
| **Check Now** | – | Pregunta una vez, de inmediato. La página indica entonces que esta copia está al día o que existe una versión más reciente. |
| Enlace a la página del módulo | – | Abre la página del módulo en MyPresta.eu. |

Esta página no toca su catálogo ni los textos generados.

### 3.15 La página de edición de producto

Abra **Catalog**, luego **Products**, edite un producto y abra la pestaña **Modules**, luego **My AI DeepSeek**. Según su versión de PrestaShop y los ajustes de **General**, es posible que vea también pequeños botones **Generate with AI** junto a la descripción, la descripción corta y los campos meta.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

La pestaña tiene cuatro partes: **Generate**, **Simulate**, **Photos** y **History**. Si **Product edit page Form** está desactivado solo queda **History** (cuando **Product Edit History** está activado).

**Generate** – cada botón escribe un campo y guarda el texto en el producto.

| Control | Qué hace |
|---|---|
| Botones **Language** | Eligen un idioma de la tienda. **Every language** escribe todos. |
| **If the field already has text** | **Replace** (predeterminado), **Add above**, **Add below** o **Skip if filled**. |
| **Description** | El texto largo, con una breve introducción y una lista de características. |
| **Short description** | Un resumen breve y sencillo, de menos de unos 400 caracteres. |
| **Name** | El título del producto que ven los clientes. |
| **Meta title** | El título en los resultados de búsqueda, unos 70 caracteres. |
| **Meta description** | El texto en los resultados de búsqueda, unos 160 caracteres. |
| **Tags** | Una lista de palabras separadas por comas. |
| **SEO pack** – **Fill all** | Escribe el nombre, ambas descripciones y ambos campos meta de una vez. Si la respuesta no se puede usar verá **The model did not return a usable SEO pack.** |
| **Fill** | Aparece en cada tarjeta de campo: genera y guarda ese campo. |
| **Use your own instruction or a saved prompt** | Abre un cuadro de filtro, mosaicos con las plantillas activadas (**Standard brief** es la predeterminada) y un cuadro **Instruction**. Deje el cuadro vacío para usar la descripción estándar del campo que pulsa. |

**Simulate** – las mismas tarjetas de campo con un botón **Try**. La respuesta se muestra en esta página y el producto **no** se cambia. Úselo para probar un prompt y luego vuelva a **Generate**.

**Photos** – vea la sección 3.16.

**History** – la tabla **When**, **Type**, **Status** y un botón **Restore**. **Restore** devuelve al producto el texto anterior de esa escritura. Las filas sin valor anterior, o con error, no tienen botón. El informe **History** de toda la tienda no se borra. Una lista vacía dice **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Fotos del producto

Abra la pestaña **Photos** en un producto. Si **AI Image Finder** está desactivado, la pestaña explica cómo activarlo en **Settings**, **General**.

1. Haga clic en **Find pages**. DeepSeek sugiere páginas web que probablemente contienen fotos del producto.
2. Aparecen páginas e imágenes. Marque las imágenes que quiera.
3. Haga clic en **Add selected to this product**. No se guarda nada antes de este clic.

El modelo sugiere páginas a partir de su propio conocimiento, no de una búsqueda web en vivo. Compruebe los derechos de autor y la calidad de las imágenes antes de publicarlas.

## 4. Front de la tienda

El módulo no muestra nada a los clientes. Los dos hooks de front que registra están vacíos y no se añade ninguna plantilla, botón ni bloque a su tema. El texto escrito por el módulo aparece en su tienda solo como campos normales de productos y categorías (nombre, descripciones, metaetiquetas, etiquetas). No necesita modificar el tema.

El módulo tiene además dos direcciones que un navegador o un servidor pueden abrir:

| Dirección | Quién la usa | Qué ocurre |
|---|---|---|
| La dirección **Cron** con `&action=generateProductContent` o `&action=generateCategoryContent` | El programador de su servidor, o usted al probar | Se escribe un lote. Con **Enable Debug** en **Yes**, se imprime el plan y no se guarda nada. Un secreto incorrecto o ausente se rechaza. |
| La dirección interna de solicitudes que usan los botones del back office | Su navegador mientras trabaja en el back office | Necesita un token que el back office añade automáticamente. Usted nunca lo escribe. Si se rechaza, vuelva a cargar la página del back office. |

## 5. Problemas

**Una generación falla y History muestra un Error.**
Abra **History**, abra la fila y lea el mensaje. Las causas habituales están a continuación.

**La clave de API es rechazada o falta.**
Abra **Settings**, **DeepSeek**, pegue de nuevo la clave de https://platform.deepseek.com/api_keys y pulse **Save**. En la página de producto nuevo, el aviso **Add an API key in the module settings first.** desaparece después. Si DeepSeek informa de que no hay saldo, recargue la cuenta en DeepSeek.

**La llamada termina con un tiempo de espera agotado.**
Aumente **API timeout (seconds)** en **Settings**, **General** (para `deepseek-reasoner` use varios cientos de segundos). Para cron, reduzca **Product to update**.

**El texto se corta a mitad de una frase.**
Aumente **Max Tokens** en **Settings**, **DeepSeek**. Con `deepseek-reasoner` el límite cubre también su razonamiento.

**Los ajustes no parecen cambiar el estilo.**
Con `deepseek-reasoner`, **Temperature**, **Top P** y los dos campos de penalización pueden ignorarse. Use `deepseek-chat`. Compruebe también que **Studio** está guardado y que ha usado el idioma correcto.

**Una respuesta no se guarda y no cambia nada en el producto.**
Causas posibles: la respuesta contiene una línea de **Forbidden words** y **Quality gate** está activado (edite la lista o desactive el filtro); **Existing text** está en **Skip if filled** y el campo tiene texto; se ha alcanzado el límite mensual (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**El nombre de modelo que escribí no funciona.**
Añadió un id que su cuenta no puede llamar. Seleccione de nuevo el `deepseek-chat` integrado y elimine su entrada propia.

**La lista de Generate está vacía o es demasiado corta.**
Revise **Product status**, **Product stock**, **Update only** y **Product Limit**. Un error habitual es dejar **Update only** en "already updated" en una primera ejecución.

**El cron no hace nada.**
Compruebe en este orden: **Enable Cron Feature** está en **Yes**; la dirección termina con el `&action=…` correcto; el secreto es el que se muestra actualmente; **Enable Debug** está en **No**; **Selected Products** todavía tiene elementos en espera; el servidor realmente llama a la dirección. Un conjunto terminado deja de cambiar a propósito. Para varios campos use **pendingField** en lugar de **pendingDeepSeek**, porque el segundo omite un producto en cuanto se ha generado cualquier campo.

**El cron se detuvo después de cambiar el secreto.**
La dirección antigua ya no es válida. Copie la nueva dirección (con `&action=…`) en el programador.

**La página dice "Error! Invalid token!" o los botones no responden.**
La página estuvo abierta demasiado tiempo. Vuelva a cargar la página del back office e inténtelo de nuevo.

**La pestaña Modules del producto no tiene contenido de My AI DeepSeek.**
Compruebe que **Product edit page Form** o **Product Edit History** está activado, que el módulo está activo y que la caché se ha vaciado.

**No hay botón "Restore".**
La fila era un error, la escritura no tenía valor anterior, o **Clear list** eliminó las filas de History.

**Algunas etiquetas aún dicen "OpenAi".**
Unos pocos mensajes y etiquetas de filtro conservan un nombre anterior, por ejemplo **OpenAi Settings Updated** tras guardar el formulario **DeepSeek**, las opciones "updated with OpenAi content" del filtro **Update only** o un nombre de modelo de ejemplo antiguo en una pista. El servicio utilizado es DeepSeek. En History la columna **Provider** puede mostrar el nombre interno anterior. Esto no afecta a los resultados.

**No cambia nada en el front de la tienda.**
El módulo escribe campos normales de producto. Revise el producto en **Catalog** y la caché de su tema.

## 6. Para el desarrollador

### 6.1 Resumen

- **Nombre técnico:** `myaideepseek`
- **Nombre del módulo en la lista:** My AI DeepSeek - AI content generation
- **Versión:** 1.0.0
- **Autor:** MyPresta.eu
- **Compatibilidad con PrestaShop:** 1.6 – 9.99.99
- **PHP:** 7.0 o superior (la instalación rechaza versiones anteriores)
- **Red:** cURL y HTTPS a `https://api.deepseek.com/v1`
- **Prefijo de configuración:** `MYPRESTA_MYAIDEEPSEEK_`
- **Flujo:** los ajustes se leen de la tabla de configuración; los prompts se construyen a partir de la plantilla o la instrucción más las reglas de Studio; se envía una solicitud de chat por campo; la respuesta se comprueba (Quality gate, presupuesto), se guarda en el producto o la categoría y se registra en `myaideepseek_log` con el valor anterior.

### 6.2 Archivos

| Archivo | Finalidad |
|---|---|
| `myaideepseek.php` | Clase principal: instalación, desinstalación, formularios de ajustes, navegación, hooks, pestaña de producto. |
| `autoload.php` | Carga de clases para `src/` y `lib/`. |
| `src/OpenAIService.php` | Cliente HTTP para la llamada de chat completion (se mantiene con el nombre de archivo anterior). |
| `src/Studio.php` | Añade las reglas de Studio y la comprobación de calidad. |
| `lib/updateChecker.php` | Comprobación de actualizaciones contra MyPresta.eu. |
| `lib/sectionHelp.php` | Textos de las pistas de ayuda. |
| `lib/searchTool/` | Ayudante de autocompletado. |
| `lib/prestashop9compatibility.php` | Ayudante de compatibilidad para PrestaShop 9. |
| `controllers/admin/` | Siete controladores de administración (vea 6.3). |
| `controllers/front/ajax.php` | Acciones AJAX del back office (generar, restaurar, búsqueda de imágenes). |
| `controllers/front/cron.php` | Generación programada. |
| `views/templates/hook/*.tpl` | Pestaña de producto, generadores masivos, dashboard, cron, history, playground, navegación. |
| `views/templates/admin/product_creator.tpl` | Pantalla de producto nuevo. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Traducciones del módulo. |

### 6.3 Controladores

| Clase | Función |
|---|---|
| `AdminMyAIDeepSeekMain` | Padre del menú **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` o `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Entrada de ajustes (los formularios residen en la página de configuración del módulo). |
| `AdminMyAIDeepSeekCron` | Formularios de **Cron**. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Necesita el parámetro `secret_token` igual a `MYPRESTA_MYAIDEEPSEEK_TOKEN`; en caso contrario responde *Error! Invalid token!* |
| `ModuleFrontController` cron | Necesita `secret` igual al secreto de productos o de categorías. |

La página de configuración del módulo usa `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = la sección **DeepSeek**, `studio`, `templates`, `playground`) y `mcg_preset` para los rangos de fecha predefinidos.

Parámetros de consulta de cron que lee `controllers/front/cron.php`:

| Parámetro | Se usa para | Valor predeterminado si falta |
|---|---|---|
| `secret` | Secreto de productos o categorías (obligatorio) | – |
| `action` | `generateProductContent` o `generateCategoryContent` (obligatorio) | – |
| `updatedField` | Campo que se escribe | valor guardado |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | valor guardado |
| `productsToUpdate` / `categoriesToUpdate` | Tamaño del lote | valor guardado |
| `languageId` | Idioma | valor guardado |
| `promptTemplateId` | Plantilla | valor guardado |
| `debug` | Solo imprimir el plan | valor guardado |
| `categories` | Filtro de categorías (productos) | valor guardado |
| `productIds` | Filtro de ids de producto | valor guardado |

### 6.4 Hooks

Registrados: `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (ambos devuelven una cadena vacía), `actionProductFormBuilderModifier` (retorna sin salida), `displayAdminProductsExtra` (el contenido de la pestaña **Modules**), `displayBackOfficeHeader` (recursos, cargador de la página de producto), `displayBackOfficeTop` (acceso directo en la barra superior), `dashboardZoneTwo` (bloque en el dashboard de PrestaShop), `displayHeader` y `displayFooter` (ambos vacíos). El módulo no expone hooks propios. No tiene sobrescritura de `enable()` ni de `disable()`.

### 6.5 Overrides

Ninguno.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 filas tras la instalación. |
| `myaideepseek_log` | Una fila por solicitud: ids de producto, categoría, CMS, fabricante, idioma y empleado; `type`, `method`, `status`, servicio, `model`, código HTTP, duración, recuentos de tokens, mensaje de error, `prompt`, `reply`, y los valores antiguos y nuevos de nombre, descripciones, campos meta y etiquetas. |

La desinstalación elimina ambas tablas. Las pestañas se eliminan. El texto de productos y categorías no se toca.

### 6.7 Claves y traducciones

Todas las claves llevan el prefijo `MYPRESTA_MYAIDEEPSEEK_`.

| Sufijo de clave | Predeterminado | Significado |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Tiempo de espera de la llamada en segundos. |
| `PRODUCT_LOG` | 1 | Historial de edición de producto. |
| `TOPCTA` | 1 | Acceso directo de la barra superior. |
| `PRODUCT` | 1 | Generador en la página de producto. |
| `IMAGEFINDER_ENABLE` | 1 | Interruptor de la búsqueda de fotos. |
| `IMAGEFINDER_PROMPT` | texto en inglés integrado | Instrucción de la búsqueda de fotos. |
| `API_KEY` | vacío | Clave de DeepSeek. |
| `MODEL` | `deepseek-chat` | Modelo activo. |
| `EXTRA_MODELS` | vacío | Modelos añadidos por el comerciante, uno por línea. |
| `MODEL_CAPS` | vacío | Parámetros aprendidos por modelo en tiempo de ejecución. |
| `TEMPERATURE` | 0.7 | Muestreo. |
| `MAX_TOKENS` | 3200 | Límite de respuesta. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Muestreo y penalizaciones. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | vacío | Reglas de Studio. |
| `BUDGET` | 0 | Límite mensual, 0 = ninguno. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | aleatorio | Token de la dirección AJAX. |
| `SECRET`, `CAT_SECRET` | aleatorio | Secretos de cron de productos y categorías. |
| `ENABLE_CRON` | 0 | Interruptor global de cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Intervalo sugerido (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Campo de cron. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Regla de cron. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Lote de cron. |
| `promptTemplateId`, `catpromptTemplateId` | vacío | Plantilla de cron. |
| `languageId`, `catlanguageId` | idioma predeterminado | Idioma de cron. |
| `debug`, `catdebug` | 0 | Debug de cron. |
| `productIdsList`, `categories` | vacío | Filtros de cron. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | vacío / se fija en tiempo de ejecución | Estado de la interfaz. |

El modelo predeterminado es `deepseek-chat`. Los modelos integrados son `deepseek-chat` y `deepseek-reasoner`. La desinstalación elimina las claves anteriores. Las claves de filtro de Generate (por ejemplo los filtros de categoría, marca y estado de los formularios **Generate**) no están en la lista de desinstalación y pueden permanecer.

Traducciones: añada `translations/{iso}.php` en el formato estándar de PrestaShop. Los textos de ayuda de los campos los construye `fieldHelp()` con la forma What it does / How to configure / Effect y pasan por `$this->l()`. Algunas cadenas de la pestaña de producto y de las plantillas de generate se definen en los archivos `.tpl` con `{l s=…}`. Unas pocas cadenas sobrantes aún contienen el nombre anterior del proveedor (vea Problemas).

### 6.8 Ampliación

La pestaña de producto, las pantallas masivas y cron usan los mismos marcadores de prompt y las mismas acciones AJAX, así que una plantilla propia que siga `{product_name}`, `{product_brand}`, `{product_features}` y `{product_tags}` funciona en todas partes. Los controladores de front no renderizan ninguna plantilla, por lo que un tema no tiene nada que sobrescribir. Las plantillas de administración de `views/templates/hook/` pueden sobrescribirse mediante la sobrescritura estándar de plantillas de módulo del tema de su back office.

## 7. Ayuda

Página del módulo: https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

Para escribirnos sobre el módulo:

1. Inicie sesión en su cuenta de cliente en mypresta.eu.
2. Abra la página de contacto.
3. Elija el asunto **Support for paid modules**. El formulario indica que debe haber iniciado sesión. Tras iniciar sesión, seleccione este módulo de su historial de compras.
4. Describa el problema. Añada la fila de **History** (estado y mensaje) y las versiones de PrestaShop y PHP. No envíe nunca la clave de API ni el secreto de cron.
