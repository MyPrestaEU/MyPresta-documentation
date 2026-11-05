---
title: "AI Translations with Claude - documentación y manual de usuario"
description: "Guía de configuración y de solución de problemas para tiendas que ya usan el módulo AI Translations with Claude."
sidebar:
  label: "AI Translations with Claude - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with Claude en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.7.0.0 y versiones posteriores, incluidas PrestaShop 8 y 9.

- **PrestaShop:** 1.7.0.0 o posterior.
- **PHP:** 5.6 o posterior.
- **Extensiones de PHP:** cURL, OpenSSL, SimpleXML y mbstring.
- **Otros módulos:** el módulo no necesita ningún otro módulo.
- **Fuera de la tienda:** una cuenta de Anthropic y una clave de API, que puede crear en https://console.anthropic.com/settings/keys. El servidor de la tienda tiene que poder conectarse a `https://api.anthropic.com/v1/messages`.
- **Opcional:** una tarea programada en el servidor que llame a la dirección cron que aparece en **Settings**. Sin ella, tendrá que procesar los trabajos usted mismo en **Jobs**.
- **Catálogos grandes:** un dominio con miles de cadenas supone muchas llamadas a la API. El módulo divide cada trabajo en tandas del tamaño de **Batch size**. Antes de empezar, ejecute **Estimate** en **Bulk** para ver cuánto costará.
- La tienda necesita al menos dos idiomas. Con un solo idioma, el back office muestra **The shop needs at least two languages.** y no hay nada que traducir.

## 2. Instalación

1. Abra **Modules** y después **Module Manager**. Elija **Upload a module**, suba el archivo ZIP y haga clic en **Install** junto a **AI Translations with Claude**.
2. Tras la instalación, **AI Translations with Claude** aparece en el menú **International**.
3. La instalación no vacía la caché de la tienda. El módulo la vacía cuando guarda una traducción.

A continuación, abra **AI Translations with Claude**, vaya a **Settings** y pegue su clave de Claude. Mientras no haya una clave guardada, cada página del módulo mostrará **No Claude API key.** con un enlace a **Open Settings**.

**Desinstalación.** En **Module Manager**, haga clic en **Uninstall** y confirme **Delete this module and its data (jobs, glossary, cache)?**

- La entrada del menú desaparece. Se eliminan los trabajos, el glosario, los patrones de exclusión, el historial de llamadas, la cola de **Review**, las copias para **Rollback**, el registro de costes y la configuración del módulo, incluida la clave de API.
- Se conserva el texto que el módulo ya escribió en la tienda: las traducciones del catálogo y los archivos de traducción de los módulos clásicos que escribió. También se conserva su elección sobre la comprobación de actualizaciones.
- Una instalación nueva no recupera los trabajos, el glosario ni el historial eliminados. Restablece los valores por defecto y crea una dirección cron nueva.

## 3. Configuración y trabajo diario

Todo el módulo está en una sola página: **International** y después **AI Translations with Claude**. Las pestañas son **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** y **Settings**. **Updates** está al final de la barra. **Help** abre un panel de ayuda para la pestaña en la que se encuentra.

Los nombres de botones y campos de este manual son los del back office en inglés. Si su back office está en otro idioma, verá la traducción del mismo control.

**Del primer clic a una traducción guardada**

El trabajo lo inicia un empleado desde el back office. El cliente no lo inicia.

1. **Settings.** Pegue la clave de Claude, elija el modelo y el idioma de origen, haga clic en **Test connection** y después en **Save**. Sin clave, ninguna herramienta envía texto a Claude.
2. **Elija cómo trabajar.**
   - Unas pocas cadenas, o un dominio, con revisión antes de guardar: **Manual** (3.3).
   - Un dominio grande, un tema o un módulo: **Bulk** y después el trabajo en **Jobs** (3.4 y 3.5).
   - Campos de producto, categoría y CMS: **Catalog**, hasta 100 registros cada vez (3.7).
   - Campos sueltos en **International → Translations** (3.12) y en los formularios de producto, categoría y CMS (3.13).
3. **Control de calidad.** Cada cadena traducida se comprueba en busca de marcadores de posición y de HTML. Una cadena que no supera la comprobación no se guarda. Van a **Review** las cadenas con una puntuación inferior a 70, las que son más de dos veces y media más largas que el original, y las que todavía contienen palabras en inglés como *the*, *and*, *with*, *your* o *please*.
4. **Guardado.**
   - **Manual:** **Translate selected (review)** no guarda nada hasta que haga clic en **Save approved**. **Save now (skip review)** escribe en el acto las filas válidas.
   - **Bulk:** el trabajo espera en **Jobs**. Solo escribe después de **Process slice**, **Auto-process** o de una llamada a la dirección cron. Un trabajo con **Dry-run job** activado no escribe nada.
   - **Catalog:** las filas válidas se escriben al momento en el idioma de destino.
   - **International → Translations** y los formularios de la tienda: los botones solo rellenan los campos. Los guarda el botón **Save** de PrestaShop.
   - Con **Allow publish / save** desactivado, **Manual**, **Bulk** y **Catalog** no escriben nada en la tienda.
5. **Fin del trabajo.** En **Jobs**, el estado cambia a **completed** o **completed_with_errors**. Las filas de **Review** salen de la lista al hacer clic en **Approve** o **Reject**. **Catalog** indica cuántas filas se guardaron y cuántas fallaron.

### 3.1. Configuración del módulo

Abra **Modules**, **Module Manager**, busque **AI Translations with Claude** y haga clic en **Configure**. Se abrirá **Dashboard**. Vaya a **Settings**.

**Save** y **Test connection** están al final del formulario. Guardar este formulario no inicia ninguna traducción ni cambia las traducciones ya guardadas en la tienda.

