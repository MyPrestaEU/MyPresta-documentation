---
title: "AI Translations with ChatGPT - documentación y manual de usuario"
description: "Configuración y resolución de problemas para tiendas que ya tienen AI Translations with ChatGPT."
sidebar:
  label: "AI Translations with ChatGPT - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with ChatGPT en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.7.0.0 y posteriores, incluidas PrestaShop 8 y 9.

- **PrestaShop:** 1.7.0.0 o posterior.
- **PHP:** 5.6 o posterior.
- **Extensiones de PHP:** cURL, OpenSSL, SimpleXML y mbstring.
- **Otros módulos:** este módulo no necesita otro módulo.
- **Fuera de la tienda:** una cuenta de OpenAI y una clave de API. El servidor de la tienda debe poder abrir `https://api.openai.com/v1/chat/completions`.
- **Opcional:** una tarea programada en el servidor que abra la dirección cron de **Settings**. Sin ella, usted procesa los trabajos en **Jobs**.
- **Catálogos grandes:** un dominio con miles de cadenas son muchas llamadas a la API. El trabajo se divide en trozos del tamaño de **Batch size**. Ejecute **Estimate** en **Bulk** antes de empezar.
- La tienda necesita al menos dos idiomas. Con un solo idioma el back office muestra **The shop needs at least two languages.** y no hay nada que traducir.

## 2. Instalación

1. Abra **Modules** y después **Module Manager**. Elija **Upload a module**, suba el ZIP y pulse **Install** en **AI Translations with ChatGPT**.
2. Tras la instalación, **AI Translations with ChatGPT** aparece en el menú **International**.
3. La instalación no vacía la caché de la tienda. El módulo vacía la caché cuando guarda una traducción.

Abra **AI Translations with ChatGPT**, después **Settings**, y pegue la clave de ChatGPT. Mientras no haya una clave guardada, cada página del módulo muestra **No ChatGPT API key.** y el enlace **Open Settings**.

**Desinstalación.** En **Module Manager**, pulse **Uninstall** y confirme **Delete this module and its data (jobs, glossary, cache)?**

- La entrada del menú desaparece. Se borran los trabajos, el glosario, los patrones de exclusión, el historial de llamadas, la cola de **Review**, las copias para deshacer, el libro de costes y los ajustes del módulo (incluida la clave de API).
- El texto que el módulo ya escribió en la tienda permanece: traducciones del catálogo y los archivos de traducción de los módulos clásicos que este módulo escribió. También permanece la elección de la comprobación de actualizaciones.
- Una instalación nueva no recupera los trabajos, el glosario ni el historial borrados. Pone los valores por defecto y crea una dirección cron nueva.

## 3. Configuración y trabajo diario

Todo el módulo es una página: **International** y después **AI Translations with ChatGPT**. Las pestañas son **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** y **Settings**. **Updates** está al final de la barra. **Help** abre un panel de la pestaña en la que está.

Los nombres de botones y campos de este manual son los del back office en inglés. En otro idioma del panel verá la traducción del mismo control. Las capturas son del back office en inglés.

Un uso normal tiene cuatro partes.

1. **Conexión.** En **Settings**, pegue la clave, elija el modelo y pulse **Test connection** y después **Save**.
2. **Una prueba pequeña.** En **Manual**, filtre un dominio, marque unas cadenas vacías y tradúzcalas. Compruebe el resultado antes de lanzar un catálogo entero.
3. **Un trabajo.** En **Bulk**, elija la sección, los idiomas y los dominios, pulse **Estimate** y después **Start job**. Abra el trabajo y pulse **Process slice** o **Auto-process**, o deje que la dirección cron lo llame.
4. **Una revisión.** Abra **Review** para las filas que retuvo el control de calidad, e **History** cuando falle una llamada. **Rollback** en el trabajo restaura el texto anterior donde el módulo guardó una copia.

El módulo no empieza una traducción por sí solo. **Estimate**, **Filter** y **Save** en **Settings** no escriben texto del catálogo. Un trabajo permanece en **Jobs** hasta que usted lo procesa o se llama a la dirección cron.

### 3.1. Configuración del módulo

Abra **Modules**, **Module Manager**, busque **AI Translations with ChatGPT** y pulse **Configure**. Se abre **Dashboard**. Vaya a **Settings**.

**Save** y **Test connection** están al final del formulario. Guardar este formulario no inicia una traducción y no reescribe traducciones ya guardadas.

