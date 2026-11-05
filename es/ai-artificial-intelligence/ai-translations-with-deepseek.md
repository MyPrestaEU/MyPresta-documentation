---
title: "AI Translations with DeepSeek – documentación y manual de usuario (user manual)"
sidebar:
  label: "AI Translations with DeepSeek – documentación y manual de usuario (user manual)"
description: "Guía de configuración y solución de problemas del módulo AI Translations with DeepSeek para los titulares de tienda que ya tienen el módulo."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with DeepSeek en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.7.0.0 o posterior y necesita una clave API de su propia cuenta de DeepSeek.

- **PrestaShop:** versión 1.7.0.0 o posterior.
- **PHP:** el módulo no declara una versión mínima de PHP. El servidor debe ejecutar la versión de PHP que exige su versión de PrestaShop.
- **Extensiones de PHP:** cURL (conexión con DeepSeek), mbstring (recuento de caracteres en los textos), OpenSSL (cifrado de la clave API) y JSON (guardado de los datos enviados y recibidos).
- **Otros módulos:** el módulo no requiere ningún otro módulo.
- **Fuera de la tienda:** una cuenta propia de DeepSeek con clave API. Sin clave, el módulo no puede traducir nada.
- **Cron en el servidor:** solo es necesario si los trabajos masivos deben ejecutarse sin hacer clic. Consulte el apartado 3.1.
- **Catálogo grande:** un trabajo masivo se divide en fragmentos, y cada fragmento es una llamada a DeepSeek. Los rangos grandes tardan mucho, así que compruébelos con **Estimate** antes de iniciarlos.

## 2. Instalación

1. Suba el archivo ZIP del módulo en **Module Manager** con el botón **Upload a module** y haga clic en **Install**.
2. Tras la instalación aparece una entrada en el menú: **International → AI Translations with DeepSeek**. Esta entrada abre el panel del módulo.
3. La instalación no vacía la caché de la tienda. Si la nueva entrada del menú no aparece, vaya a **Advanced Parameters → Performance** y haga clic en **Clear cache**.

Tras la instalación el panel está vacío: no hay clave API y los ajustes tienen los valores iniciales del apartado 3.1.

**La desinstalación** elimina la entrada del menú, los trabajos masivos con su historial, el glosario, la lista de exclusiones, la memoria de traducciones, las copias de seguridad que usa **Rollback**, el historial de llamadas y errores, la cola de revisión, la lista de la pestaña **Catalog** y todos los ajustes, incluidas la clave API y la dirección cron.

La desinstalación **no elimina** las traducciones ya guardadas en la tienda: los textos de productos, categorías, páginas CMS y International → Translations se quedan como están. Después de desinstalar, ya no podrá deshacer estas traducciones con **Rollback**, porque las copias de seguridad se eliminan junto con el módulo.

Reinstalar **no restaura** los datos eliminados. Las tablas se crean vacías y los ajustes vuelven a sus valores iniciales. La dirección cron también cambia, así que copie la nueva desde **Settings** y actualice la programación en el servidor.

## 3. Configuración y trabajo en el back office

Las pantallas del panel están en inglés. En este manual los nombres de campos, pestañas y botones se dan exactamente como aparecen en pantalla.

**Quién inicia el trabajo:** siempre un empleado en el back office. Los clientes no inician traducciones.

**El proceso de principio a fin:**

1. En **Settings**, pegue su clave de DeepSeek, seleccione un modelo y haga clic en **Save**. Después haga clic en **Test connection** para comprobar la clave.
2. Configure **Source locale** (el idioma del original) y compruebe que **Allow publish / save** esté activado.
3. Elija qué traducir. Los dominios y cadenas sueltas se traducen en **Manual**. Los rangos grandes se envían mediante **Bulk**. Los campos de productos, categorías y páginas CMS se traducen en **Catalog**. Los botones junto a los campos de los formularios de la tienda y en la página International → Translations funcionan donde esté trabajando.
4. En **Manual** y junto a los campos recibe primero una propuesta de traducción. La guarda en un paso aparte: con el botón **Save approved** en **Manual**, marcando **Save now (skip review)** o con el botón **Save** de PrestaShop en el formulario.
5. En **Bulk** haga clic en **Estimate**. No se envía ni se guarda nada. Si la estimación le parece bien, haga clic en **Start job**. El trabajo va a **Jobs** y espera. No se ejecuta solo: haga clic en **Process slice** o **Auto-process**, o deje que una llamada cron en el servidor procese los fragmentos.
6. Las traducciones que no superaron el control de calidad pasan a **Review**. El botón **Approve** solo cambia el estado de la fila. No escribe el texto en la tienda.
7. **Glossary** y **Excludes** afectan a las siguientes traducciones. Las traducciones ya guardadas no cambian.
8. **Dashboard** muestra las carencias y los costes, y **History** muestra cada llamada a DeepSeek.

**Cómo termina el trabajo:** un trabajo masivo termina con el estado **completed** (todo traducido) o **completed_with_errors** (hubo errores). Si la notificación está activada, después se envía un correo electrónico. Una traducción manual termina cuando las filas seleccionadas se guardan en la tienda.

### 3.1 Settings (ajustes del módulo)

Ruta: **Módulos** → **Module Manager** → nombre del módulo → **Configure**. El botón **Configure** abre el panel del módulo, y la pestaña **Settings** está en la barra superior.