![Ajustes, back office en inglés. Parte superior del formulario: Claude API key, Model, Add a Claude model, Tone y Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Conexión**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Claude API key** | vacío | La clave secreta que esta tienda envía a Claude. Pegue la clave que obtiene en https://console.anthropic.com/settings/keys. Deje el campo vacío para conservar la clave ya guardada. Un valor nuevo sustituye a la clave almacenada; un campo vacío no la borra. Cuando hay una clave guardada, el texto de ayuda muestra **Key saved:** y la clave enmascarada. |
| **Model** | claude-haiku-4-5 | El modelo de Claude que escribe las traducciones. Los nombres integrados se mantienen en la lista: claude-haiku-4-5, claude-sonnet-4-5 y claude-opus-4-5. La siguiente traducción usa el modelo seleccionado. Si su cuenta no puede usar un modelo, la llamada falla y el error aparece en **History**. |
| **Add a Claude model** | vacío | Escriba el identificador exacto de su cuenta de Anthropic y haga clic en **Add model**. El nuevo identificador aparece en **Model** y pasa a ser el modelo activo. **Remove** solo borra los identificadores que añadió aquí. Los identificadores integrados no se pueden borrar. |

Mensajes: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Estilo y origen**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Tone** | Formal | Añade una instrucción de estilo a cada petición. **Formal** sirve para los textos de la tienda y del back office, **Casual** da un tono más cercano y **Brand** funciona junto con **Brand voice**. Las traducciones nuevas siguen ese estilo. Las que ya existen se mantienen hasta que las vuelva a traducir. |
| **Brand voice** | vacío | Se muestra cuando **Tone** es **Brand**. Unas pocas frases sencillas sobre cómo debe sonar la tienda, o el campo vacío. El texto se añade a la siguiente petición. Vacío significa que no hay voz adicional. No reescribe las traducciones ya guardadas. |
| **Source locale** | vacío | El idioma que el modelo trata como original. La opción vacía es un guion en la lista, y entonces el origen lo proporciona la pantalla que está traduciendo. Elija la configuración regional en la que están escritos sus catálogos, normalmente en-US. **Manual**, **Bulk** y los iconos de **International → Translations** usan esta configuración regional como origen. El idioma predeterminado de la tienda no cambia. |
| **Individual field buttons — shop forms** | Yes | Un botón junto a cada campo multilingüe de los formularios de la tienda: producto, categoría, CMS y el resto de formularios del back office. El botón traduce solo ese campo. **No** oculta estos botones en toda la tienda. Las traducciones guardadas no cambian. |
| **Individual field checkboxes — shop forms** | Yes | Cada uno de esos campos tiene una casilla, y la barra traduce solo los campos que marque. **No** oculta las casillas y la barra. Los botones de arriba tienen su propio interruptor. |
| **Individual field buttons — International → Translations** | Yes | Un botón junto a cada campo de **International → Translations**. **No** oculta estos botones. Los formularios de la tienda no se ven afectados. Un clic rellena ese campo. El botón **Save** de PrestaShop sigue guardando la página. |
| **Individual field checkboxes — International → Translations** | Yes | Casillas y barra en **International → Translations**. **No** las oculta. Los formularios de la tienda no se ven afectados. |

![Ajustes, back office en inglés. Parte inferior del formulario: límites, correo, la dirección cron, Test connection y Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Límites**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Batch size** | 25 | Cuántas cadenas se envían en una llamada a la API. En la primera prueba use entre 10 y 25. El valor se mantiene entre 1 y 100. Un lote más grande termina el trabajo con menos llamadas. Si una llamada falla, el reintento abarca un bloque mayor. |
| **Dry-run sample** | 10 | Cuántas cadenas de ejemplo muestra **Estimate** antes de un trabajo de **Bulk**. El valor se mantiene entre 1 y 50. **Estimate** no escribe traducciones. |
| **Max tokens (0 = default)** | 0 | Límite de longitud de una respuesta. Con 0 se envía un límite de 4096 tokens. Ponga un número si las respuestas se cortan o si las quiere más breves. Solo la siguiente llamada usa el límite. Las traducciones ya guardadas no se acortan. |
| **Budget USD / month** | 0 | Tope mensual en dólares estadounidenses, calculado con el registro de consumo. 0 significa que no hay tope. Cuando el registro llega a esa cantidad, se detienen las nuevas traducciones. Lo que ya se guardó permanece. |
| **Rate limit / min** | 60 | Cuántas llamadas a la API puede iniciar esta tienda en un minuto. 0 desactiva este límite local. Las llamadas por encima del límite se omiten y aparecen en **History**. Claude puede aplicar además su propio límite. |
| **Log retention days** | 30 | Cuántos días de filas se conservan en **History**. Mínimo 1. Las filas más antiguas se eliminan. Este número no borra los trabajos, el glosario ni las traducciones guardadas. |
| **Temperature** | 0.2 | Cuánta libertad tiene el modelo para reformular. Con un valor cercano a 0.2 se mantiene cerca del original. Los valores más próximos a 1 cambian más las frases. El valor guardado se mantiene entre 0 y 1. Los marcadores de posición y el HTML se comprueban después igualmente. Los modelos integrados reciben este valor. Un identificador de modelo que añada y que no sea Claude Haiku, Sonnet u Opus 4.0, 4.1, 4.5 o 4.6 no lo recibe, así que este campo no tiene efecto en ese modelo. |
| **Allow publish / save** | Yes | Si este módulo puede escribir una traducción en PrestaShop. **No** bloquea el guardado en **Manual**, en los trabajos de **Bulk** y en **Catalog**. Los iconos de la página de traducciones y de los formularios de la tienda siguen limitándose a rellenar el formulario. El botón **Save** de PrestaShop es independiente. |

Después de **Save**:

- **Settings saved. No translation was started.** Los ajustes están guardados y no se ha traducido nada.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Pegue una clave en **Claude API key** y haga clic de nuevo en **Save**.

**Correo y cron**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Email notify on complete** | No | Envía un correo cuando termina un trabajo de **Bulk**. El trabajo se ejecuta igual, con o sin correo. Lo único que se añade o se omite es el correo. |
| **Notify email** | vacío | La dirección que recibe ese correo. El campo solo se usa si el interruptor anterior está activado. Guardar la dirección, por sí solo, no envía ningún mensaje. |
| **CRON URL** | una dirección con token | Dirección secreta que el servidor puede llamar para procesar una tanda de un trabajo en espera. Cópiela en el programador de tareas del servidor. No la publique. Quien tenga la dirección puede iniciar una tanda. Abrir **Settings** no inicia ningún trabajo. |

**Test connection** comprueba la clave y el modelo con una petición breve. No traduce ni guarda nada.

- **Connection OK (N ms). No translation was started.** La conexión funciona.
- **Connection was not made. Nothing was translated.** seguido del motivo. Compruebe la clave y el modelo. El detalle está en **History**.

Para empezar: pegue la clave, elija el modelo y el idioma de origen, haga clic en **Test connection** y después en **Save**. Deje los números con los valores de instalación hasta que algún trabajo dé problemas.

### 3.2. Dashboard

Abra la pestaña **Dashboard**. Cuenta las cadenas del catálogo que faltan por traducir y, debajo, muestra el consumo de Claude en tarjetas, gráficos y las diez peticiones más recientes. La página no traduce ni cambia ninguna cadena.

![Dashboard, back office en inglés. Cobertura de una configuración regional, la línea cron y los filtros del historial.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Cobertura**

- **Locale:** la configuración regional de la tienda cuyas cadenas pendientes se cuentan.
- **Show:** vuelve a dibujar la tabla para esa configuración regional.
- Columnas: **Section**, **Total**, **Missing**, **Done** y una barra de progreso. Las secciones son **Back office**, **Themes**, **Installed modules**, **Emails** y **Others**. **Missing** es el número de cadenas sin traducción en esa configuración regional.
- Debajo de la tabla, **CRON** muestra la misma dirección que **CRON URL** en **Settings**.
- Una tabla vacía indica que la tienda todavía no tiene catálogo para esa configuración regional. Cree uno en **International → Translations**.

Tras **Show**, el mensaje es **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Consumo**

- Intervalos predefinidos: **Today**, **7 days**, **30 days**, **This month**, **All time**.
- Filtros: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** y **Prompt or reply contains**. Pulse **Filter**.
- Tarjetas: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** y **Estimated cost**. El coste estimado es un cálculo local, no una factura de Anthropic.
- Gráficos: **Requests and errors**, **Tokens sent and received** y **Requests by model**. Debajo hay grupos **By day**, **By model**, **By type**, **By language** y **By employee**, con las columnas **Group**, **Calls**, **Sent**, **Received** y **Total**. Un grupo vacío muestra **No requests in this range.**
- **Latest prompts** muestra diez llamadas. **View** abre el prompt y la respuesta. **See all** abre **History** (3.10). Si la lista está vacía, verá **No requests yet.**

Filtrar no borra el historial ni cambia las traducciones.

Si en una sección faltan casi todas las cadenas, abra **Manual** para unas pocas o **Bulk** para un dominio entero.

### 3.3. Manual

Abra **Manual**. Traduce un dominio o un módulo clásico, unas decenas de cadenas cada vez. Filtrar por sí solo no guarda nada.

![Manual, back office en inglés. Section, Source, Target, Domain, Only empty y Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Section** | Back office | Qué catálogo se lee: **Back office**, **Themes**, **Installed modules**, **Emails** u **Others**. Al cambiar de sección se recarga la página y solo se muestran los campos de esa sección. No se llama a Claude. |
| **Theme** | vacío | Solo aparece con **Themes**. Limita la lista a un tema. |
| **Module** | vacío | Solo aparece con **Installed modules**. Limita la lista a un módulo. Un módulo clásico sin dominio carga todas las cadenas de ese módulo. |
| **Domain** | vacío | La misma agrupación que en **International → Translations**. Elija una y haga clic en **Filter**. Se oculta en un módulo clásico y en una sección sin dominios. |
| **Source** | el **Source locale** de **Settings**, o en-US | El idioma del que se toman las cadenas. Elija uno que ya tenga un buen texto. |
| **Target** | el primer idioma de la lista | El idioma que quiere rellenar. Debe existir en **International → Localization → Languages**. |
| **Only empty** | Yes | Muestra solo las cadenas sin traducir. Si lo desactiva, se ven todas las cadenas. Las traducciones guardadas no se borran. |
| **Search** | vacío | Deja solo las cadenas de origen que contienen la palabra que escriba. |

Pasos:

1. Ajuste **Section**, **Source** y **Target**.
2. En **Themes**, elija **Theme**. En **Installed modules**, elija **Module**.
3. Haga clic en **Filter**. La lista **Domain** se actualiza. Elija un dominio y haga clic de nuevo en **Filter**. En un módulo clásico, omita el dominio: **Filter** carga todas las cadenas del módulo.
4. Marque las filas que quiera. **Check all** y **Uncheck all** seleccionan o limpian la lista.
5. Haga clic en **Translate selected (review)**. Se abre la tabla **Review before save** con **Source**, **AI proposal** y **Warnings**. Desmarque las filas que no quiera. Si una propuesta necesita un retoque, edítela directamente en el campo. Haga clic en **Save approved**.
6. O bien marque **Save now (skip review)** antes de traducir. Las filas válidas se escriben al momento, sin pasar por la tabla de revisión.

Las columnas de la lista de cadenas son **Source**, **Current** y **Status** (**empty** o **filled**).

Mensajes:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Es la lista de un módulo clásico.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Esas filas se omitieron. Corrija los marcadores de posición y las etiquetas para que coincidan con el original y guarde otra vez.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Al cambiar de sección aparece también una línea corta, por ejemplo **Section is Back office. Theme and module are not used.**, junto con **Nothing was sent to Claude.** El mismo patrón se aplica a **Themes**, **Installed modules**, **Emails** y **Others**.

### 3.4. Bulk

Abra **Bulk**. Crea un único trabajo para muchos dominios e idiomas. **Estimate** no guarda nada. **Start job** añade una fila en **Jobs**. No se escribe nada en la tienda hasta que el trabajo se procesa y **Allow publish / save** está activado.

![Bulk, back office en inglés. Section, Source, Targets, Domains, Policy y Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Section** | Back office | Qué catálogo lee el trabajo. Las mismas opciones que en **Manual**. |
| **Theme** / **Module** | vacío | Solo aparecen con la sección correspondiente, igual que en **Manual**. |
| **Source** | el **Source locale** de **Settings**, o en-US | El idioma que se trata como original. Cada idioma de destino se traduce desde este. |
| **Targets** | ninguno | Uno o varios idiomas que rellenar. Mantenga pulsada la tecla Ctrl (o Cmd en un Mac) para seleccionar varios. Un clic simple sustituye la selección. |
| **Domains** | ninguno | Los dominios incluidos en el trabajo. Mantenga pulsada Ctrl o Cmd. Si no selecciona ninguno, el trabajo abarca todos los dominios de la sección elegida. |
| **Policy** | Fill empty | **Fill empty** envía solo las cadenas sin traducción. **Overwrite all** envía todas, también las que ya tienen traducción, y puede sustituirlas. **Outdated if equals source** envía solo las cadenas cuya traducción es idéntica al original. |
| **Dry-run job** | No | Claude trabaja igualmente y el trabajo aparece en **Jobs**, pero las respuestas no se escriben en la tienda. |

Pasos:

1. Elija la sección, el origen, los idiomas de destino, los dominios y la política.
2. Haga clic en **Estimate**. La página muestra **Estimate**, el número de cadenas, una estimación de tokens, una estimación de coste y un **Sample**.
3. Si la estimación le parece aceptable, haga clic en **Start job**. Se abre **Jobs** con el trabajo nuevo.
4. Procéselo en **Jobs** (3.5) o déjelo para la dirección cron.

Mensajes:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Abra **Jobs**. Cada fila es una ejecución iniciada desde **Bulk**.

![Jobs, back office en inglés. La lista de trabajos. En esta tienda todavía no hay trabajos.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Columnas: **#**, **Status**, **Locales** (origen y después destinos), **Progress** (hechas/total), **Cost**, **Employee**, **Date** y **Open**. Si la lista está vacía, verá **No jobs yet.**

Estados del trabajo, tal como aparecen en pantalla:

- `pending` - en espera. No arranca solo.
- `running` - en curso.
- `paused` - detenido hasta que lo reanude.
- `cancelled` - detenido. Las cadenas que seguían en espera no se tradujeron.
- `completed` - todas las cadenas procesadas, sin errores.
- `completed_with_errors` - terminado, aunque algunas cadenas fallaron.
- `failed` - el trabajo terminó con un error.

**La pantalla del trabajo**

**Open** muestra **Job #N**, el estado, el progreso (hechas/total), **failed**, **skipped**, el coste, el número de empleado y la etiqueta **dry-run** si el trabajo es una prueba. La barra de progreso se actualiza sola mientras el trabajo está abierto. La tabla de debajo tiene las columnas **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** y **Error**.

Estados de las filas: `pending`, `processing`, `done`, `failed`, `skipped` (coincidió una exclusión o la cadena ya estaba traducida) y `rolled_back`.

Botones:

- **Process slice** - procesa una tanda del tamaño de **Batch size** y se detiene. Mensaje: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Si no queda nada: **The job has no more strings waiting.**
- **Auto-process** - repite tandas hasta que el trabajo termina o un error lo detiene. Funciona en el navegador, así que la pestaña debe permanecer abierta. Al cerrarla, el bucle se detiene. El trabajo se conserva y puede terminarlo con **Process slice** o con la dirección cron.
- **Pause** - mensaje: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - mensaje: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - las cadenas con error vuelven a la espera y el trabajo vuelve a esperar. Mensaje: **Retried N failed items.**
- **Rollback** - pregunta **Roll back this job?** y restaura la traducción anterior allí donde el módulo guardó una copia antes del cambio. Mensaje: **Rollback: restored N translations.**
- **Error CSV** - descarga las filas con error. Columnas: id, domain, locale, source, error.
- **Failed only** - muestra solo las filas con error.
- **Review queue** - abre **Review** (3.6).

La pantalla del trabajo no tiene botón Cancel. Para detener el trabajo, use **Pause**.

**Pausa automática**

Cuando Claude rechaza llamadas por un límite de frecuencia, el trabajo se pausa solo. La línea de error dice **Rate limit — job auto-paused. Resume later.** Espere un poco y haga clic en **Resume**. **Rate limit / min** en **Settings** reduce el número de llamadas que la tienda inicia por minuto.

Otros mensajes de esta pantalla:

- **Nothing was translated.** seguido de **No Claude API key. Nothing was translated.** Pegue la clave en **Settings**.
- **Allow publish is off in Settings.** Un trabajo que no es una prueba no se ejecutará hasta que active **Allow publish / save**.
- **Monthly API budget has been exhausted.** Suba **Budget USD / month** o póngalo a 0.

### 3.6. Review

Abra **Review** o haga clic en **Review queue** en un trabajo. El título de la página es **Needs-review queue (quality score / flags).** La lista muestra las filas más recientes que el control de calidad no aprobó automáticamente, hasta 100.

![Review, back office en inglés. La cola de revisión está vacía.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Columnas: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, y después **Approve** y **Reject**. Si la lista está vacía, verá **The queue is empty.**

Cómo leer una fila:

- **Score** va de 0 a 100. Por debajo de 70, la fila entra en la cola.
- **Flags:**
  - `validation_failed` - los marcadores de posición o el HTML no superaron la comprobación.
  - `warning` - una nota menor de la comprobación.
  - `length_explosion` - la traducción es más de dos veces y media más larga que el original.
  - `too_short` - la traducción es mucho más corta que un original largo.
  - `possible_untranslated` - en la traducción siguen palabras en inglés como *the*, *and*, *with*, *your* o *please*.
- **Source** es el original. **AI** es la propuesta del modelo.

**Approve** y **Reject** solo cambian el estado de la fila. El mensaje es **Review updated.** y la fila sale de la lista. Esta acción no escribe el texto en la tienda ni cambia el resto del dominio.

Si el trabajo tenía permiso para guardar, la propuesta puede estar ya en la tienda. Para deshacer los cambios de ese trabajo, use **Rollback** en el trabajo, en **Jobs**.

### 3.7. Catalog

Abra **Catalog**. Traduce campos de producto, categoría o CMS guardados en los idiomas de la tienda. No edita **International → Translations**. Cada pulsación procesa como máximo 100 registros. Las filas guardadas se escriben en el idioma de destino.

![Catalog, back office en inglés. Entity, Fields, idiomas, Only empty y Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Entity** | product | Qué se lee: **product**, **category** o **cms**. Al cambiarlo, la página se recarga y muestra solo la lista de campos de esa entidad. El cambio en sí no traduce nada. |
| **Fields** | todos los campos de esa entidad | Qué textos envía el lote. Mantenga pulsada Ctrl o Cmd para elegir varios. Los campos sin seleccionar no se envían y se quedan como están. Producto: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** y **Friendly URL**. Categoría: **Title**, **Description**, **Meta title**, **Meta description** y **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content** y **Friendly URL**. En un producto o una categoría, **Title** es el nombre. En CMS, **Title** es el título de la página y **Content** es el contenido de la página. Deje **Friendly URL** sin seleccionar si quiere que los enlaces se mantengan. |
| **Source language** | el primer idioma de la tienda | El idioma del que se copian los campos. Ese idioma no se modifica. |
| **Target language** | el primer idioma de la tienda | El idioma que recibe la traducción. Debe ser distinto del origen. |
| **Only empty** | Yes | Omite los campos que ya tienen texto en el idioma de destino. Desactívelo solo si quiere sustituir el texto existente. Activado: el texto de destino existente se conserva. Desactivado: el lote puede sustituirlo, si la publicación está permitida. |
| **Start after ID** | 0 | Omite los registros hasta este ID. 0 empieza por el primer registro. Tras cada tanda, el campo se fija en el ID más alto de esa tanda, incluidas las filas que fallaron. Pulse el botón otra vez para continuar. Para reintentar una fila con error, ponga de nuevo el ID por debajo de ese registro antes de la siguiente pulsación. |

Botón: **Translate batch (max 100)**.

Pasos:

1. Elija **Entity** y marque los campos.
2. Elija **Source language** y **Target language**.
3. Deje **Only empty** activado.
4. Haga clic en **Translate batch (max 100)**. El mensaje es **Catalog finished: saved N, failed M.** La página también muestra los contadores **Saved** y **failed**.
5. Abra un registro en el idioma de destino y revise el resultado antes de desactivar **Only empty** o de lanzar la siguiente tanda.

Mensajes:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Al cambiar **Entity** aparece **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Abra **Glossary**. El glosario es una lista de palabras y expresiones que el modelo debe conservar sin cambios o traducir siempre igual. Añadir una fila no cambia las traducciones ya guardadas. La siguiente traducción leerá la lista.

![Glossary, back office en inglés. Añadir un término y la importación CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**Un término**

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Source term** | vacío, obligatorio | La palabra o expresión en el idioma de origen. Escríbala exactamente como aparece, con las mayúsculas donde importen. |
| **Target locale** | vacío | Limita la fila a una configuración regional, por ejemplo pl-PL. Vacío significa que la fila vale para todos los idiomas de destino. Si indica una configuración regional, la fila se ignora en los demás idiomas. |
| **Target term** | vacío | La traducción aprobada. Solo puede quedar vacío si **Do not translate** está activado. |
| **Do not translate** | No | Activado: el modelo copia el término tal cual, por ejemplo una marca, un SKU o una etiqueta. Desactivado: usa **Target term**. |

Pulse **Add**. Mensajes: **Glossary term added. Translations already stored were not changed.** o **Nothing was added. Type a source term.**

**La tabla**

Columnas: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** o **No**) y **Delete**. **Delete** elimina solo esa fila. Mensaje: **Glossary term deleted.** Si la lista está vacía, verá **No glossary terms yet.**

**CSV**

- Elija **CSV file** y pulse **Import CSV**. Mensaje: **Imported N rows.** Si falta el archivo: **CSV file is missing.** Si no se puede leer: **Cannot open the CSV file.**
- La primera fila es el encabezado: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Esa primera fila siempre se omite. Las filas con menos de tres columnas también se omiten. En la cuarta columna, un valor vacío o 0 significa **No**. Cualquier otro valor significa **Yes**.
- La importación añade las filas del archivo. No comprueba si el término ya existe, así que importar el mismo archivo dos veces crea duplicados.
- **Export CSV** descarga la lista actual como `glossary.csv`. No necesita ningún archivo de entrada y no cambia la lista.

Use términos cortos y precisos. Un término demasiado amplio se aplica siempre que aparece.

### 3.9. Excludes

Abra **Excludes**. Una exclusión es un patrón de texto de origen que el módulo no envía a Claude. El texto se queda en la tienda sin cambios. El patrón se aplica en **Manual**, **Bulk**, **Catalog** y en las páginas de traducción.

![Excludes, back office en inglés. Pattern, Type y la lista vacía.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Campo | Al instalar | Qué hace |
|---|---|---|
| **Pattern** | vacío, obligatorio | El texto que se compara con cada cadena de origen. La forma de comparar depende de **Type**. |
| **Type** | exact | **exact** coincide con la cadena completa. **prefix** coincide con el principio. **contains** coincide con un fragmento en cualquier parte. **regex** es una expresión regular de PHP y se aplica tal como la escribió. Una expresión incorrecta no coincide con nada. Empiece con un patrón corto y compruebe qué se ha omitido. Un tipo equivocado puede omitir demasiado o nada. |

Pulse **Add**. Mensaje: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Si el patrón está vacío: **Nothing was added. Type a pattern.**

Columnas: **Pattern**, **Type**, **On** y **Delete**. **On** muestra 1 cuando el patrón está activo. Esta pantalla no tiene un interruptor para desactivar patrones. Para dejar de usarlo, pulse **Delete** y vuelva a añadirlo si todavía lo necesita. **Delete** elimina solo ese patrón. No borra las traducciones existentes. Mensaje: **Pattern deleted.** Si la lista está vacía, verá **No patterns yet.**

Use las exclusiones para el texto que debe quedarse en el idioma de origen, como un nombre legal o un token técnico. Para un término que debe traducirse siempre de la misma manera, use **Glossary**.

### 3.10. History

Abra **History** o pulse **See all** en **Dashboard**.

![History, back office en inglés. La lista de llamadas y Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** es la lista completa de las llamadas guardadas a Claude: ejecuciones manuales, la página de traducciones, trabajos de **Bulk**, lotes de **Catalog** y la prueba de conexión. Cada fila guarda el prompt, la respuesta, el modelo, los idiomas, el número de tokens y el tiempo de la llamada. Las tarjetas y los gráficos están en **Dashboard**. Abrir esta página no envía ninguna petición nueva ni cambia las traducciones.

Los filtros y los gráficos siguen en **Dashboard**. Esta página es solo la lista.

Columnas: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** y **Prompt**. Tipos: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** y **Not sent** (la llamada no se envió, por ejemplo por el límite local o el presupuesto). Una fila **Bulk job** muestra el número del trabajo.

- **View** abre el prompt y la respuesta, con **HTTP**, **Sent**, **Received** y **Total**. Si hay un error, la respuesta es el texto del error. **Back to the list** vuelve a la tabla. Si la fila ya no existe: **This history row no longer exists.**
- Un error de acceso significa que la clave de **Settings** es incorrecta o que la cuenta no puede usar el modelo elegido.
- **Previous**, **Next** y **Page** cambian de página en la lista.
- **Clear history** pregunta **Clear the stored history? Saved translations stay.** Después aparece **History cleared. Saved translations were not changed.** La ayuda del botón dice **Clear history deletes these rows only. Saved translations stay.**

Si la lista está vacía, verá **No requests yet.**

Si las traducciones se detienen de repente, abra aquí la fila de error más reciente antes de cambiar el glosario.

### 3.11. Updates

Abra **Updates** en el extremo derecho de la barra del módulo. El título del formulario es **MyPresta Updates**.

![Updates, back office en inglés. Manual Check, Automatic Notifications y Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** contiene **Check Now**. Comprueba la versión al instante.
- **Automatic Notifications** tiene el estado **Enabled** o **Disabled**. **Enabled** es el valor si nunca se ha guardado una elección. Cuando está activado, el módulo comprueba si MyPresta tiene una versión más nueva y puede mostrar un aviso en el back office.
- **Product Page** es un enlace a la página de contacto que usa este módulo.
- **Save** guarda la elección. Mensaje: **Update settings saved.**

Tras **Check Now**: **New version available!** o **Module is up to date!**

### 3.12. Botones en International → Translations

Abra **International → Translations**. Los botones junto a los campos aparecen cuando **Individual field buttons — International → Translations** está activado. Las casillas y la barra aparecen cuando **Individual field checkboxes — International → Translations** está activado.

Lo que verá:

- Un botón **Translate** junto a cada campo de texto.
- Una casilla en cada campo, cuando las casillas están activadas.
- Una barra con el título **Claude translations**, con **Source** (en-US, o el **Source locale** de **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** y la indicación **Fills the fields. Save with the PrestaShop button.** **Translate empty in this section** rellena los campos vacíos de la sección actual.

Pasos:

1. Elija **Target**.
2. Marque los campos o pulse **Check empty**.
3. Pulse **Translate selected** o **Translate empty**.
4. Espere a que la barra muestre **Done**. Mientras trabaja, el estado es **Translating…** con un contador. Si no marca nada, la barra dice **Tick at least one field.**
5. Revise los campos rellenados y guarde la página con el botón **Save** de PrestaShop.

Los botones solo rellenan los campos. Sin el botón **Save** de PrestaShop, el texto no llega a la tienda. Con **Allow publish / save** desactivado, los campos se rellenan igualmente, y el botón **Save** de PrestaShop guarda la página.

Mensajes:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** En **Emails**, el texto de origen procede del archivo de la plantilla de correo, no de un campo de la página. Elija otro **Source locale** que tenga esos archivos de correo.

### 3.13. Botones en los formularios de producto, categoría y CMS

Abra un producto, una categoría, una página CMS u otro formulario de la tienda con campos multilingües. Los botones aparecen cuando **Individual field buttons — shop forms** está activado. Las casillas y la barra aparecen cuando **Individual field checkboxes — shop forms** está activado.

Lo que verá:

- Un botón **Translate** junto a cada campo multilingüe.
- Una casilla para la barra.
- Una barra con el título **Claude translations**, con **Translate from** y **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** y la indicación **Fills the fields. Save with the PrestaShop button.**

Pasos:

1. Rellene el campo en el idioma de origen. Si está vacío, la barra dice **Fill the source language field first.**
2. Elija el idioma de destino en la barra.
3. Pulse el botón de un campo, o marque varios campos y pulse **Translate selected**. **Translate empty** rellena los campos vacíos.
4. Pulse **Save** en el formulario de PrestaShop. Sin este paso, el texto no se guarda.

El botón solo rellena el campo del formulario. Los campos que no marque se quedan sin cambios.

## 4. Tienda

El módulo no añade nada a la página que ve el cliente. No hay ningún bloque, botón ni mensaje en la tienda, así que el tema no tiene nada que mostrar para este módulo.

La única dirección fuera del back office es la dirección cron. Sirve para una tarea programada en el servidor. No es para los clientes.

- Cópiela desde **Settings**, campo **CRON URL**, o desde la línea **CRON** del **Dashboard**.
- Péguela en el programador de tareas del servidor, por ejemplo para que se ejecute cada pocos minutos. Cada llamada procesa una tanda de un trabajo en espera.
- Use la dirección `https://` si la tienda tiene SSL activado.

| Qué ve al abrir la dirección | Qué hacer |
|---|---|
| **Forbidden** | La dirección está incompleta o se ha modificado. Cópiela de nuevo desde **Settings**. |
| **No pending jobs** | No hay ningún trabajo en `pending` ni en `running`. Cree uno en **Bulk** o reanude un trabajo pausado en **Jobs**. |
| Un resultado JSON con `ok`, `finished` y `counts` | Se ha procesado una tanda. Revise el progreso en **Jobs**. |

La dirección cron solo procesa los trabajos en `pending` y `running`. Un trabajo `paused` hay que reanudarlo en **Jobs**.

## 5. Problemas

| Qué ve | Causa | Qué hacer |
|---|---|---|
| **No Claude API key.** en todas las páginas del módulo | No hay ninguna clave guardada. | Abra **Settings**, pegue la clave en **Claude API key** y pulse **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Se guardaron los ajustes sin clave. | Pegue la clave y pulse **Save**. |
| **Connection was not made. Nothing was translated.** después de **Test connection** | Clave incorrecta, sin conexión con Anthropic, o un modelo que la cuenta no puede usar. | Compruebe la clave, elija otro **Model** o añada el identificador correcto en **Add a Claude model**. Lea la fila en **History**. |
| Errores de acceso en **History** | La clave es incorrecta o la cuenta no puede usar el modelo seleccionado. | Corrija la clave o elija un modelo que la cuenta pueda usar. |
| **Nothing was started. There is no Claude API key.** en **Bulk** | No hay clave. | Pegue la clave en **Settings** y después vuelva a pulsar **Estimate** y **Start job**. |
| Un trabajo se queda en `pending` | Un trabajo no arranca solo. | Pulse **Process slice** o **Auto-process** en **Jobs**, o configure la dirección cron (sección 4). |
| Un trabajo está `paused` con **Rate limit — job auto-paused. Resume later.** | Claude rechazó llamadas por un límite de frecuencia. | Espere unos minutos y pulse **Resume**. Baje **Batch size** o **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Se alcanzó **Budget USD / month**. | Suba el importe o póngalo a 0. Un mes nuevo empieza desde cero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** está desactivado. | Active **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** en **Manual** | La traducción cambió marcadores de posición o etiquetas HTML. | Corrija la fila en **Review before save** para que los marcadores y las etiquetas coincidan con el original y pulse **Save approved**. |
| Un trabajo termina como `completed_with_errors` | Algunas cadenas fallaron. | Abra el trabajo, pulse **Failed only**, descargue **Error CSV** y pulse **Retry failed**. |
| Filas de **Review** con un **Score** bajo | El control de calidad las envió a la cola. | Lea **Source** y **AI**. Pulse **Approve** o **Reject**. Si ya se guardó un texto incorrecto, use **Rollback** en el trabajo. |
| La traducción se guardó, pero la tienda sigue mostrando el texto antiguo | La caché de esa página no se actualizó. El módulo vacía la caché al guardar una traducción de catálogo, una tanda de un trabajo masivo o al hacer un rollback. | Vacíe la caché en el back office de PrestaShop. |
| Una exclusión no omite la cadena | **Type** incorrecto o un **regex** que no coincide con nada. | En **Excludes**, elimine el patrón y añada uno más corto con el **Type** adecuado. |
| Un término nuevo del glosario no cambia las traducciones guardadas | El glosario se lee en la siguiente traducción. Los textos guardados se conservan. | Vuelva a traducir esos textos en **Bulk** con **Overwrite all**, después de revisar **Estimate**. |
| **The source language mail file was not found.** | El origen elegido no tiene archivo de correo. | Elija otro **Source locale** en **Settings**, u otro **Source** en la página de traducciones, que tenga los archivos de correo. |
| **No strings match this filter. Nothing was sent to Claude.** | El filtro no coincide con nada. | Desactive **Only empty**, borre **Search** o elija otro dominio. |
| **Nothing was translated. Tick at least one row.** | No se marcó ninguna fila. | Marque las filas y pulse **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** en **Catalog** | El origen y el destino son el mismo idioma. | Elija otro **Target language**. |
| **Catalog finished** dejó **Start after ID** por delante de las filas que fallaron | El campo se fija en el ID más alto de la tanda, incluidas las filas con error. | Ponga **Start after ID** por debajo del registro que falló y ejecute la tanda de nuevo. |
| La cobertura del Dashboard está vacía | La tienda todavía no tiene catálogo para esa configuración regional. | Cree uno en **International → Translations** y vuelva a **Dashboard**. |
| **History** muestra **Not sent** | El límite local o el presupuesto detuvo la llamada antes de enviarla. | Revise **Rate limit / min** y **Budget USD / month** en **Settings**. |
| **The shop needs at least two languages.** | La tienda tiene un solo idioma. | Añada un idioma en **International → Localization → Languages**. |

## 6. Para desarrolladores

### 6.1. Descripción general

- Clase principal: `myaitranslationsclaude`, archivo `myaitranslationsclaude.php`.
- Versión: 1.2.0.
- Nombre técnico: `myaitranslationsclaude`. Nombre en la lista de módulos: **AI Translations with Claude**.
- Autor: MyPresta.eu. Pestaña en Module Manager: `administration`.
- Pestaña del back office: `AdminMyaitranslationsclaude`, con padre `AdminInternational` y padre alternativo `IMPROVE`. La etiqueta visible de la pestaña es `AI Translations with Claude`. `ensureTab()` repara una pestaña que falta. `renameTabIfTechnical()` sustituye un nombre de pestaña que todavía es el nombre técnico.
- Instalación: `parent::install()`, tablas definidas en `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (escribe una clave solo si falta), los hooks `displayBackOfficeHeader` y `actionAdminControllerSetMedia`, y después la pestaña.
- Desinstalación: elimina la pestaña, ejecuta `sql/uninstall.php` (borra 11 tablas), `removeConfiguration()` borra las claves `MYAITCL_*` listadas allí y después se llama a `parent::uninstall()`. No borra `mypresta_updates`, `update_myaitranslationsclaude` ni `updatev_myaitranslationsclaude`.
- No hay `enable()` ni `disable()`.
- `getContent()` llama a `ensureTab()` y redirige a `AdminMyaitranslationsclaude` (pestaña predeterminada `dashboard`).

Flujo de datos:

1. El formulario de ajustes envía un POST a `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` guarda los `MYAITCL_*` en `Configuration`. `MyaitclApiKeyEncryptor` cifra la clave de API con AES-256-CBC, usando una clave derivada de `_COOKIE_KEY_`, y la guarda como `MYAITCL_API_KEY_ENC`. Una clave enviada vacía o un valor enmascarado no sustituye la clave guardada.
3. Traducción: `MyaitclTranslateService::translateMessages()` construye los prompts (`MyaitclPromptBuilder`), los envía mediante `MyaitclClaudeTranslationProvider` (POST con cURL a `https://api.anthropic.com/v1/messages`, cabecera `anthropic-version: 2023-06-01`), comprueba la respuesta (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), la puntúa (`MyaitclQualityScorer`) y la guarda a través de `MyaitclTranslationAdapter`.
4. Cuando **Max tokens** es 0, el proveedor envía `max_tokens` con 4096. `acceptsTemperature()` envía **Temperature** solo si el identificador del modelo coincide con `claude-(opus|sonnet|haiku)-4-(0|1|5|6)`.
5. El guardado del catálogo usa el servicio de traducciones de PrestaShop si existe; si no, usa la tabla `_DB_PREFIX_translation`. Las claves de los módulos clásicos las escribe `MyaitclLegacyModuleCatalogue` en `translations/{iso}.php` de ese módulo.
6. Bulk: `MyaitclBulkJobFactory` inserta filas en `myaitcl_job` y `myaitcl_job_item`. `MyaitclJobWorker::processSlice()` ejecuta una tanda del tamaño de `BATCH_SIZE`. La llaman **Process slice**, el bucle de **Auto-process** (AJAX `ProcessJob`) y `controllers/front/cron.php`.
7. Catalog: `MyaitclCatalogTranslateService::collect()` lee como máximo 100 filas. `translateAndSave()` escribe en `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`. Los resultados se emparejan por ID. Tras la tanda, **Start after ID** pasa a ser el `id_entity` más alto del conjunto recogido, incluidas las filas que fallaron.
8. Cada llamada se guarda en `myaitcl_request` (**History**). Los errores también van a `myaitcl_api_log`. El coste se registra en `myaitcl_usage_ledger`. `MyaitclSnapshotService` copia el valor anterior en `myaitcl_snapshot` para **Rollback**. `clearTranslationCache()` llama a `Tools::clearCache()` tras guardar el catálogo, tras una tanda que no sea de prueba y tras un rollback.

### 6.2. Archivos

| Archivo | Función |
|---|---|
| `myaitranslationsclaude.php` | Instalación, desinstalación, pestaña, hooks, recursos, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Comprobación de actualizaciones para la pestaña **Updates** y el aviso del back office. Clase `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logotipo en la cabecera del módulo. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Todas las pestañas del back office, guardados, acciones de trabajo, glosario, exclusiones, catálogo, CSV y AJAX. |
| `controllers/front/cron.php` | Dirección cron. Procesa una tanda y devuelve JSON. |
| `sql/install.php`, `sql/uninstall.php` | Crean y eliminan las tablas. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Interfaz de lectura y escritura de las traducciones de PrestaShop. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Secciones, dominios, configuraciones regionales, guardado mediante el servicio o la tabla `translation`, vaciado de caché. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Adaptador concreto. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Crea el adaptador. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Lee los catálogos XLF de temas y módulos. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Módulos clásicos: lee y escribe `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Formularios del back office y texto `desc` de los campos. |
| `src/Admin/MyaitclSectionHelp.php` | Texto del panel **Help** de cada pestaña. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History**: filas, tarjetas, gráficos, filtros, borrado y retención. |
| `src/Audit/MyaitclApiLogRepository.php` | Registro de errores y avisos de la API, y su retención. |
| `src/Audit/MyaitclTranslationMemory.php` | Reutiliza un resultado para el mismo texto, configuración regional, modelo y glosario. |
| `src/Audit/MyaitclUsageLedger.php` | Estimación del coste con la tabla de precios de este archivo, y el presupuesto mensual. |
| `src/Audit/MyaitclSnapshotService.php` | Copias antes de una escritura y su restauración en **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Lista del glosario, inserción y borrado. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Inserción, borrado y coincidencia de exclusiones. |
| `src/Job/MyaitclJobStatuses.php` | Constantes de estado de trabajos y filas. |
| `src/Job/MyaitclJobRepository.php` | Trabajos y filas: lectura, estado, siguiente tanda, contadores. |
| `src/Job/MyaitclJobWorker.php` | Procesamiento de tandas, reintentos, cierre, cola de revisión y correo al terminar. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Interfaz del proveedor. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Llamadas a Claude, prueba de conexión, registro de peticiones. |
| `src/Provider/MyaitclPromptBuilder.php` | Prompts de sistema y de usuario: tono, voz de marca, glosario. |
| `src/Provider/MyaitclProviderFactory.php` | Crea el proveedor. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Comprobación de marcadores de posición y etiquetas. |
| `src/Quality/MyaitclHtmlValidator.php` | Comprobación de HTML. |
| `src/Quality/MyaitclPsNativeValidator.php` | Comprobación antes de un guardado en **Manual**. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Protege el HTML del correo antes de la llamada y lo restaura después de la respuesta. |
| `src/Quality/MyaitclQualityScorer.php` | Puntuación de 0 a 100, flags y decisión de revisión. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Cifrado y descifrado de la clave de API. |
| `src/Service/MyaitclConfigService.php` | Lectura y guardado de ajustes, modelos, token cron y rangos. |
| `src/Service/MyaitclRateLimiter.php` | Límite local por minuto, archivo `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Exclusiones, memoria, llamadas, validación, puntuación, guardado y estimación. |
| `src/Service/MyaitclBulkJobFactory.php` | Crea un trabajo de **Bulk** y la estimación. |
| `src/Service/MyaitclCatalogTranslateService.php` | Recoge y guarda las filas de **Catalog**. |
| `src/Service/MyaitclDashboardService.php` | Recuentos de cobertura en **Dashboard**. |
| `translations/*.php` | Traducciones de la interfaz, un archivo por idioma. |
| `views/templates/admin/configure.tpl` | Página del módulo y el panel **Help**. |
| `views/templates/admin/_partials/*.tpl` | Pestañas: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Estilos del back office. |
| `views/js/admin.js` | Progreso de **Jobs** y **Auto-process**, selección de filas, AJAX. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Botones y barra en **International → Translations**. |
| `views/js/entity-fields.js` | Botones y barra en los formularios de producto, categoría y CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Gráficos en **Dashboard**. |
| `var/rate_limit.json` | Contador del límite local por minuto. |
| `index.php` en cada directorio | Impide listar el contenido del directorio. |

### 6.3. Controladores

**Back office: `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsclaude&token=…`, con `&myaitcl_tab=` opcional y los valores `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (la etiqueta de la pestaña es **History**), `settings` o `updates`.
- Acciones de trabajo, mediante el parámetro `job_action` junto con `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` y `export_errors`. La plantilla no muestra un botón Cancel. `filter_failed=1` limita la tabla de filas.
- Acciones de revisión: `review_action=approve|reject` e `id_review`.
- Glosario: `delete_glossary`. Exclusiones: `delete_exclude`. Modelos: `delete_claude_model`, y un POST `new_claude_model` con `submitMyaitranslationsclaudeAddModel`.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail` y los endpoints de traducción de campos que usan `translations-tool.js` y `entity-fields.js`.

**Front: `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- URL de la tienda: `module/myaitranslationsclaude/cron`.
- El parámetro `token` debe coincidir con `MYAITCL_CRON_TOKEN` (`hash_equals`). Si falta o no coincide, la respuesta es HTTP 403 con el JSON `{"ok":false,"error":"Forbidden"}`.
- `id_job`, opcional, procesa ese trabajo. Sin él, se procesa el primer trabajo `pending` o `running`.
- Una tanda correcta devuelve JSON con `ok`, `finished` y `counts`. Si no hay ningún trabajo en espera, el cuerpo es `{"ok":true,"message":"No pending jobs"}`.
- `ssl` es true en el controlador.

### 6.4. Hooks

Hooks registrados:

- `displayBackOfficeHeader` - cambia la etiqueta técnica de la pestaña y después carga CSS y JS.
- `actionAdminControllerSetMedia` - carga los mismos recursos.

`translations-tool.js` se añade en el controlador de traducciones. `entity-fields.js` se añade en los formularios de la tienda cuando los interruptores de campo están activados. `Media::addJsDef` publica `myaitclTr` (URL de AJAX, configuración regional de origen, idiomas y etiquetas de la barra).

El módulo no registra ningún hook propio que otros módulos deban implementar. No hay `enable()` ni `disable()`.

### 6.5. Sobrescrituras

El módulo no sobrescribe ninguna clase ni ningún controlador de PrestaShop.

### 6.6. Base de datos

| Tabla | Contenido |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, id de tienda y fechas. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`) y `enabled`. |
| `myaitcl_job` | Una ejecución masiva: configuraciones regionales, `scope_json`, `policy_json`, `dry_run`, contadores, totales de tokens, coste, empleado, error y marcas de tiempo. |
| `myaitcl_job_item` | Una cadena de un trabajo: dominio, clave, tema, configuración regional, origen, valor anterior, valor nuevo, estado, motivo de omisión, error, tokens y validación. |
| `myaitcl_memory` | Memoria de traducción: hash, origen, configuración regional, traducción, modelo y número de aciertos. |
| `myaitcl_usage_ledger` | Filas diarias de tokens y coste, id de trabajo opcional y modelo. |
| `myaitcl_snapshot` | Valor anterior a una escritura del trabajo, usado por **Rollback**. |
| `myaitcl_api_log` | Filas de error y aviso: nivel, proveedor `claude`, código HTTP, mensaje y contexto. |
| `myaitcl_request` | Filas de **History**: tipo, estado, modelo, configuraciones regionales, código HTTP, duración, tokens, coste, empleado, trabajo, prompt, respuesta y error. |
| `myaitcl_review` | Cola de revisión: elemento del trabajo, estado, puntuación, flags y empleado. |
| `myaitcl_catalog_item` | Filas de una tanda de **Catalog**: entidad, campo, idiomas, origen, valor anterior, valor nuevo, estado y error. |

Al desinstalar se eliminan las once tablas. La instalación usa `CREATE TABLE IF NOT EXISTS`, así que reinstalar sobre una base de datos que todavía tiene las tablas conserva esas filas. Una desinstalación normal las borra antes. No se añade ninguna columna la primera vez que se visita una página.

### 6.7. Claves y traducciones

Prefijo `MYAITCL_`. Valores que se usan cuando falta una clave; son también los que se escriben al instalar:

| Clave | Valor si falta |
|---|---|
| `API_KEY_ENC` | vacío |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | vacío |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vacío |
| `BATCH_SIZE` | `25` (al guardar se vuelve a acotar a 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vacío |
| `TEMPERATURE` | `0.2` (al guardar se vuelve a acotar a 0-1) |
| `DRY_RUN_SAMPLE` | `10` (al guardar se vuelve a acotar a 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (mínimo 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vacío |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (el proveedor envía entonces 4096) |
| `CRON_TOKEN` | 16 bytes aleatorios en hexadecimal, generados al instalar |

`removeConfiguration()` también borra los nombres antiguos `DEEPL_API_KEY` y `CLAUDE_API_KEY` con el mismo prefijo. No borra las claves del comprobador de actualizaciones.

Las descripciones de los campos son las cadenas `desc` de `src/Admin/MyaitclForms.php`, que `help()` compone a partir de la finalidad, la forma de configurarlo y su efecto. La ayuda de las pestañas está en `src/Admin/MyaitclSectionHelp.php`.

Las cadenas de la interfaz pasan por `$this->l()` o por `{l s=... mod='myaitranslationsclaude'}`. Para añadir un idioma, cree `translations/{iso}.php`. Los errores de trabajo **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.** y **Monthly API budget has been exhausted.** son cadenas en inglés que devuelven `MyaitclJobWorker` y `MyaitclTranslateService`, no llamadas a `$this->l()`. Las cadenas de **Updates** usan el dominio de traducción `updatechecker`.

### 6.8. Ampliación

La tienda no muestra ninguna plantilla del módulo, así que el tema no tiene nada que sobrescribir.

Las plantillas del back office están en `views/templates/admin/`. PrestaShop no permite sobrescribirlas desde el tema. Cambie las etiquetas en `translations/{iso}.php`. Los botones de **International → Translations** y de los formularios de la tienda los inyectan `views/js/translations-tool.js` y `views/js/entity-fields.js` usando `myaitclTr`. No existe ningún hook con el que un tema pueda sustituir esa barra.

## 7. Ayuda

Página del módulo: https://mypresta.eu/es/ia-inteligencia-artificial/traducciones-ia-con-claude.html

Para escribirnos sobre este módulo, inicie sesión en su cuenta de cliente de mypresta.eu, abra el formulario de contacto y elija el asunto **Support for paid modules**. El formulario indica que para los módulos de pago es necesario iniciar sesión. Una vez dentro, elija este módulo en su historial de compras.