![Ajustes, back office en inglés. Parte superior del formulario: ChatGPT API key, Model, Add a ChatGPT model, Tone y Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Conexión**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **ChatGPT API key** | vacío | El secreto que esta tienda envía a ChatGPT. Pegue la clave de su cuenta de OpenAI. Deje el cuadro vacío para conservar la clave ya guardada. Un valor nuevo sustituye la clave guardada. Un cuadro vacío no la borra. Cuando hay una clave guardada, la ayuda muestra **Key saved:** y una clave enmascarada. |
| **Model** | gpt-4.1-mini | El modelo de ChatGPT que escribe la traducción. Los nombres integrados permanecen en la lista: gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini y o1-mini. La siguiente traducción usa el modelo elegido. Un modelo que la cuenta no puede usar hace fallar la llamada, y el error queda en **History**. |
| **Add a ChatGPT model** | vacío | Escriba el identificador exacto de la cuenta de OpenAI y pulse **Add model**. El texto de ejemplo del cuadro es gpt-4.1. El identificador nuevo aparece en **Model** y pasa a ser el modelo activo. **Remove** borra solo los identificadores añadidos aquí. Los identificadores integrados no se pueden borrar. |

Mensajes: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Voz y origen**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Tone** | Formal | Añade una instrucción de estilo a cada prompt. **Formal** es para el texto de la tienda y del back office, **Casual** es más ligero y **Brand** se usa junto con **Brand voice**. Las traducciones nuevas siguen ese estilo. Las existentes permanecen hasta que las vuelva a ejecutar. |
| **Brand voice** | vacío | Visible cuando **Tone** es **Brand**. Unas frases sencillas sobre cómo debe sonar la tienda, o un cuadro vacío. El texto entra en el siguiente prompt. Vacío significa que no hay voz extra. No reescribe traducciones ya guardadas. |
| **Source locale** | vacío | El idioma que el modelo trata como original. La opción vacía es un guion en la lista: la pantalla que traduce aporta el origen. Elija la configuración regional en la que están escritos sus catálogos, normalmente en-US. **Manual**, **Bulk** y los iconos de **International → Translations** envían esa configuración como origen. El idioma predeterminado de la tienda no cambia. |
| **Individual field buttons — shop forms** | Yes | Un botón en cada campo multidioma de los formularios de la tienda: producto, categoría, CMS y los demás formularios del back office. El botón traduce solo ese campo. **No** oculta esos botones en toda la tienda. Las traducciones guardadas no cambian. |
| **Individual field checkboxes — shop forms** | Yes | Cada uno de esos campos recibe una casilla, y la barra traduce solo los campos que marque. **No** oculta las casillas y la barra. Los botones de arriba siguen su propio interruptor. |
| **Individual field buttons — International → Translations** | Yes | Un botón en cada campo de **International → Translations**. **No** oculta esos botones. Los formularios de la tienda no se ven afectados. Un clic rellena ese campo. **Save** de PrestaShop sigue escribiendo la página. |
| **Individual field checkboxes — International → Translations** | Yes | Casillas y barra en **International → Translations**. **No** las oculta. Los formularios de la tienda no se ven afectados. |

**Límites**

![Ajustes, back office en inglés. Batch size y los campos de límite que hay debajo.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Batch size** | 25 | Cuántas cadenas se envían en una llamada a la API. Use de 10 a 25 en la primera pasada. El valor se mantiene entre 1 y 100. Un lote mayor termina un trabajo con menos llamadas. Un fallo reintenta entonces un trozo mayor. |
| **Dry-run sample** | 10 | Cuántas cadenas de ejemplo muestra **Estimate** antes de un trabajo masivo. El valor se mantiene entre 1 y 50. **Estimate** no escribe traducciones. |
| **Max tokens (0 = default)** | 0 | El formulario guarda este número. La petición de traducción no lo envía, así que no acorta la respuesta y no detiene una respuesta cortada. La prueba de conexión usa su propia petición corta. Las traducciones ya guardadas no se recortan. |
| **Budget USD / month** | 0 | Un techo mensual en dólares de EE. UU., contado desde el libro de uso. 0 significa que no hay techo. Cuando el libro alcanza la cantidad, las traducciones nuevas se detienen. Lo ya guardado permanece. |
| **Rate limit / min** | 60 | Cuántas llamadas a la API puede iniciar esta tienda en un minuto. 0 apaga este límite local. Las llamadas por encima del límite se omiten y se anotan en **History**. ChatGPT puede seguir aplicando su propio límite. |
| **Log retention days** | 30 | Cuántos días de filas se conservan en **History**. Como mínimo 1. Las filas más antiguas se eliminan. Este número no borra trabajos, el glosario ni las traducciones guardadas. |
| **Temperature** | 0.2 | Con qué libertad puede reformular el modelo. Alrededor de 0,2 se queda cerca del origen. Los valores cercanos a 1 varían más las frases. El valor guardado se mantiene entre 0 y 1. Los marcadores y el HTML se comprueban después. La petición de traducción envía este valor para cada modelo de la lista, también para un identificador que usted añada. |
| **Allow publish / save** | Yes | Si este módulo puede escribir una traducción en PrestaShop. **No** bloquea el guardado en **Manual**, en los trabajos masivos y en **Catalog**. Los iconos de la página de traducciones y de los formularios de la tienda solo rellenan el formulario. **Save** de PrestaShop es aparte. |

Después de **Save**:

- **Settings saved. No translation was started.** Los ajustes quedan guardados y no se tradujo nada.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Pegue una clave en **ChatGPT API key** y pulse **Save** otra vez.

**Correo y cron**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Email notify on complete** | No | Envía un correo cuando termina un trabajo masivo. El trabajo se ejecuta de todos modos. Solo se añade o se omite el correo. |
| **Notify email** | vacío | La dirección que recibe ese correo. El campo solo se muestra cuando el interruptor de arriba está activado. Guardar la dirección no envía un mensaje por sí solo. |
| **CRON URL** | una dirección con token | Una dirección secreta con la que el servidor puede procesar un trozo de un trabajo en espera. Cópiela en el programador del servidor. No la publique. Quien tenga la dirección puede iniciar un trozo. Abrir **Settings** no inicia un trabajo. |

**Test connection** comprueba la clave y el modelo con una petición corta. No traduce y no guarda.

- **Connection OK (N ms). No translation was started.** La conexión funciona.
- **Connection was not made. Nothing was translated.** seguido del motivo. Compruebe la clave y el modelo. El detalle está en **History**.

Un inicio práctico: pegue la clave, elija el modelo y la configuración de origen, pulse **Test connection** y después **Save**. Deje los números en los valores de instalación hasta que un trabajo se comporte mal.

### 3.2. Dashboard

Abra la pestaña **Dashboard**. Cuenta las cadenas de catálogo que faltan y después muestra el uso de ChatGPT en tarjetas, gráficos y los diez prompts más recientes. La página no traduce y no cambia cadenas.

![Dashboard, back office en inglés. Cobertura de una configuración regional, la línea cron y los filtros del historial.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Cobertura**

- **Locale:** la configuración regional de la tienda cuyas cadenas faltantes se cuentan.
- **Show:** vuelve a dibujar la tabla para esa configuración.
- Columnas: **Section**, **Total**, **Missing**, **Done** y una barra de progreso. Las secciones son **Back office**, **Themes**, **Installed modules**, **Emails** y **Others**. **Missing** es el número de cadenas sin traducción en esa configuración.
- Debajo de la tabla, **CRON** muestra la misma dirección que **CRON URL** en **Settings**.
- Una tabla vacía significa que la tienda aún no tiene catálogo para esa configuración. Créelo en **International → Translations**.

Después de **Show**, el mensaje es **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Uso**

- Preajustes: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtros: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** y **Prompt or reply contains**. Pulse **Filter**.
- Tarjetas: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** y **Estimated cost**. El coste estimado es un cálculo local, no una factura de OpenAI.
- Gráficos: **Requests and errors**, **Tokens sent and received**, **Requests by model**. Debajo, los grupos **By day**, **By model**, **By type**, **By language** y **By employee**, con las columnas **Group**, **Calls**, **Sent**, **Received** y **Total**. Un grupo vacío dice **No requests in this range.**
- **Latest prompts** lista diez llamadas. **View** abre el prompt y la respuesta. **See all** abre **History** (3.10). Una lista vacía dice **No requests yet.**

Filtrar no borra el historial y no cambia las traducciones.

Si una sección está casi vacía, abra **Manual** para unas cadenas o **Bulk** para un dominio entero.

### 3.3. Manual

Abra **Manual**. Traduce un dominio, o un módulo clásico, unas decenas de cadenas cada vez. Filtrar no guarda nada.

![Manual, back office en inglés. Section, Source, Target, Domain, Only empty y Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Section** | Back office | Qué catálogo se lee: **Back office**, **Themes**, **Installed modules**, **Emails** u **Others**. Cambiar la sección recarga la página y muestra solo los campos de esa sección. No llama a ChatGPT. |
| **Theme** | vacío | Solo se muestra para **Themes**. Limita la lista a un tema. |
| **Module** | vacío | Solo se muestra para **Installed modules**. Limita la lista a un módulo. Un módulo clásico sin dominio carga cada cadena de ese módulo. |
| **Domain** | vacío | La misma agrupación que en **International → Translations**. Elíjalo y pulse **Filter**. Oculto para un módulo clásico y para una sección sin dominios. |
| **Source** | el **Source locale** de **Settings**, o en-US | El idioma del que se toman las cadenas. Elija un idioma que ya tenga un buen texto. |
| **Target** | el primer idioma de la lista | El idioma que quiere rellenar. Debe existir en **International → Localization → Languages**. |
| **Only empty** | Yes | Muestra solo cadenas sin traducción. Al apagarlo se muestra cada cadena. Las traducciones guardadas no se borran. |
| **Search** | vacío | Conserva solo las cadenas de origen que contienen la palabra que escribe. |

Pasos:

1. Fije **Section**, **Source** y **Target**.
2. Para **Themes**, elija **Theme**. Para **Installed modules**, elija **Module**.
3. Pulse **Filter**. La lista **Domain** se actualiza. Elija un dominio y pulse **Filter** otra vez. Para un módulo clásico, omita el dominio: **Filter** carga cada cadena del módulo.
4. Marque las filas. **Check all** y **Uncheck all** seleccionan o vacían la lista.
5. Pulse **Translate selected (review)**. Se abre una tabla **Review before save** con **Source**, **AI proposal** y **Warnings**. Desmarque las filas que no quiera. Edite la propuesta en el cuadro. Pulse **Save approved**.
6. O marque **Save now (skip review)** antes de traducir. Las filas válidas se escriben de inmediato, sin la tabla de revisión.

Las columnas de la lista de cadenas son **Source**, **Current** y **Status** (**empty** o **filled**).

Mensajes:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Esta es la lista de un módulo clásico.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Esas filas se omitieron. Corrija los marcadores y las etiquetas para que coincidan con el origen y guarde de nuevo.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Cambiar la sección muestra también una línea corta como **Section is Back office. Theme and module are not used.** junto con **Nothing was sent to ChatGPT.** El mismo patrón se usa para **Themes**, **Installed modules**, **Emails** y **Others**.

### 3.4. Bulk

Abra **Bulk**. Crea un trabajo para muchos dominios e idiomas. **Estimate** no guarda. **Start job** crea una fila en **Jobs**. No se escribe nada hasta que el trabajo se procesa y **Allow publish / save** está activado.

![Bulk, back office en inglés. Section, Source, Targets, Domains, Policy y Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Section** | Back office | Qué catálogo lee el trabajo. Las mismas opciones que en **Manual**. |
| **Theme** / **Module** | vacío | Solo se muestra para la sección correspondiente, como en **Manual**. |
| **Source** | el **Source locale** de **Settings**, o en-US | El idioma tratado como original. Cada destino se traduce desde ese idioma. |
| **Targets** | ninguno | Uno o más idiomas que rellenar. Mantenga Ctrl, o Cmd en un Mac, para elegir varios. Un clic simple sustituye la selección. |
| **Domains** | ninguno | Dominios incluidos en el trabajo. Mantenga Ctrl o Cmd. Los dominios que no seleccione no se traducen. Déjelos todos sin seleccionar solo si quiere un trabajo vacío. La excepción es un módulo clásico sin dominio: el trabajo cubre entonces ese módulo. |
| **Policy** | Fill empty | **Fill empty** envía solo cadenas sin traducción. **Overwrite all** envía cada cadena, incluidas las que ya tienen traducción, y puede sustituirlas. **Outdated if equals source** envía solo cadenas cuya traducción es idéntica al origen. |
| **Dry-run job** | No | ChatGPT se ejecuta de todos modos y el trabajo aparece en **Jobs**, pero las respuestas no se escriben en la tienda. |

Pasos:

1. Elija la sección, el origen, los destinos, los dominios y la política.
2. Pulse **Estimate**. La página muestra **Estimate**, el número de cadenas, una estimación de tokens, una estimación de coste y un **Sample**.
3. Si la estimación es aceptable, pulse **Start job**. **Jobs** se abre con el trabajo nuevo.
4. Procéselo en **Jobs** (3.5), o déjelo para la dirección cron.

Mensajes:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Abra **Jobs**. Cada fila es una ejecución de **Bulk**.

![Jobs, back office en inglés. La lista de trabajos vacía.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Columnas: **#**, **Status**, **Locales** (origen y después destinos), **Progress** (hechos/total), **Cost**, **Employee**, **Date** y **Open**. Una lista vacía dice **No jobs yet.**

Estados del trabajo, tal como aparecen en pantalla:

- `pending` - en espera. No empieza solo.
- `running` - en curso.
- `paused` - detenido hasta que lo reanude.
- `cancelled` - detenido. Las cadenas que aún esperaban no se tradujeron.
- `completed` - cada cadena procesada, sin fallos.
- `completed_with_errors` - terminado, y algunas cadenas fallaron.
- `failed` - el trabajo acabó con un error.

**La pantalla del trabajo**

**Open** muestra **Job #N**, el estado, el progreso (hechos/total), **failed**, **skipped**, el coste, el número de empleado y la etiqueta **dry-run** cuando el trabajo es de prueba. La barra de progreso se actualiza sola mientras el trabajo está abierto. La tabla de debajo tiene **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** y **Error**.

Estados de fila: `pending`, `processing`, `done`, `failed`, `skipped` (coincidió una exclusión, o la cadena ya estaba traducida) y `rolled_back`.

Botones:

- **Process slice** - un trozo del tamaño de **Batch size**, y después se detiene. Mensaje: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Cuando no queda nada: **The job has no more strings waiting.**
- **Auto-process** - repite trozos hasta que el trabajo termina o un error lo detiene. Se ejecuta en el navegador, así que la pestaña debe permanecer abierta. Cerrar la pestaña detiene el bucle. El trabajo permanece y se puede terminar con **Process slice** o con la dirección cron.
- **Pause** - mensaje: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - mensaje: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - las cadenas fallidas vuelven a la espera y el trabajo espera otra vez. Mensaje: **Retried N failed items.**
- **Rollback** - pregunta **Roll back this job?** y restaura la traducción anterior donde el módulo guardó una copia antes del cambio. Mensaje: **Rollback: restored N translations.**
- **Error CSV** - descarga las filas fallidas. Columnas: id, domain, locale, source, error.
- **Failed only** - muestra solo las filas fallidas.
- **Review queue** - abre **Review** (3.6).

La pantalla del trabajo no tiene botón Cancel. Use **Pause** para detener el trabajo que queda.

**Pausa automática**

Cuando ChatGPT rechaza llamadas por un límite de ritmo, el trabajo se pausa solo. La línea de error es **Rate limit — job auto-paused. Resume later.** Espere y después pulse **Resume**. **Rate limit / min** en **Settings** baja cuántas llamadas inicia la tienda en un minuto.

Otros mensajes en esta pantalla:

- **Nothing was translated.** seguido de **No ChatGPT API key. Nothing was translated.** Pegue la clave en **Settings**.
- **Allow publish is off in Settings.** Un trabajo que no es de prueba no se ejecuta hasta que active **Allow publish / save**.
- **Monthly API budget has been exhausted.** Suba **Budget USD / month**, o póngalo a 0.

### 3.6. Review

Abra **Review**, o pulse **Review queue** en un trabajo. La línea del título es **Needs-review queue (quality score / flags).** Lista las filas más recientes que el control de calidad no aprobó solo, hasta 100.

![Review, back office en inglés. La cola de revisión vacía.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Columnas: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, y después **Approve** y **Reject**. Una lista vacía dice **The queue is empty.**

Cómo leer una fila:

- **Score** va de 0 a 100. Por debajo de 70, la fila entra en la cola.
- **Flags:**
  - `validation_failed` - los marcadores o el HTML no pasaron el control.
  - `warning` - una nota menor del control.
  - `length_explosion` - la traducción es más de dos veces y media el origen.
  - `too_short` - la traducción es mucho más corta que un origen largo.
  - `possible_untranslated` - quedan palabras inglesas como the, and, with, your o please en la traducción.
- **Source** es el original. **AI** es la propuesta del modelo.

**Approve** y **Reject** solo cambian el estado de la fila. El mensaje es **Review updated.** La fila sale de la lista. Esta página no pega el texto en el catálogo por sí sola.

Si el trabajo podía guardar, la propuesta puede estar ya en la tienda. Para deshacer un cambio de ese trabajo, use **Rollback** en el trabajo de **Jobs**.

### 3.7. Catalog

Abra **Catalog**. Traduce campos de producto, categoría o CMS guardados en los idiomas de la tienda. No edita **International → Translations**. Una pulsación trata como máximo 100 registros. Las filas guardadas se escriben en el idioma de destino.

![Catalog, back office en inglés. Entidad, campos, idiomas y Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Entity** | product | Qué se lee: **product**, **category** o **cms**. Cambiarlo recarga la página y muestra solo esa lista de campos. El cambio en sí no traduce. |
| **Fields** | cada campo de esa entidad | Qué textos envía el lote. Mantenga Ctrl o Cmd. Los campos no seleccionados no se envían y se quedan como están. Producto: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Categoría: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. **Title** de un producto o una categoría es el nombre. En CMS, **Title** es el título de la página y **Content** es el cuerpo. Deje **Friendly URL** sin seleccionar cuando los enlaces deban quedarse igual. |
| **Source language** | el primer idioma de la tienda | El idioma del que se copian los campos. Ese idioma no se modifica. |
| **Target language** | el primer idioma de la tienda | El idioma que recibe la traducción. Debe ser distinto del origen. |
| **Only empty** | Yes | Omite campos que ya tienen texto en el idioma de destino. Apáguelo solo cuando quiera sustituir texto existente. Encendido: el texto de destino existente se queda. Apagado: el lote puede sustituirlo cuando la publicación está permitida. |
| **Start after ID** | 0 | Omite registros hasta este ID. 0 empieza por el primer registro. Tras un lote, el campo pasa al ID más alto de ese lote, incluidas las filas que fallaron. Pulse el botón otra vez para continuar. Para reintentar una fila fallida, vuelva a poner el ID por debajo de ese registro antes de la siguiente pulsación. |

Botón: **Translate batch (max 100)**.

Pasos:

1. Elija **Entity** y marque los campos.
2. Elija **Source language** y **Target language**.
3. Deje **Only empty** activado.
4. Pulse **Translate batch (max 100)**. El mensaje es **Catalog finished: saved N, failed M.** La página muestra también los recuentos **Saved** y **failed**.
5. Abra un registro en el idioma de destino y compruebe el resultado antes de apagar **Only empty** o de lanzar el siguiente lote.

Mensajes:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Cambiar **Entity** muestra **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Abra **Glossary**. El glosario es una lista de palabras y frases que el modelo debe conservar o traducir siempre igual. Añadir una fila no cambia las traducciones ya guardadas. La siguiente traducción lee la lista.

![Glossary, back office en inglés. Añadir término y la lista de términos.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**Un término**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Source term** | vacío, obligatorio | La palabra o frase en el idioma de origen. Escríbala exactamente como aparece, con mayúsculas cuando importen. |
| **Target locale** | vacío | Limita la fila a una configuración regional, por ejemplo pl-PL. Vacío significa que la fila se usa para cada idioma de destino. Una configuración rellena se ignora para los demás idiomas. |
| **Target term** | vacío | La traducción aprobada. Puede estar vacía solo cuando **Do not translate** está activado. |
| **Do not translate** | No | Activado: el modelo copia el término sin cambios, por ejemplo una marca, un SKU o una etiqueta. Desactivado: usa **Target term**. |

Pulse **Add**. Mensajes: **Glossary term added. Translations already stored were not changed.** o **Nothing was added. Type a source term.**

**La tabla**

Columnas: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** o **No**) y **Delete**. **Delete** quita solo esa fila. Mensaje: **Glossary term deleted.** Una lista vacía dice **No glossary terms yet.**

**CSV**

- Elija **CSV file** y pulse **Import CSV**. Mensaje: **Imported N rows.** Si falta el archivo: **CSV file is missing.** Si no se puede leer: **Cannot open the CSV file.**
- La primera fila es una cabecera: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Esa primera fila siempre se omite. Las filas con menos de tres columnas se omiten. En la cuarta columna, un valor vacío o 0 significa **No**. Cualquier otro valor significa **Yes**.
- La importación añade las filas que puede leer. No busca un término existente para sustituirlo, así que importar el mismo archivo otra vez añade duplicados.
- **Export CSV** descarga la lista actual como `glossary.csv`. No necesita un archivo de entrada y no cambia la lista.

Use términos cortos y exactos. Un término muy amplio se fuerza cada vez que aparece.

### 3.9. Excludes

Abra **Excludes**. Una exclusión es un patrón de texto de origen que el módulo no envía a ChatGPT. El texto permanece en la tienda sin cambios. El patrón se aplica en **Manual**, **Bulk**, **Catalog** y en las páginas de traducción.

![Excludes, back office en inglés. Pattern, Type y la lista de patrones.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Pattern** | vacío, obligatorio | El texto que se compara con cada cadena de origen. La comparación depende de **Type**. |
| **Type** | exact | **exact** es la cadena entera. **prefix** es el inicio. **contains** es un fragmento en cualquier punto de la cadena. **regex** es una expresión regular de PHP, aplicada tal como está escrita. Una expresión incorrecta no coincide con nada. Empiece con un patrón corto y compruebe qué se omitió. Un tipo incorrecto puede omitir demasiado o nada. |

Pulse **Add**. Mensaje: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Un patrón vacío: **Nothing was added. Type a pattern.**

Columnas: **Pattern**, **Type**, **On** y **Delete**. **On** muestra 1 cuando el patrón está activo. Esta pantalla no tiene un interruptor para apagar un patrón. Para dejar de usarlo, **Delete** y vuelva a añadirlo si todavía lo necesita. **Delete** quita solo ese patrón. Las traducciones existentes no se borran. Mensaje: **Pattern deleted.** Una lista vacía dice **No patterns yet.**

Use exclusiones para texto que debe quedarse en el idioma de origen, como un nombre legal o un token técnico. Para un término que debe traducirse siempre de una manera, use **Glossary**.

### 3.10. History

Abra **History**, o pulse **See all** en **Dashboard**.

![History, back office en inglés. La lista de peticiones.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** es la lista completa de llamadas a ChatGPT guardadas: ejecuciones manuales, la página de traducciones, trabajos masivos, lotes de catálogo y la prueba de conexión. Cada fila guarda el prompt, la respuesta, el modelo, los idiomas, los recuentos de tokens y cuánto tardó la llamada. Las tarjetas y los gráficos están en **Dashboard**. Abrir esta página no envía una petición nueva y no cambia las traducciones.

Los filtros son los mismos que en **Dashboard** (3.2).

Columnas: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** y **Prompt**. Tipos: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** y **Not sent** (la llamada no se envió, por ejemplo por el límite local o el presupuesto). Una fila **Bulk job** muestra el número de trabajo.

- **View** abre el prompt y la respuesta, con **HTTP**, **Sent**, **Received** y **Total**. En un error, la respuesta es el texto del error. **Back to the list** vuelve a la tabla. Si la fila ya no está: **This history row no longer exists.**
- Un error de acceso significa que la clave de **Settings** es incorrecta, o que la cuenta no puede usar el modelo elegido.
- **Previous**, **Next** y **Page** recorren la lista.
- **Clear history** pregunta **Clear the stored history? Saved translations stay.** Después: **History cleared. Saved translations were not changed.** La ayuda del botón dice **Clear history deletes these rows only. Saved translations stay.**

Una lista vacía dice **No requests yet.**

Cuando las traducciones se detienen de golpe, abra aquí la fila de error más reciente antes de cambiar el glosario.

### 3.11. Updates

Abra **Updates** en el extremo derecho de la barra del módulo. El título del formulario es **MyPresta Updates**.

![Updates, back office en inglés. Manual Check, Automatic Notifications y Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** contiene **Check Now**. Comprueba la versión de inmediato.
- **Automatic Notifications** es **Enabled** o **Disabled**. **Enabled** es el valor cuando la elección nunca se ha guardado. Cuando está activado, el módulo comprueba si MyPresta tiene una versión más nueva y puede mostrar un aviso en el back office.
- **Product Page** es un enlace que abre la página de contacto que usa este módulo.
- **Save** guarda la elección. Mensaje: **Update settings saved.**

Después de **Check Now**: **New version available!** o **Module is up to date!**

### 3.12. Botones en International → Translations

Abra **International → Translations**. Los botones de campo aparecen cuando **Individual field buttons — International → Translations** está activado. Las casillas y la barra aparecen cuando **Individual field checkboxes — International → Translations** está activado.

Qué ve:

- Un botón **Translate** en cada campo de texto.
- Una casilla en cada campo, cuando las casillas están activadas.
- Una barra **ChatGPT translations**, con **Source** (en-US, o el **Source locale** de **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** y la indicación **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** rellena los campos vacíos de la sección actual.

Pasos:

1. Elija **Target**.
2. Marque los campos, o pulse **Check empty**.
3. Pulse **Translate selected**, o **Translate empty**.
4. Espere a que la barra muestre **Done**. Mientras trabaja, el estado es **Translating…** con el recuento. Si no marca nada, la barra dice **Tick at least one field.**
5. Compruebe los campos rellenos. Guarde la página con el botón **Save** de PrestaShop.

Los botones solo rellenan los campos. Sin **Save** de PrestaShop, el texto no entra en la tienda. Con **Allow publish / save** apagado, los campos se rellenan igual, y **Save** de PrestaShop escribe la página.

Mensajes:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** En **Emails**, el texto de origen sale del archivo de plantilla de correo, no del campo de la página. Elija otro **Source locale** que tenga esos archivos de correo.

### 3.13. Botones en los formularios de producto, categoría y CMS

Abra un producto, una categoría, una página CMS u otro formulario de la tienda con campos multidioma. Los botones se ven cuando **Individual field buttons — shop forms** está activado. Las casillas y la barra se ven cuando **Individual field checkboxes — shop forms** está activado.

Qué ve:

- Un botón **Translate** en cada campo multidioma.
- Una casilla para la barra.
- Una barra **ChatGPT translations**, con **Translate from** y **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** y la indicación **Fills the fields. Save with the PrestaShop button.**

Pasos:

1. Rellene el campo en el idioma de origen. Si está vacío, la barra dice **Fill the source language field first.**
2. Elija el idioma de destino en la barra.
3. Pulse el botón de un campo, o marque campos y pulse **Translate selected**. **Translate empty** rellena los campos vacíos.
4. Pulse **Save** en el formulario de PrestaShop. Sin eso, el texto no se guarda.

El botón solo rellena el campo del formulario. Los campos que no marque permanecen sin cambios.

## 4. Tienda

El módulo no añade nada a la página que ve el cliente. No hay bloque, botón ni mensaje en la tienda, así que el tema no tiene nada que mostrar para este módulo.

La única dirección fuera del back office es la dirección cron. Es para una tarea programada en el servidor. No es para los clientes.

- Cópiela de **Settings**, **CRON URL**, o de la línea **CRON** de **Dashboard**.
- Péguela en el programador del servidor, por ejemplo cada pocos minutos. Cada llamada procesa un trozo de un trabajo en espera.
- Use la dirección `https://` cuando la tienda tenga SSL activado.

| Qué ve al abrir la dirección | Qué hacer |
|---|---|
| **Forbidden** | La dirección está incompleta o se cambió. Cópiela otra vez desde **Settings**. |
| **No pending jobs** | No hay un trabajo en `pending` ni en `running`. Cree uno en **Bulk**, o reanude un trabajo en pausa en **Jobs**. |
| Un resultado JSON con `ok`, `finished` y `counts` | Se procesó un trozo. Compruebe el progreso en **Jobs**. |

La dirección cron procesa solo trabajos en `pending` y `running`. Un trabajo `paused` hay que reanudarlo en **Jobs**.

## 5. Problemas

| Qué ve | Causa | Qué hacer |
|---|---|---|
| **No ChatGPT API key.** en cada página del módulo | No hay clave guardada. | Abra **Settings**, pegue la clave en **ChatGPT API key** y pulse **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Los ajustes se guardaron sin clave. | Pegue la clave y pulse **Save**. |
| **Connection was not made. Nothing was translated.** después de **Test connection** | Clave incorrecta, sin ruta hacia OpenAI, o un modelo que la cuenta no puede usar. | Compruebe la clave, elija otro **Model**, o añada el identificador correcto en **Add a ChatGPT model**. Lea la fila de **History**. |
| Errores de acceso en **History** | La clave es incorrecta, o la cuenta no puede usar el modelo elegido. | Corrija la clave, o elija un modelo que la cuenta pueda llamar. |
| **Nothing was started. There is no ChatGPT API key.** en **Bulk** | No hay clave. | Pegue la clave en **Settings** y vuelva a ejecutar **Estimate** y **Start job**. |
| Un trabajo se queda en `pending` | Un trabajo no empieza solo. | Pulse **Process slice** o **Auto-process** en **Jobs**, o configure la dirección cron (sección 4). |
| Un trabajo está `paused` con **Rate limit — job auto-paused. Resume later.** | ChatGPT rechazó llamadas por un límite de ritmo. La respuesta en **History** también puede decir **ChatGPT rate limit (429). Try again later.** | Espere unos minutos y pulse **Resume**. Baje **Batch size** o **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Se alcanzó **Budget USD / month**. | Suba la cantidad, o póngala a 0. Un mes nuevo empieza en cero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** está apagado. | Active **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** en **Manual** | La traducción cambió marcadores o etiquetas HTML. | Edite la fila en **Review before save** para que los marcadores y las etiquetas coincidan con el origen, y pulse **Save approved**. |
| Un trabajo acaba como `completed_with_errors` | Algunas cadenas fallaron. | Abra el trabajo, pulse **Failed only**, descargue **Error CSV** y pulse **Retry failed**. |
| Una fila está en **Review** | La puntuación es inferior a 70, falló el control de longitud o fallaron los marcadores. | Lea **Flags**. **Approve** o **Reject** solo cambia la cola. Use **Rollback** en el trabajo cuando el texto ya se escribió. |
| **The shop needs at least two languages.** | La tienda tiene un idioma. | Añada un idioma en **International → Localization → Languages** y abra el módulo otra vez. |
| Faltan botones en un formulario de producto | Los interruptores de los formularios de la tienda están apagados. | En **Settings**, active **Individual field buttons — shop forms** y, si quiere la barra, **Individual field checkboxes — shop forms**. |
| La página de traducciones no tiene barra | Los interruptores de la página de traducciones están apagados. | Active los dos interruptores de **International → Translations** en **Settings**. |
| **Max tokens** no cambia la longitud de las respuestas | La petición de traducción no envía ese número. | Déjelo en 0. Acorte un resultado editándolo antes de **Save approved**. |
| Importar un CSV del glosario creó duplicados | La importación añade filas. No sustituye un término ya guardado. | Borre las filas de más, o exporte, limpie el archivo, borre las filas antiguas e importe una sola vez. |

## 6. Para desarrolladores

### 6.1. Visión general

- Clase principal: `myaitranslationsgpt`, archivo `myaitranslationsgpt.php`.
- Versión: 1.2.0.
- Nombre técnico: `myaitranslationsgpt`. Nombre en la lista de módulos: **AI Translations with ChatGPT**.
- Autor: MyPresta.eu. Pestaña del Module Manager: `administration`.
- Pestaña del back office: `AdminMyaitranslationsgpt`, padre `AdminInternational`, padre de reserva `IMPROVE`. La etiqueta visible es `AI Translations with ChatGPT`. `ensureTab()` repara una pestaña que falta. `renameTabIfTechnical()` sustituye un nombre de pestaña que sigue siendo el nombre técnico.
- Instalación: `parent::install()`, tablas de `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (escribe una clave solo cuando falta), hooks `displayBackOfficeHeader` y `actionAdminControllerSetMedia`, y después la pestaña.
- Desinstalación: borra la pestaña, `sql/uninstall.php` (elimina 11 tablas), `removeConfiguration()` borra las claves `MYAITGPT_*` que allí se indican, y después `parent::uninstall()`. No borra `mypresta_updates`, `update_myaitranslationsgpt` ni `updatev_myaitranslationsgpt`.
- No hay `enable()` ni `disable()`.
- `getContent()` llama a `ensureTab()` y redirige a `AdminMyaitranslationsgpt` (pestaña por defecto `dashboard`).

Flujo de datos:

1. El formulario de ajustes envía a `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` guarda `MYAITGPT_*` en `Configuration`. `ApiKeyEncryptor` cifra la clave de API con AES-256-CBC. La clave es `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. El valor guardado lleva el prefijo `MYAITGPT1:`. Una clave enviada vacía, o un valor enmascarado, no sustituye la clave guardada.
3. Traducción: `TranslateService::translateMessages()` construye los prompts (`PromptBuilder`), los envía por `OpenAiTranslationProvider` (cURL POST a `https://api.openai.com/v1/chat/completions`, cabecera `Authorization: Bearer`), comprueba la respuesta (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), la puntúa (`QualityScorer`) y la guarda por `TranslationAdapter`.
4. `translateBatch()` envía `temperature` desde los ajustes y no envía `max_tokens`. La prueba de conexión (`ping`) envía `max_tokens` 5 y `temperature` 0. `MYAITGPT_MAX_TOKENS` se guarda y `translateBatch()` no lo lee.
5. El guardado del catálogo usa el servicio de traducción de PrestaShop cuando existe; si no, la tabla `_DB_PREFIX_translation`. Las claves de los módulos clásicos las escribe `LegacyModuleCatalogue` en `translations/{iso}.php` de ese módulo.
6. Bulk: `BulkJobFactory` inserta `myaitgpt_job` y `myaitgpt_job_item`. Una lista de dominios vacía no produce elementos, salvo un módulo clásico, que usa `LegacyModuleCatalogue::DOMAIN`. `JobWorker::processSlice()` ejecuta un trozo de `BATCH_SIZE`. Lo llaman **Process slice**, el bucle de **Auto-process** (AJAX `ProcessJob`) y `controllers/front/cron.php`.
7. Catalog: `CatalogTranslateService::collect()` se llama con un límite de 100. `translateAndSave()` escribe `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`. Los resultados se emparejan por id. Tras el lote, **Start after ID** pasa a ser el `id_entity` más alto del conjunto recogido, incluidas las filas fallidas.
8. Cada llamada se guarda en `myaitgpt_request` (**History**). Los errores van también a `myaitgpt_api_log` (la columna `provider` vale por defecto `openai`). El coste va a `myaitgpt_usage_ledger`. `SnapshotService` copia el valor anterior en `myaitgpt_snapshot` para **Rollback**. `clearTranslationCache()` llama a `Tools::clearCache()` tras un guardado de catálogo, tras un trozo que no es de prueba y tras un rollback.

`QualityScorer` empieza en 100. `validation_failed` resta 40. Cada aviso resta 5. Una relación de longitud superior a 2,5 pone `length_explosion` y resta 20. Una relación inferior a 0,3 cuando el origen tiene más de 20 caracteres pone `too_short` y resta 15. Las palabras inglesas the, and, with, your o please que queden ponen `possible_untranslated` y restan 10. La fila necesita revisión cuando la puntuación es inferior a 70, o cuando está puesto `validation_failed` o `length_explosion`.

### 6.2. Archivos

| Archivo | Función |
|---|---|
| `myaitranslationsgpt.php` | Instalación, desinstalación, pestaña, hooks, recursos, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Comprobación de actualización de la pestaña **Updates** y del aviso del back office. Clase `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logotipo de la cabecera del módulo. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Cada pestaña del back office, guardados, acciones de trabajo, glosario, exclusiones, catálogo, CSV, AJAX. |
| `controllers/front/cron.php` | Dirección cron. Procesa un trozo y devuelve JSON. |
| `sql/install.php`, `sql/uninstall.php` | Crear y eliminar las tablas. |
| `src/Adapter/TranslationAdapterInterface.php` | Interfaz de lectura y escritura de las traducciones de PrestaShop. |
| `src/Adapter/AbstractTranslationAdapter.php` | Secciones, dominios, configuraciones, guardado por el servicio o la tabla `translation`, vaciado de caché. |
| `src/Adapter/TranslationAdapter.php` | Adaptador concreto. |
| `src/Adapter/TranslationAdapterFactory.php` | Construye el adaptador. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Lee catálogos XLF de temas y módulos. |
| `src/Adapter/LegacyModuleCatalogue.php` | Módulos clásicos: leer y escribir `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Formularios del back office y texto `desc` de los campos. |
| `src/Admin/MyaitgptSectionHelp.php` | Texto del panel **Help** de cada pestaña. |
| `src/Audit/RequestLogRepository.php` | **History**: filas, tarjetas, gráficos, filtros, vaciado, retención. |
| `src/Audit/ApiLogRepository.php` | Registro de errores y avisos de la API, retención. |
| `src/Audit/TranslationMemory.php` | Reutiliza un resultado para el mismo texto, configuración, modelo y glosario. |
| `src/Audit/UsageLedger.php` | Estimación de coste y presupuesto mensual. |
| `src/Audit/SnapshotService.php` | Copias antes de una escritura y restauración en **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Lista del glosario, inserción, borrado. |
| `src/Glossary/ExcludePatternRepository.php` | Inserción, borrado y comparación de exclusiones. |
| `src/Job/JobStatuses.php` | Constantes de estado de trabajos y filas. |
| `src/Job/JobRepository.php` | Trabajos y filas: lectura, estado, siguiente trozo, contadores. |
| `src/Job/JobWorker.php` | Procesado del trozo, reintento, fin, cola de revisión, correo de finalización. |
| `src/Provider/TranslationProviderInterface.php` | Interfaz del proveedor. |
| `src/Provider/OpenAiTranslationProvider.php` | Llamadas a ChatGPT, prueba de conexión, registro de peticiones. |
| `src/Provider/PromptBuilder.php` | Prompts de sistema y de usuario: tono, voz de marca, glosario. |
| `src/Provider/ProviderFactory.php` | Construye el proveedor. |
| `src/Quality/PlaceholderValidator.php` | Control de marcadores y etiquetas. |
| `src/Quality/HtmlValidator.php` | Control de HTML. |
| `src/Quality/PsNativeValidator.php` | Control antes de un guardado en **Manual**. |
| `src/Quality/EmailHtmlPipeline.php` | Protege el HTML del correo antes de la llamada y lo restaura después de la respuesta. |
| `src/Quality/QualityScorer.php` | Puntuación 0-100, marcas, decisión de revisión. |
| `src/Security/ApiKeyEncryptor.php` | Cifrar y descifrar la clave de API. |
| `src/Service/ConfigService.php` | Leer y guardar ajustes, modelos, token cron, rangos. |
| `src/Service/RateLimiter.php` | Límite local por minuto, archivo `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Exclusiones, memoria, llamadas, validación, puntuación, guardado, estimación. |
| `src/Service/BulkJobFactory.php` | Construye un trabajo **Bulk** y la estimación. |
| `src/Service/CatalogTranslateService.php` | Recoge y guarda filas de **Catalog**. |
| `src/Service/DashboardService.php` | Recuentos de cobertura en **Dashboard**. |
| `translations/*.php` | Textos de la interfaz, un archivo por idioma. |
| `views/templates/admin/configure.tpl` | La página del módulo y el cajón **Help**. |
| `views/templates/admin/_partials/*.tpl` | Pestañas: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Estilos del back office. |
| `views/js/admin.js` | Progreso de **Jobs** y **Auto-process**, marcas de fila, AJAX. Muestra **Brand voice** solo cuando **Tone** es **Brand**, y **Notify email** solo cuando el aviso por correo está activado. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Botones y barra en **International → Translations**. |
| `views/js/entity-fields.js` | Botones y barra en los formularios de producto, categoría y CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Gráficos de **Dashboard**. |
| `var/rate_limit.json` | Contador del límite local por minuto. |
| `index.php` en cada directorio | Impide el listado del directorio. |

### 6.3. Controladores

**Back office: `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsgpt&token=…`, opcional `&myaitgpt_tab=` con `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (la etiqueta de la pestaña es **History**), `settings`, `updates`.
- Acciones de trabajo, consulta `job_action` más `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback`, `export_errors`. La plantilla no pinta un botón Cancel. `filter_failed=1` limita la tabla de filas. `cancel` pone el trabajo en `cancelled` y deja sin traducir las cadenas que esperaban. Mensaje: **Job cancelled. Strings still waiting were not translated.**
- Acciones de revisión: `review_action=approve|reject` e `id_review`.
- Glosario: `delete_glossary`. Exclusiones: `delete_exclude`. Modelos: `delete_openai_model`, y POST `new_openai_model` con `submitMyaitranslationsgptAddModel`.
- CSV del glosario: `importGlossaryCsv()` omite la cabecera y cualquier fila con menos de tres columnas, y después inserta cada fila restante. No actualiza un término existente.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource`, `displayAjaxListDomains`.

**Tienda: `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- URL de la tienda: `module/myaitranslationsgpt/cron`.
- La consulta `token` debe coincidir con `MYAITGPT_CRON_TOKEN` (`hash_equals`). Un token ausente o incorrecto devuelve HTTP 403 y JSON `{"ok":false,"error":"Forbidden"}`.
- Un `id_job` opcional procesa ese trabajo. Sin él, se procesa el primer trabajo `pending` o `running`.
- Un trozo correcto devuelve JSON con `ok`, `finished` y `counts`. Cuando no hay trabajo en espera, el cuerpo es `{"ok":true,"message":"No pending jobs"}`.
- `ssl` del controlador es true.

### 6.4. Hooks

Hooks registrados:

- `displayBackOfficeHeader` - renombra una etiqueta técnica de pestaña y después carga CSS y JS.
- `actionAdminControllerSetMedia` - carga los mismos recursos.

`translations-tool.js` se añade en el controlador de traducciones. `entity-fields.js` se añade en los formularios de la tienda cuando los interruptores de campo están activados. `Media::addJsDef` publica `myaitgptTr` (URL ajax, configuración de origen, idiomas y etiquetas de la barra). La etiqueta de la barra es **ChatGPT translations**.

El módulo no registra un hook propio para que otros módulos lo implementen. No hay `enable()` ni `disable()`.

### 6.5. Sustituciones

El módulo no sustituye ninguna clase ni controlador de PrestaShop.

### 6.6. Base de datos

| Tabla | Contenido |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id de tienda, fechas. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | Una ejecución masiva: configuraciones, `scope_json`, `policy_json`, `dry_run`, contadores, totales de tokens, coste, empleado, error, marcas de tiempo. |
| `myaitgpt_job_item` | Una cadena de un trabajo: dominio, clave, tema, configuración, origen, valor anterior, valor nuevo, estado, motivo de omisión, error, tokens, validación. |
| `myaitgpt_memory` | Memoria de traducción: hash, origen, configuración, traducción, modelo, número de aciertos. |
| `myaitgpt_usage_ledger` | Filas diarias de tokens y coste, id de trabajo opcional, modelo. |
| `myaitgpt_snapshot` | Valor anterior a una escritura del trabajo, usado por **Rollback**. |
| `myaitgpt_api_log` | Filas de error y aviso: nivel, proveedor (por defecto `openai`), código HTTP, mensaje, contexto. |
| `myaitgpt_request` | Filas de **History**: tipo, estado, modelo, configuraciones, código HTTP, duración, tokens, coste, empleado, trabajo, prompt, respuesta, error. |
| `myaitgpt_review` | Cola de revisión: elemento del trabajo, estado, puntuación, marcas, empleado. |
| `myaitgpt_catalog_item` | Filas del lote de catálogo: entidad, campo, idiomas, origen, anterior, nuevo, estado, error. |

La desinstalación elimina las once tablas. La instalación usa `CREATE TABLE IF NOT EXISTS`, así que una reinstalación sobre una base que aún tiene las tablas conserva esas filas. Una desinstalación normal las quita antes. No se añade ninguna columna en la primera visita a una página.

### 6.7. Claves y traducciones

Prefijo `MYAITGPT_`. Valores cuando falta la clave, que es también el valor escrito en la instalación:

| Clave | Cuando falta |
|---|---|
| `API_KEY_ENC` | vacío |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | vacío |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vacío |
| `BATCH_SIZE` | `25` (al guardar se vuelve a limitar a 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vacío |
| `TEMPERATURE` | `0.2` (al guardar se vuelve a limitar a 0-1) |
| `DRY_RUN_SAMPLE` | `10` (al guardar se vuelve a limitar a 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (mínimo 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vacío |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (solo se guarda; `translateBatch()` no lo envía) |
| `CRON_TOKEN` | 16 bytes aleatorios en hexadecimal, generados en la instalación |

`removeConfiguration()` también borra los nombres residuales `DEEPL_API_KEY` y `CLAUDE_API_KEY` bajo el mismo prefijo. No borra las claves del comprobador de actualizaciones.

Las descripciones de campo son las cadenas `desc` de `src/Admin/MyaitgptForms.php`, construidas por `help()` como finalidad, modo de ajuste y efecto. La ayuda de **Max tokens** dice que se deje 0 para el valor por defecto de ChatGPT. La petición ignora el valor guardado. La ayuda de las pestañas está en `src/Admin/MyaitgptSectionHelp.php`.

Las cadenas de la interfaz pasan por `$this->l()` / `{l s=... mod='myaitranslationsgpt'}`. Añada un idioma con `translations/{iso}.php`. El error de trabajo **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.** y **Monthly API budget has been exhausted.** son cadenas en inglés devueltas por `JobWorker` y `TranslateService`, no llamadas a `$this->l()`. Las cadenas de **Updates** usan el dominio de traducción `updatechecker`. `OpenAiTranslationProvider` devuelve **ChatGPT rate limit (429). Try again later.** ante HTTP 429.

### 6.8. Ampliación

La tienda no renderiza una plantilla del módulo, así que el tema no tiene nada que sustituir.

Las plantillas del back office están en `views/templates/admin/`. PrestaShop no ofrece una sustitución de tema para esas plantillas de administración. Cambie las etiquetas con `translations/{iso}.php`. Los botones de **International → Translations** y de los formularios de la tienda los inyectan `views/js/translations-tool.js` y `views/js/entity-fields.js` desde `myaitgptTr`. No hay un hook que un tema pueda usar para sustituir esa barra.

## 7. Ayuda

Página del módulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

Para escribir sobre este módulo, inicie sesión en su cuenta de cliente en mypresta.eu, abra el formulario de contacto y elija **Support for paid modules**. El formulario indica que los módulos de pago exigen iniciar sesión. Después de iniciar sesión, elija este módulo en el historial de compras.