![Pestaña Settings](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

Más partes del mismo formulario:

![Settings – interruptores de botones de traducción e idioma de origen](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – límites, presupuesto y temperatura](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – correo, guardado y dirección cron con los botones Test connection y Save](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Guardar el formulario con **Save** no cambia las traducciones terminadas. Si el campo **DeepSeek API key** está vacío y antes no se guardó ninguna clave, aparece el mensaje: “Settings saved. No API key is stored, so nothing can be translated until you paste one.”

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **DeepSeek API key** | vacío | La clave de su cuenta de DeepSeek. Un campo vacío mantiene la clave ya guardada, y un valor nuevo la sustituye. Un campo vacío no borra la clave. Bajo el campo se muestra la clave guardada enmascarada. Las peticiones van a api.deepseek.com. |
| **Model** | deepseek-flash | El modelo de DeepSeek que escribe la traducción. Los modelos integrados son: deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat y deepseek-reasoner. Un modelo que la cuenta no puede usar falla con un error que se guarda en **History**. |
| **Add a DeepSeek model** | vacío | Añade un identificador de modelo que no está en la lista. Escríbalo exactamente como aparece en su cuenta de DeepSeek y haga clic en **Add model**. El modelo añadido pasa a ser el modelo activo al momento. **Remove** solo borra los modelos añadidos aquí. Los modelos integrados no se pueden eliminar. |
| **Tone** | Formal | Un estilo que se añade a cada instrucción para el modelo. **Formal** es para textos de la tienda y del back office, **Casual** es más ligero, y **Brand** funciona junto con el campo **Brand voice**. Las traducciones nuevas siguen el estilo. Las traducciones guardadas no cambian hasta que las vuelva a traducir. |
| **Brand voice** | vacío | Algunas frases que describen cómo debe sonar la tienda. El campo aparece cuando **Tone** está en **Brand**. El texto se añade a la siguiente instrucción y no reescribe las traducciones guardadas. |
| **Source locale** | vacío (—) | El idioma tratado como original, por ejemplo English (en-US). El guion “—” significa que la pantalla en la que traduce proporciona por sí misma el idioma de origen. Las traducciones manuales y masivas y los botones de International → Translations envían este idioma como origen. El idioma predeterminado de la tienda no cambia. |
| **Individual field buttons — shop forms** | Sí | Un botón junto a cada campo multilingüe de los formularios de la tienda: producto, categoría, CMS y otros formularios. El botón traduce solo ese campo. **No** oculta estos botones en toda la tienda. No afecta a International → Translations. |
| **Individual field checkboxes — shop forms** | Sí | Una casilla junto a los campos de los formularios de la tienda y una barra inferior que traduce los campos marcados. **No** oculta las casillas y la barra. Los botones de la fila anterior tienen su propio interruptor. |
| **Individual field buttons — International → Translations** | Sí | Un botón junto a cada campo de International → Translations. **No** oculta estos botones solo en esta página. Los formularios de la tienda no cambian. |
| **Individual field checkboxes — International → Translations** | Sí | Casillas y barra en International → Translations. La barra traduce los campos marcados uno a uno. **No** oculta las casillas y la barra en esta página. |
| **Batch size** | 25 | Cuántas cadenas se envían en una llamada a DeepSeek. Los valores permitidos van de 1 a 100. Para una primera ejecución elija de 10 a 25. Un bloque más grande termina un trabajo con menos llamadas, pero tras un error se repite una parte mayor. |
| **Dry-run sample** | 10 | Cuántas cadenas de ejemplo muestra **Estimate** antes de un trabajo masivo. Los valores permitidos van de 1 a 50. **Estimate** no guarda traducciones. |
| **Max tokens (0 = default)** | 0 | Un límite para la longitud de una respuesta. 0 significa el límite predeterminado de DeepSeek. Ponga un número si las respuestas se cortan o son demasiado largas. El límite se aplica solo a las llamadas siguientes. |
| **Budget USD / month** | 0 | Un límite mensual en dólares estadounidenses, calculado a partir del consumo guardado. 0 significa sin límite. Al alcanzar el límite se detienen las nuevas traducciones, y las ya guardadas se conservan. |
| **Rate limit / min** | 60 | Cuántas llamadas puede hacer la tienda por minuto. 0 desactiva este límite local. Las llamadas por encima del límite se omiten y se registran en **History**. DeepSeek puede aplicar además su propio límite. |
| **Log retention days** | 30 | Cuántos días se conservan las entradas de **History**. El mínimo es 1 día. Las entradas más antiguas se eliminan. Los trabajos, el glosario y las traducciones guardadas no se borran. |
| **Temperature** | 0.2 | Cuánto puede reformular el modelo el texto. Un valor cercano a 0,2 se mantiene fiel al original, y los valores más cercanos a 1 cambian más las frases. Rango permitido: de 0 a 1. Los marcadores y el HTML se siguen comprobando después de cada traducción. |
| **Email notify on complete** | No | Envía un correo cuando termina un trabajo masivo. El trabajo en sí funciona igual; solo cambia el envío. |
| **Notify email** | vacío | La dirección que recibe el correo sobre un trabajo terminado. El campo solo funciona si **Email notify on complete** está activado. Un campo vacío envía el correo a la dirección de la tienda de los datos de la empresa. Guardar la dirección no envía ningún mensaje. El asunto y el texto están en inglés, por ejemplo “myaitranslationsdeepseek job #41 completed”, y el texto contiene los números de cadenas hechas, fallidas y omitidas. |
| **Allow publish / save** | Sí | Si el módulo puede guardar traducciones en la tienda. Con **No** el guardado queda bloqueado en **Manual**, en trabajos masivos y en **Catalog**. Los botones de International → Translations solo rellenan el formulario, y el botón **Save** de PrestaShop lo guarda. |
| **CRON URL** | dirección generada | Una dirección para la programación del servidor. Cada llamada procesa un fragmento de un trabajo en espera y termina. No publique esta dirección, porque cualquiera que la conozca puede iniciar un fragmento. Abrir **Settings** no inicia ningún trabajo. |

Botones al final del formulario: **Save** guarda los ajustes. **Test connection** comprueba la clave y no guarda ninguna traducción.

Inicio recomendado: pegue la clave, seleccione un modelo, configure **Source locale**, haga clic en **Save** y después en **Test connection**. Deje el resto de valores en sus valores iniciales hasta que algún trabajo no se comporte como espera.

### 3.2 Dashboard

El Dashboard muestra cuántos textos faltan en cada parte del catálogo para el idioma elegido, y el uso de DeepSeek. Abrir **Dashboard** no envía ninguna petición ni cambia traducciones.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** es el idioma cuyas carencias se cuentan. La primera vez se selecciona el primer idioma de la lista de la tienda. Cambie el idioma y haga clic en **Show** para recalcular la tabla.
- **Tabla de cobertura** con las columnas **Section**, **Done**, **Missing** y **Total**. Cada fila es una parte del catálogo: back office, temas, módulos, correos u otros. La barra muestra qué parte ya está traducida.
- **Tarjetas y gráficos** cuentan las llamadas del periodo elegido. Los campos de filtro son fechas (valores predefinidos y **From** y **To**), luego **Model**, tipo, estado, idioma, empleado y una palabra en el prompt o en la respuesta. El botón **Filter** aplica el filtro. Las tarjetas muestran el número de llamadas, los tokens enviados y recibidos, el tiempo medio y el coste estimado. El coste es una estimación local, no una factura.
- **Latest prompts** lista las diez llamadas más recientes. **View** abre el prompt y la respuesta en una ventana. **See all** lleva a **History**.
- Bajo la tabla aparece la dirección cron. Es el mismo secreto que en **Settings**.

![Dashboard – gráficos y resúmenes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

Una tabla de cobertura vacía significa que la tienda aún no tiene catálogo para ese idioma. El catálogo lo crea International → Translations.

### 3.3 Manual

**Manual** traduce un dominio elegido, unas pocas cadenas cada vez. **Filter** solo carga la lista y no guarda nada.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Section** | Back office | Elige el catálogo de PrestaShop que se lee: **Back office**, **Themes**, **Installed modules**, **Emails** u **Others**. Cambiar la sección recarga el formulario y no llama a DeepSeek. |
| **Theme** | — | Aparece solo con **Themes**. Limita la lista a un tema. |
| **Module** | — | Aparece solo con **Installed modules**. Limita la lista a un módulo. Un módulo sin dominios carga de inmediato todas sus cadenas. |
| **Source** | Source locale de **Settings** (en-US) | El idioma del que se toman los textos. Elija el que ya tenga una traducción fiable. El idioma de destino no cambia. |
| **Target** | primer idioma de la tienda de la lista | El idioma que quiere completar. Debe existir en International → Localization → Languages. La lista y el guardado posterior solo se aplican a este idioma. |
| **Domain** | — | El dominio de traducción, los mismos grupos que en International → Translations. Pulse **Filter** para que se rellene la lista, elija un dominio y pulse **Filter** de nuevo. No aparece para un módulo sin dominios. |
| **Only empty** | Sí | Oculta las cadenas que ya tienen traducción. **No** muestra todas las cadenas. La tabla cambia; las traducciones guardadas no se borran. |
| **Search** | vacío | Deja solo las cadenas cuyo origen contiene la palabra escrita. El catálogo no cambia. |

**Cómo traducir:**

1. Marque las filas, o haga clic en **Check all** (marca las filas visibles). **Uncheck all** quita las marcas.
2. Haga clic en **Translate selected (review)**. El módulo envía las cadenas marcadas y muestra una tabla de revisión. Todavía no se guarda nada.
3. En la tabla de revisión, desmarque una fila que no quiera guardar y corrija la propuesta en el campo **AI proposal**.
4. Haga clic en **Save approved**. Se guardan las filas marcadas.

Si marca **Save now (skip review)** antes de traducir, las filas aceptadas se guardan de inmediato, sin la tabla de revisión.

La tabla de resultados tiene las columnas **Source**, **Current** (la traducción actual), **AI proposal**, **Status** (**empty** o **filled**), **Tokens** y **Warnings**. Una fila con un marcador o HTML defectuoso no se guarda.

Mensajes que puede ver:

- “No strings match this filter. Nothing was sent to DeepSeek.” — el filtro no encontró cadenas. No se envió nada.
- “Review is ready. Nothing is saved until you press Save approved.” — las propuestas esperan en la tabla. Solo **Save approved** las guarda.
- “Saved. The approved strings were written for the target language.” — se guardaron las filas marcadas.
- “Not saved because of broken placeholders or HTML: N.” — N filas no se guardaron porque el modelo cambió un marcador o una etiqueta HTML. Corríjalas en la tabla o desmárquelas.

### 3.4 Bulk

**Bulk** crea un trabajo para muchos dominios e idiomas. El trabajo no se ejecuta en esta página. Espera en **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Section** | Back office | El catálogo que lee el trabajo. El campo **Theme** aparece solo con **Themes**, y el campo **Module** solo con **Installed modules**. Las cadenas fuera de la sección elegida no entran en el trabajo. |
| **Source** | Source locale de **Settings** (en-US) | El idioma que el trabajo trata como original. Cada destino se traduce desde él. |
| **Targets** | vacío | Los idiomas que completa el trabajo. Puede elegir varios: mantenga pulsada Ctrl o Cmd y haga clic. El trabajo crea cadenas separadas para cada idioma elegido. |
| **Domains** | vacío | Los dominios incluidos en el trabajo. Los dominios no elegidos no se traducen. |
| **Policy** | Fill empty | **Fill empty** omite las cadenas que ya tienen traducción. **Overwrite all** envía todas las cadenas, incluidas las traducidas, y puede sustituirlas. **Outdated if equals source** envía las cadenas cuya traducción es idéntica al original. |
| **Dry-run job** | No | El trabajo llama al modelo y guarda el resultado en el historial del trabajo, pero no escribe traducciones en la tienda. Con **No** el trabajo guarda los resultados, si **Allow publish / save** está activado. |

**Estimate** muestra el número de cadenas, los tokens y el coste estimados, y cadenas de ejemplo. No se envía ni se guarda nada. Mensaje: “Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved.”

**Start job** crea el trabajo y lo lleva a **Jobs** con el nuevo trabajo abierto. Mensaje: “Job #N is waiting (N strings, est. $…). It has not run yet.”

Mensajes de error que impiden el inicio:

- “Nothing was started. Select at least one target language.” — no se eligió ningún idioma de destino.
- “Nothing was started. Pick a theme.” o “Nothing was started. Pick a module.” — en la sección **Themes** o **Installed modules** no se eligió tema o módulo.
- “Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.” — no hay clave. No se creó ningún trabajo.

### 3.5 Jobs

**Jobs** es la cola de trabajos masivos. Abrir la lista no llama a DeepSeek. El catálogo solo cambia mientras se procesa un trabajo que no es una prueba (dry-run).

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**La lista de trabajos** tiene las columnas **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** y **Date**. Haga clic en un trabajo para ver sus cadenas. El filtro **Failed only** muestra solo los errores, y **Error CSV** descarga la lista de errores como archivo.

Estados del trabajo, tal como aparecen en la columna **Status**: **pending** (en espera), **running** (en curso), **paused** (pausado), **completed** (terminado), **completed_with_errors** (terminado con errores), **cancelled** (cancelado) y **failed** (terminado con error). Estados de las cadenas en los detalles: **pending**, **processing**, **done**, **failed**, **skipped** y **rolled_back**. La etiqueta **dry-run** marca un trabajo de prueba.

**Botones dentro de un trabajo:**

- **Process slice** envía el siguiente bloque (tantas cadenas como indique **Batch size**) y se detiene. Tras el clic ve qué filas se guardaron, omitieron o fallaron.
- **Auto-process** envía bloques uno tras otro hasta que el trabajo termina o falla. Deje la página abierta, porque la barra de progreso se actualiza sola.
- **Pause** detiene el trabajo. No traduce más cadenas hasta que lo reanude.
- **Resume** devuelve el trabajo a la cola. El trabajo no arranca solo: haga clic en **Process slice** o **Auto-process**, o espere a la llamada cron.
- **Retry failed** devuelve las cadenas fallidas al estado en espera.
- **Rollback** restaura las traducciones anteriores allí donde el módulo guardó una copia de seguridad antes del cambio. Antes de ejecutarlo se pregunta: “Roll back this job?”. Mensaje tras ejecutarlo: “Rollback: restored N translations.”
- **Error CSV** descarga la lista de filas con error.

**En esta versión del módulo no hay botón de cancelar en la pantalla del trabajo.** No intente cancelar un trabajo aquí. Deténgalo con **Pause** y no lo reanude.

Si DeepSeek rechaza demasiadas llamadas, el trabajo se detiene solo. Su error muestra: “Rate limit — job auto-paused. Resume later.”

### 3.6 Review

**Review** es la cola de traducciones que retuvo el control de calidad. Aquí llegan las filas con un marcador o HTML defectuoso, con una traducción muy larga o muy corta, o con una puntuación inferior a 70.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Columna | Qué muestra |
|---|---|
| **ID** | El número de la fila en la cola. |
| **Domain** | El dominio del que procede el texto. |
| **Source** | El texto original. |
| **AI** | La propuesta del modelo. |
| **Score** | La puntuación automática de calidad de 0 a 100. |
| **Flags** | Los motivos por los que se retuvo la fila, descritos abajo. |

**Marcas (flags):**

- **validation_failed** — falta un marcador o una etiqueta HTML, o se cambió.
- **length_explosion** — la traducción tiene más del doble y medio de caracteres que el original.
- **too_short** — la traducción tiene menos del 30 % de la longitud del original, y el original tiene más de 20 caracteres.
- **possible_untranslated** — quedan palabras en inglés como “the”, “and”, “with” en la traducción.
- **warning** — una advertencia de control que baja la puntuación.

**Approve** marca la fila como aceptada y **Reject** como rechazada. Ninguno de los dos botones guarda texto en la tienda. Una cola vacía muestra: “The queue is empty.” Una cola vacía no significa que todos los idiomas estén traducidos. Compruébelo en el **Dashboard**.

Si el trabajo tenía permiso para guardar y la cadena superó la validación, la traducción puede estar ya en la tienda. La cola **Review** es una lista para revisión manual, no un bloqueo de guardado. El guardado separado de filas seleccionadas se hace en **Manual**.

### 3.7 Catalog

**Catalog** traduce campos de productos, categorías y páginas CMS. No abarca los textos de International → Translations. Un bloque incluye como máximo 100 registros.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Entity** | product | Elige el tipo de registros: **product**, **category** o **cms**. La lista de campos cambia con la elección. La elección por sí sola no traduce nada. |
| **Fields** | campos seleccionados por defecto para el tipo | Los textos que envía el bloque. Para productos: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** y **Friendly URL**. Para categorías: **Title**, **Description**, **Meta title**, **Meta description** y **Friendly URL**. Para CMS: **Title**, **Meta description**, **Meta keywords**, **Content** y **Friendly URL**. Seleccione manteniendo pulsada Ctrl o Cmd. Los campos no seleccionados no se envían ni cambian. |
| **Source language** | primer idioma de la lista | El idioma del que se copia el texto. No cambia. |
| **Target language** | primer idioma de la lista | El idioma que recibe la traducción. Elija uno distinto del origen. |
| **Only empty** | Sí | Omite los campos que ya tienen texto en el idioma de destino. **No** envía también los campos rellenos, y entonces el bloque puede sustituir ese texto. |
| **Start after ID** | 0 | Omite los registros hasta este ID. 0 empieza por el primer registro. Tras cada bloque el campo se rellena solo, y el siguiente bloque empieza después de ese ID. |

El botón **Translate batch (max 100)** ejecuta un bloque. El resultado muestra cuántas filas se guardaron y cuántas fallaron.

Antes de cambiar **Only empty** a **No**, ejecute un bloque pequeño y abra un producto en el idioma de destino.

### 3.8 Glossary

**Glossary** es una lista de términos que el modelo debe mantener o traducir de una forma fija. Añadir un término no cambia las traducciones guardadas. Las traducciones siguientes leen la lista.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Source term** | vacío (obligatorio) | La palabra o expresión en el idioma original, con mayúsculas si importan. El modelo trata este término como fijo cuando aparece en el texto de origen. |
| **Target locale** | vacío | Limita la fila a un idioma, por ejemplo pl-PL. Un campo vacío aplica la fila a todos los idiomas de destino. |
| **Target term** | vacío | La traducción aprobada del término. Déjelo vacío solo si **Do not translate** está activado. |
| **Do not translate** | No | El modelo copia el término sin cambios. Actívelo para nombres de marca, SKU y marcadores. Desactívelo cuando **Target term** deba ser la traducción. |

El botón **Add** añade el término. La tabla bajo el formulario tiene las columnas **Source**, **Locale**, **Target** y **Do not translate**, y cada fila tiene un botón **Delete** que elimina solo esa fila. Una lista vacía muestra: “No glossary terms yet.”

**Import CSV** añade filas desde un archivo. El archivo debe tener las columnas: source_term, target_locale, target_term, do_not_translate. La importación solo añade las filas que puede leer. **Export CSV** descarga la lista actual y no cambia nada.

Los términos cortos y exactos funcionan mejor. Un término muy general se impondrá cada vez que aparezca.

### 3.9 Excludes

**Excludes** son patrones de texto que no deben enviarse a DeepSeek. El texto permanece sin cambios en PrestaShop. El módulo lo omite en la siguiente traducción manual, en el trabajo masivo y en las acciones de International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Pattern** | vacío (obligatorio) | El texto o expresión que se compara con cada texto de origen. Según **Type**, es el texto completo, el principio, un fragmento o una expresión regular. |
| **Type** | exact | **exact** es el texto completo, **prefix** es el principio, **contains** es un fragmento en cualquier lugar y **regex** es una expresión regular de PHP. Un patrón demasiado amplio omite más de lo que espera. Empiece con uno corto. |

El botón **Add** añade el patrón. La tabla tiene las columnas **Pattern**, **Type** y **On** (si el patrón está activo). Cada fila tiene un botón **Delete** que elimina solo ese patrón. Las traducciones guardadas no se borran. Una lista vacía muestra: “No patterns yet.”

Use patrones para textos que deben quedarse en el idioma de origen, como nombres legales o tokens técnicos. Si un texto debe traducirse de una forma fija, use **Glossary**.

### 3.10 History

**History** es la lista completa de llamadas guardadas a DeepSeek: traducción manual, la página de International → Translations, trabajos masivos, Catalog y la prueba de conexión. Cada fila guarda el prompt, la respuesta, el modelo, los idiomas, el número de tokens y el tiempo de respuesta.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** es la fecha de la llamada. **Type** es el lugar desde el que se inició. En un trabajo masivo, el número que sigue al tipo es el número del trabajo.
- **View** abre el prompt enviado y la respuesta recibida en una ventana de esta página. Una fila con error muestra el error en lugar de la respuesta.
- Filtros: fechas, **Model**, tipo, estado, idioma, empleado y una palabra en el prompt o en la respuesta. Los botones **Previous** y **Next** cambian de página.
- **HTTP 401** o **HTTP 403** significa que la clave de **Settings** es incorrecta o que la cuenta no tiene acceso al modelo elegido.
- **Clear history** borra estas entradas, y las traducciones guardadas se conservan. La pregunta antes de borrar es: “Clear the stored history? Saved translations stay.”

Esta página no envía ninguna petición nueva ni cambia traducciones. Si las traducciones dejan de funcionar de repente, mire primero la fila con error más reciente antes de cambiar el glosario.

### 3.11 Updates

La pestaña **Updates** muestra la sección **MyPresta Updates**. El botón **Check Now** junto a **Manual Check** comprueba al momento si existe una versión más nueva del módulo. El campo **Automatic Notifications** (**Enabled** o **Disabled**) decide si el módulo comprueba por sí solo. Guarde su elección con **Save**.

Cuando las notificaciones automáticas están activadas, el módulo comprueba la versión cada 3 días, al abrir el back office. Envía al servidor de MyPresta el nombre del módulo, su versión, la dirección de la tienda y el identificador de licencia, si está guardado. Desactivar esta opción detiene estas comprobaciones automáticas.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

### 3.12 Botones junto a los campos de los formularios de la tienda

Junto a los campos multilingües de los formularios de productos, categorías, CMS y otros formularios del back office aparece un botón de traducción. Cuando hay campos marcados, aparece además una barra en la parte inferior del formulario.

![Producto – traducción de un campo](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Producto – campos meta](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Producto – barra de traducción](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Formulario de categoría con la barra de traducción](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**La barra** de la parte inferior tiene los campos **Source** y **Target** y los botones **Check all**, **Uncheck all**, **Check empty**, **Translate empty** y **Translate selected**. El contador **Selected** muestra cuántos campos están marcados.

El botón junto a un campo solo rellena ese campo. Para que el cambio quede en la tienda, haga clic en el botón **Save** de PrestaShop al final del formulario. La barra funciona igual: rellena los campos marcados y exige guardar el formulario.

Mensajes de la barra:

- “Fill the source language field first.” — el campo de origen está vacío. Escriba texto en el idioma de origen e inténtelo de nuevo.
- “Tick at least one field.” — no hay ningún campo marcado.
- “Target is not a language from this shop.” — el idioma de destino elegido no pertenece a la tienda.
- “Translating…” y “Done” — traducción en curso o terminada.

Los botones y la barra desaparecen cuando los interruptores de **Settings** están desactivados. En los formularios de la tienda, los interruptores **shop forms** los controlan.

### 3.13 Página International → Translations

En la página International → Translations aparece un botón de traducción junto a cada campo, y en la parte inferior, la misma barra. La barra tiene el campo **Source** (en-US por defecto) y el campo **Target**. Elija el idioma que quiere completar.

![Página International → Translations](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- El botón junto a un campo lo rellena con la traducción. Solo el botón **Save** de PrestaShop en esta página lo guarda.
- La barra traduce los campos marcados uno a uno.
- **Translate empty in this section** traduce los campos vacíos de la sección abierta.
- En la sección **Emails** el módulo lee el archivo de origen de la plantilla. Si no lo encuentra, aparece el mensaje: “The source language mail file was not found.” Entonces elija otro idioma de origen en **Settings**.
- El mensaje “The source language field is not on this page.” significa que en esta página no hay campo de idioma de origen. Abra otra pestaña o sección que tenga ese idioma.

Los interruptores **Individual field buttons** e **Individual field checkboxes — International → Translations** en **Settings** ocultan los botones y la barra solo en esta página.

## 4. Tienda online

El módulo no muestra nada a los clientes. No añade ninguna página, bloque, botón ni mensaje en la tienda online, así que el tema no muestra ningún efecto del módulo y no se hace ninguna captura de la tienda. Los clientes no tienen ningún paso en el módulo.

La única dirección por la que un servidor externo puede llamar al módulo es la dirección cron de **Settings**. No está pensada para los clientes. La usa el servidor para procesar trabajos.

Lo que verá al abrir esta dirección en el navegador:

| Lo que ve | Qué hacer |
|---|---|
| El texto `{"ok":false,"error":"Forbidden"}` | La dirección es incorrecta o su token ha caducado. Copie de nuevo la CRON URL desde **Settings** y péguela en la programación. |
| El texto `{"ok":true,"message":"No pending jobs"}` | No hay ningún trabajo en espera. Es normal y no hay que hacer nada. |
| El texto `{"ok":true,...}` con datos de un fragmento | Se procesó un fragmento. Verá los detalles en **Jobs**. |
| El texto `{"ok":false,"error":"..."}` con un mensaje | Lea el mensaje y vaya al apartado 5 de este manual. |

## 5. Problemas

**No hay ninguna entrada en el menú International.** La causa habitual es la caché de la tienda. Vaya a **Advanced Parameters → Performance** y haga clic en **Clear cache**. Si la entrada sigue sin aparecer, desinstale el módulo y vuelva a instalarlo. La desinstalación elimina los ajustes y el historial de trabajos, así que guarde antes su clave API y sus ajustes.

**“Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.”** No se introdujo la clave o se eliminó. Abra **Settings**, pegue la clave de su cuenta de DeepSeek, haga clic en **Save** y después en **Test connection**.

**“No DeepSeek API key. Nothing was translated.”** Es el mismo caso: pegue la clave en **Settings** y guarde.

**“Settings saved. No API key is stored, so nothing can be translated until you paste one.”** Los ajustes se guardaron sin clave. Pegue la clave y guarde de nuevo.

**Test connection falla, o History muestra HTTP 401 o 403.** La clave es incorrecta o caducada, o la cuenta no tiene acceso al modelo elegido. Pegue la clave de nuevo. Si el error afecta al modelo, elija otro de la lista o añada un identificador válido en **Add a DeepSeek model**.

**“DeepSeek rate limit (429). Try again later.”** DeepSeek limitó el número de llamadas. Espere unos minutos y reanude el trabajo en **Jobs** con **Resume** y **Process slice**. Si el error vuelve, baje **Batch size** en **Settings**.

**“Rate limit — job auto-paused. Resume later.”** El trabajo se pausó solo tras demasiadas llamadas rechazadas. Pasado un rato, haga clic en **Resume** en el trabajo y después en **Process slice** o **Auto-process**.

**“Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.”** El trabajo espera un inicio manual o la llamada cron. Haga clic en **Process slice** o **Auto-process**. Para que los trabajos se ejecuten sin hacer clic, añada la CRON URL a la programación del servidor y llámela con regularidad.

**“Monthly API budget has been exhausted.”** Se alcanzó el límite mensual **Budget USD / month**. Abra **Settings**, suba el importe o ponga 0 para quitar el límite. Las nuevas traducciones se reanudan cuando se continúe el trabajo.

**“Allow publish is off in Settings.”** El guardado de traducciones está bloqueado. Abra **Settings** y active **Allow publish / save**. Sin esto, **Process slice** no guardará texto en la tienda.

**“Not saved because of broken placeholders or HTML: N.”** N filas no se guardaron porque el modelo cambió un marcador o una etiqueta HTML. Abra **Review** o la tabla de **Manual**, corrija la propuesta y guarde de nuevo, o rechace la fila.

**El trabajo terminó con el estado completed_with_errors.** Algunas cadenas fallaron. En **Jobs** active el filtro **Failed only**, descargue el **Error CSV** y haga clic en **Retry failed** para reintentar las cadenas fallidas.

**Una traducción no se puede deshacer.** **Rollback** restaura solo las traducciones para las que el módulo guardó una copia de seguridad antes del cambio. Las copias pertenecen al trabajo. Desaparecen cuando se desinstala el módulo.

**La traducción está guardada, pero la página muestra el texto antiguo.** Limpie la caché: **Advanced Parameters → Performance → Clear cache**. En los formularios de la tienda y en International → Translations, recuerde que los botones y la barra solo rellenan los campos. Los guarda el botón **Save** de PrestaShop.

**Los botones de traducción no aparecen junto a los campos.** Los interruptores están desactivados. Abra **Settings** y active el interruptor correspondiente: **Individual field buttons** o **Individual field checkboxes** para los formularios de la tienda, o para International → Translations.

**“Fill the source language field first.”** El campo del idioma de origen está vacío. Escriba texto en ese idioma e inténtelo de nuevo.

**“The source language mail file was not found.”** No hay archivo en el idioma de origen para esta plantilla de correo. Elija otro **Source locale** en **Settings** o traduzca la plantilla a mano.

**Tras Start job no pasa nada.** Start job solo crea el trabajo y no lo ejecuta. Abra **Jobs** y haga clic en **Process slice** o **Auto-process**.

**El correo sobre un trabajo terminado no llega.** Compruebe que **Email notify on complete** esté activado y que la dirección de **Notify email** sea correcta. Un campo vacío envía a la dirección de la tienda. El correo se envía solo cuando termina el trabajo. Compruebe también que la tienda envía correos en **Advanced Parameters → E-mail**.

**No se puede cancelar un trabajo.** Esta versión del módulo no tiene botón de cancelar en la pantalla del trabajo. Detenga el trabajo con **Pause** y no lo reanude.

**History está vacío o muestra “No requests yet.”** Todavía no se ha hecho ninguna llamada a DeepSeek. El Dashboard también muestra ceros hasta que ejecute una traducción.

## 6. Para desarrolladores

Esta sección describe el código del módulo. Las claves de configuración y los nombres de clase aparecen solo aquí.

### 6.1 Resumen

- **Clase principal:** `myaitranslationsdeepseek` (extiende `Module`), archivo `myaitranslationsdeepseek.php`.
- **Nombre técnico:** `myaitranslationsdeepseek`. El prefijo de las claves de configuración y de las tablas es `MYAITDS_` y `myaitds_`.
- **Versión:** 1.2.0.
- **Nombre en la lista de módulos:** AI Translations with DeepSeek.
- **Autor en el código:** MyPresta.eu. Pestaña: `administration`.
- **Compatibilidad:** PrestaShop de 1.7.0.0 a 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Pestaña de menú:** clase `AdminMyaitranslationsdeepseek`, padre `AdminInternational` (alternativa: `IMPROVE`).

Flujo de datos: los ajustes los lee `MyaitdsConfigService` desde `Configuration` (claves `MYAITDS_*`). Los servicios `MyaitdsTranslateService`, `MyaitdsJobWorker` y `MyaitdsCatalogTranslateService`, y el controlador del back office, llaman a `MyaitdsDeepSeekTranslationProvider`, que envía una petición cURL a `https://api.deepseek.com/chat/completions` (timeout de 120 s, timeout de conexión de 15 s). La respuesta pasa por los validadores (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) y por `MyaitdsQualityScorer`. El guardado va a través de `MyaitdsTranslationAdapterFactory` al servicio de traducciones de PrestaShop, y a la tabla `translation` si el servicio no está disponible. En los módulos clásicos el guardado va al `translations/{iso}.php` del propio módulo. Las llamadas se registran en `myaitds_request` y `myaitds_api_log`, y los costes en `myaitds_usage_ledger`. La memoria de traducciones (`myaitds_memory`) permite omitir una llamada a la API para el mismo origen, idioma, modelo y versión del glosario.

### 6.2 Archivos

| Archivo | Finalidad |
|---|---|
| `myaitranslationsdeepseek.php` | Clase principal: instalación, desinstalación, pestaña de menú, hooks del back office, la redirección `getContent()` al controlador. |
| `sql/install.php` | Crea las 11 tablas (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Elimina las 11 tablas (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Controlador del back office: todas las pestañas, acciones de formularios, acciones de trabajos y peticiones AJAX. |
| `controllers/front/cron.php` | Controlador de front `cron`: procesa un fragmento de un trabajo. |
| `src/Admin/MyaitdsForms.php` | Formularios HelperForm y sus textos `desc`. |
| `src/Admin/MyaitdsSectionHelp.php` | Texto de ayuda de cada pestaña. |
| `src/Service/MyaitdsConfigService.php` | Lee y escribe `MYAITDS_*`, la lista de modelos, los rangos de valores y la clave API. |
| `src/Service/MyaitdsTranslateService.php` | Traducción manual y con botones: memoria, presupuesto, validación, guardado. |
| `src/Service/MyaitdsBulkJobFactory.php` | Estimación y creación de trabajos masivos. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Campos de productos, categorías y CMS, bloques de como máximo 100 registros. |
| `src/Service/MyaitdsDashboardService.php` | Cálculo de la cobertura (textos que faltan y traducidos). |
| `src/Service/MyaitdsRateLimiter.php` | Límite de llamadas por minuto, guardado en `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Procesa fragmentos, guarda, snapshots, cola de revisión, correo de finalización. |
| `src/Job/MyaitdsJobRepository.php` | Lee y escribe trabajos y sus cadenas. |
| `src/Job/MyaitdsJobStatuses.php` | Constantes de los estados de trabajos y cadenas. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | Llamada a la API de DeepSeek (cURL), gestión de errores y códigos HTTP. |
| `src/Provider/MyaitdsPromptBuilder.php` | Construye el prompt con tono, voz de marca y glosario. |
| `src/Provider/MyaitdsProviderFactory.php` | Crea el proveedor (actualmente solo DeepSeek). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Interfaz del proveedor de traducción. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Interfaz de acceso al catálogo de PrestaShop. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Lógica común: secciones, dominios, guardado, limpieza de caché. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Exploración de archivos XLF y directorios de traducción. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Lee y escribe `translations/{iso}.php` de los módulos clásicos. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Implementación concreta del adaptador (extiende el adaptador abstracto). |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Crea el adaptador. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Comprueba los marcadores en la traducción. |
| `src/Quality/MyaitdsHtmlValidator.php` | Comprueba las etiquetas HTML. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Combina la comprobación de marcadores y HTML. Usa las clases de PrestaShop (`Validate::isCleanHtml`) cuando están disponibles. |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Protege de la traducción las etiquetas y variables de las plantillas de correo. |
| `src/Quality/MyaitdsQualityScorer.php` | Puntuación 0–100, marcas y decisión de cola de revisión (umbral 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Lee y escribe el glosario. La importación y exportación CSV están en el controlador. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Patrones de exclusión. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Historial de llamadas (**History**): guardado, filtros, vista y limpieza según la retención. |
| `src/Audit/MyaitdsApiLogRepository.php` | Registro de la API y su retención. |
| `src/Audit/MyaitdsTranslationMemory.php` | Memoria de traducciones (hash de origen, idioma, modelo y glosario). |
| `src/Audit/MyaitdsUsageLedger.php` | Consumo mensual y costes, origen del presupuesto. |
| `src/Audit/MyaitdsSnapshotService.php` | Valores anteriores a un cambio y su restauración (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | Cifrado de la clave API (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Estructura del panel con pestañas. |
| `views/templates/admin/_partials/*.tpl` | Contenido de las pestañas: dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Lógica del back office: trabajos, procesado automático, formularios. |
| `views/js/admin-help.js` | Ventanas de ayuda de las pestañas. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Gráficos del **Dashboard**. |
| `views/js/entity-fields.js` | Botones y barra junto a los campos de formularios de la tienda. |
| `views/js/translations-tool.js` | Botones y barra en International → Translations. |
| `views/css/admin.css` | Estilos del panel y de los botones. |
| `lib/updateChecker.php` | Comprobación de versiones con MyPresta y pestaña **Updates**. |
| `translations/*.php` | Traducciones del módulo (27 idiomas, incluido `pl.php`). |
| `var/rate_limit.json` | Estado del límite de llamadas por minuto. |
| `logo.png`, `logo.gif` | Logotipo en la lista de módulos y en el panel. |

### 6.3 Controladores

**Back office:** `AdminMyaitranslationsdeepseekController`, pestaña `AdminMyaitranslationsdeepseek`, padre `AdminInternational`. La pestaña se elige con el parámetro `myaitds_tab`. Valores permitidos: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (la pestaña **History**), `review`, `catalog` y `updates`. Cualquier otro valor abre `dashboard`. El controlador no define permisos propios, así que se aplican los permisos de pestaña configurados en PrestaShop.

Acciones de formulario (`Tools::isSubmit`): `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

Acciones GET: `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors`; `cancel` está implementada, pero ninguna plantilla crea un enlace a ella), `review_action` (`approve`, `reject`) con `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

Acciones AJAX (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), atendidas por los métodos `displayAjax*`: `HistoryDetail` (detalle de una fila del historial, parámetro `hist_id`), `ProcessJob` (un fragmento, `id_job`), `JobStatus` (estado del trabajo), `TranslatePageLines` (líneas de la página de traducción), `MailSource` (archivo de origen de una plantilla de correo), `ListDomains` (dominios de una sección).

**Front:** `MyaitranslationsdeepseekCronModuleFrontController` en `controllers/front/cron.php`. La dirección tiene la forma `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Ajustes del controlador: `$ssl = true`, `$ajax = true`. Parámetros: `token` (obligatorio, se compara con `MYAITDS_CRON_TOKEN` mediante `hash_equals`) y `id_job` opcional. Sin `id_job`, el módulo toma el primer trabajo con estado `pending` o `running` entre los 20 más recientes. Un token incorrecto devuelve HTTP 403 con `{"ok":false,"error":"Forbidden"}`. Sin trabajos devuelve `{"ok":true,"message":"No pending jobs"}`. Un fragmento procesado devuelve el resultado de `processSlice`.

### 6.4 Hooks

Registrados en la instalación:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: renombra la pestaña si el nombre sigue siendo técnico, y carga los recursos del back office.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: carga los mismos recursos.

`loadBoAssets()` funciona así: en la pestaña `AdminMyaitranslationsdeepseek` añade `admin.css`, `admin.js`, `admin-help.js`, y en **Dashboard** también `chart.min.js` e `history-charts.js`. En la página `AdminTranslations` añade `translations-tool.js` cuando los botones o la barra de International → Translations están activados (`MYAITDS_TR_BUTTONS` o `MYAITDS_TR_BULK`). En el resto de páginas del back office añade `entity-fields.js` cuando los botones o la barra de los formularios de la tienda están activados (`MYAITDS_ENTITY_BUTTONS` o `MYAITDS_ENTITY_BULK`). Pasa la configuración mediante `Media::addJsDef` como `myaitdsTr` y `aitHelpLabels`.

El módulo **no expone** hooks propios: no llama a `Hook::exec` y no registra hooks de front.

El módulo **no tiene** métodos `enable()` ni `disable()`. Activar y desactivar no ejecuta ninguna acción del módulo. PrestaShop elimina los hooks al desinstalar.

### 6.5 Sobrescrituras

El módulo no tiene directorio `override/` y no sobrescribe ninguna clase ni controlador de PrestaShop.

Archivos que escribe el módulo: las traducciones pasan por el servicio de traducciones de PrestaShop (`prestashop.service.translation`), y por la tabla `translation` si el servicio no está. En los módulos clásicos (claves con formato `<{nombre}>prestashop`) el módulo reescribe el `translations/{iso}.php` de ese módulo, primero en un archivo temporal y después renombrándolo. Limpia la caché con `Tools::clearCache()`. También escribe `var/rate_limit.json` y los valores `update_<módulo>`, `updatev_<módulo>` y `mypresta_updates` en `Configuration`.

### 6.6 Base de datos

Las tablas usan el prefijo de la tienda (`_DB_PREFIX_`). Todas se crean con el motor `_MYSQL_ENGINE_` y la intercalación `utf8mb4_unicode_ci`.

| Tabla | Contenido |
|---|---|
| `myaitds_glossary` | Términos del glosario: `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, fechas. Índice `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Patrones de exclusión: `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Trabajos: `uuid` (único), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, contadores `items_*`, tokens, `cost_usd_estimate` y `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Cadenas de un trabajo: `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Memoria de traducciones: `memory_hash` (único), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Consumo diario: `usage_date`, `id_myaitds_job`, `model`, tokens, `cost_usd`. Origen del presupuesto mensual. |
| `myaitds_snapshot` | Valores anteriores a un cambio: `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. Origen de **Rollback**. |
| `myaitds_api_log` | Registro de la API: `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Se limpia según `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Historial de llamadas (**History**): tipo, estado, modelo, idiomas, código HTTP, duración, tokens, coste, `prompt`, `reply`, `error_message`. Se limpia según la retención. |
| `myaitds_review` | Cola de revisión: `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Se crea en la instalación, pero ningún código escribe en ella ni lee de ella. |

La instalación crea las tablas solo con `CREATE TABLE IF NOT EXISTS`. El módulo no añade columnas al abrir una página (en el código no hay `ALTER TABLE`).

La desinstalación elimina las 11 tablas. Una reinstalación las crea vacías.

### 6.7 Claves y traducciones

**Claves de configuración** (prefijo `MYAITDS_`) y valores iniciales de `installDefaults()`:

| Clave | Valor inicial | Notas |
|---|---|---|
| `API_KEY_ENC` | `''` | Clave cifrada con AES-256-CBC; la clave de cifrado se deriva de `_COOKIE_KEY_`. |
| `MODEL` | `deepseek-flash` | El modelo de las llamadas. |
| `EXTRA_MODELS` | `''` | Identificadores de modelo añadidos (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | El único proveedor. No tiene campo en el panel. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Texto de la voz de marca. |
| `BATCH_SIZE` | `25` | Rango 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = sin límite. |
| `SOURCE_LOCALE` | `''` | Vacío significa que la pantalla proporciona el origen. Valor de respaldo en el código: `en-US`. |
| `TEMPERATURE` | `0.2` | Rango 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Rango 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | El campo del formulario se llama `MYAITDS_RATE_LIMIT`. 0 desactiva el límite. |
| `LOG_RETENTION_DAYS` | `30` | Mínimo 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Interruptor del correo. |
| `NOTIFY_EMAIL` | `''` | Vacío = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Bloquea el guardado desde **Manual**, trabajos y **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Botones y barra junto a los campos de formularios de la tienda. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Botones y barra en International → Translations. |
| `MAX_TOKENS` | `0` | 0 = límite predeterminado de DeepSeek. |
| `CRON_TOKEN` | 16 bytes aleatorios (hex) | Token de la dirección cron. |

Al desinstalar se eliminan las claves anteriores, además de `DEEPL_API_KEY` y `CLAUDE_API_KEY`, que el módulo ya no usa.

**Textos que no pasan por `$this->l()`.** Los textos de campos y ayuda pasan por `l()` en los dominios `myaitdsforms` (`MyaitdsForms`) y `sectionhelp` (`MyaitdsSectionHelp`). Las etiquetas de JavaScript van a `Media::addJsDef` mediante `translationClientConfig()`. El asunto y el texto del correo de finalización están en inglés en `MyaitdsJobWorker::notifyComplete()` y no pasan por `l()`. Los mensajes que se muestran con `$this->module->l()` en el controlador usan el dominio `adminmyaitranslationsdeepseekcontroller`.

**Añadir un idioma:** cree un archivo `translations/{iso}.php` siguiendo el modelo de los existentes (por ejemplo `translations/pl.php`). PrestaShop carga el archivo que coincide con el código ISO de la tienda.

**Origen de los textos de los campos:** `MyaitdsForms::help()` (el `desc` de cada campo) y `MyaitdsSectionHelp::pages()` y `brief()` (el texto de ayuda de las pestañas).

### 6.8 Extensión

- **Tema:** no hay nada que sobrescribir. El módulo no renderiza plantillas de front.
- **Plantillas del back office:** `views/templates/admin/`. Los cambios en los archivos del módulo se pierden al actualizarlo.
- **Nuevos modelos de DeepSeek:** no requieren cambios de código; use **Add a DeepSeek model** (`EXTRA_MODELS`).
- **Nuevo proveedor:** implemente `MyaitdsTranslationProviderInterface` y añada una entrada en `MyaitdsProviderFactory`.
- **Umbral de la cola de revisión:** 70 puntos, definido en `MyaitdsQualityScorer::score()`.
- **Glosario y exclusiones:** se gestionan en el panel, sin cambios de código.

## 7. Ayuda

Página del módulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Inicie sesión en su cuenta de cliente en mypresta.eu, vaya a contacto y elija el tema **Support for paid modules**. El formulario indica que para los módulos de pago es necesario iniciar sesión. Tras iniciar sesión, seleccione este módulo de su historial de compras.
