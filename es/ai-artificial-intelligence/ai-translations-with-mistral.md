---
title: "AI Translations with Mistral – documentación y manual de usuario"
description: "Guía de configuración y resolución de problemas para quienes usan el módulo AI Translations with Mistral."
sidebar:
  label: "AI Translations with Mistral – documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with Mistral en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Requisitos

El módulo funciona con PrestaShop 1.7.0.0 o una versión posterior.

- **PrestaShop:** 1.7.0.0 o superior.
- **PHP:** la versión que exige su PrestaShop. El módulo no fija un mínimo propio.
- **Extensiones de PHP:** cURL (conexión con Mistral), OpenSSL (cifrado de la clave API), SimpleXML (lectura de los archivos de traducción XLF) y mbstring.
- **Otros módulos:** el módulo no depende de ningún otro.
- **Fuera de la tienda:** una cuenta en Mistral AI y una clave API, que puede crear en https://console.mistral.ai/api-keys. El servidor de la tienda tiene que poder salir por HTTPS hacia `api.mistral.ai`.
- **Opcional:** una tarea programada en el servidor que llame a la dirección cron (descrita en 3.1). Sin ella, las tareas se procesan a mano en la pestaña **Jobs**.
- **Catálogos grandes:** traducir un dominio entero con miles de textos supone muchas llamadas a la API y más tiempo de espera. La tarea se divide en porciones del tamaño que indique **Batch size**. Antes de empezar, ejecute siempre **Estimate** en **Bulk**.
- La tienda necesita al menos dos idiomas. Con un único idioma, el back office muestra una advertencia, porque no hay nada que traducir.

## 2. Instalación

1. Vaya a **Modules** → **Module Manager**, pulse **Upload a module**, suba el archivo ZIP del módulo y pulse **Install** junto a **AI Translations with Mistral**.
2. Tras la instalación, **AI Translations with Mistral** aparece en el menú **International**.
3. La instalación no vacía la caché de la tienda. Al guardar una traducción, el módulo se encarga de limpiar la caché de PrestaShop.
4. Vaya a **AI Translations with Mistral** → **Settings** y pegue su clave de Mistral. Mientras no haya una clave guardada, el back office muestra el mensaje **No Mistral API key.**

**Desinstalación.** En **Module Manager** pulse **Uninstall** y confirme el aviso **Delete this module and its data (jobs, glossary, cache)?**

- Se eliminan: la entrada del menú, todas las tareas, el glosario, las exclusiones, el historial de llamadas, la cola **Review**, las copias guardadas para deshacer cambios, el resumen de costes y los ajustes del módulo (incluida la clave API).
- Se conservan los textos que el módulo guardó en la tienda: las traducciones del catálogo de PrestaShop y los archivos de traducción de los módulos clásicos en los que escribió. También se conservan los ajustes de comprobación de actualizaciones.
- Volver a instalar el módulo no recupera las tareas, el glosario ni el historial que se hayan borrado. Restablece los valores predeterminados y crea una dirección cron nueva.

## 3. Configuración y uso en el back office

Todo el módulo está en una sola página: **International** → **AI Translations with Mistral**. Arriba aparecen las pestañas **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** y **Settings**. La pestaña **Updates** está al final de la barra. El botón **Help** abre un panel que explica la pestaña en la que se encuentra.

Los nombres de campos y botones de este manual coinciden con los de la versión inglesa del back office. Si el panel está en otro idioma, verá su traducción. Las capturas también son de la versión inglesa.

Cada pestaña empieza con una frase que indica qué hace, cómo se usa y qué efecto tiene. La misma explicación, dividida en tres partes, aparece también debajo de los campos del formulario. El botón **Help**, en la esquina inferior derecha, la muestra para la pestaña actual. Abrir **Help** no traduce nada.

**El proceso de principio a fin**

Las traducciones las lanza un empleado de la tienda desde el back office. Los clientes no activan nada.

1. **Ajustes.** En **Settings** pegue su clave de Mistral, elija el modelo y el idioma de origen. Pulse **Test connection** y después **Save**. Sin clave, ningún método puede enviar texto a Mistral.
2. **Elija su forma de trabajar.**
   - Unas pocas frases o un dominio, con revisión antes de guardar: **Manual** (3.3).
   - Un dominio grande, un tema o un módulo: **Bulk**, y después trabaje la tarea en **Jobs** (3.4 y 3.5).
   - Campos de productos, categorías o páginas CMS: **Catalog** (lotes de hasta 100 registros, 3.7).
   - Campos sueltos en la página **International → Translations** (3.12) y en los formularios de producto, categoría y CMS (3.13).
3. **Control de calidad.** Cada texto traducido se revisa: variables, etiquetas y HTML. Un texto con errores no se guarda. Los textos con una puntuación inferior a 70, los que son demasiado largos (más de dos veces y media el original) o los que contienen palabras en inglés pasan a **Review**.
4. **Guardado.** Depende de la vía que use:
   - **Manual:** tras **Translate selected (review)** no se guarda nada hasta que pulse **Save approved**. Si marca **Save now (skip review)**, las filas correctas se guardan de inmediato.
   - **Bulk:** la tarea espera en **Jobs** y solo guarda cuando la procesa (**Process slice**, **Auto-process**) o cuando la procesa el cron. Una tarea de prueba (dry-run) no guarda nada.
   - **Catalog:** guarda las filas al momento en el idioma de destino elegido.
   - **La página International → Translations y los formularios de la tienda:** los botones solo rellenan los campos. El texto llega a la tienda cuando pulsa **Save** en PrestaShop.
   - Con **Allow publish / save** desactivado, ninguna de estas vías guarda texto en la tienda.
5. **Fin del trabajo.** Una tarea de **Jobs** termina con el estado **completed** (todo guardado) o **completed_with_errors** (hubo errores; véase 3.5). Las filas de **Review** desaparecen al pulsar **Approve** o **Reject**. El resultado de **Catalog** indica cuántas filas se guardaron y cuántas fallaron.

### 3.1. Página de configuración del módulo

Vaya a **Modules** → **Module Manager**, busque **AI Translations with Mistral** y pulse **Configure**. Se abrirá **Dashboard**. Pase a la pestaña **Settings**.

**Settings** es un único formulario. Los campos aparecen en el orden que se describe a continuación. Los botones **Save** y **Test connection** están al final del formulario, no arriba.

![Ajustes: clave, modelo, tono e idioma de origen (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Interruptores de los botones junto a los campos y límites (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Coste, correo, dirección cron y los botones Test connection y Save (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Conexión**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Mistral API key** | vacío | La clave de su cuenta de Mistral. Cópiela desde https://console.mistral.ai/api-keys. Deje el campo vacío para conservar la clave que ya tiene guardada. Un valor nuevo sustituye a la clave guardada; un campo vacío no la borra. La clave guardada aparece enmascarada. |
| **Model** | mistral-small-latest | El modelo de Mistral que traduce. La lista incluye mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest y codestral-latest. El modelo elegido se usa desde la siguiente traducción. Si su cuenta no puede usar un modelo, la llamada falla y el error queda registrado en **History**. |
| **Add a Mistral model** | vacío | Campo bajo la lista de modelos. Escriba el identificador exacto del modelo de su cuenta y pulse **Add model**. El modelo nuevo aparece en la lista y pasa a ser el activo. Debajo verá los modelos que añadió a mano, cada uno con un botón **Remove**. Los modelos integrados no se pueden eliminar. |

Mensajes tras estas acciones: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Estilo e idioma**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Tone** | Formal | Añade un estilo a cada instrucción: **Formal** para un tono oficial en la tienda y el back office, **Casual** para un tono más informal, y **Brand** junto con el campo **Brand voice**. Las traducciones nuevas usan el estilo elegido. Las ya existentes se mantienen hasta que las vuelva a traducir. |
| **Brand voice** | vacío | Aparece al elegir **Tone: Brand**. Unas frases que describen cómo debe sonar la tienda. Si lo deja vacío, no se añade ninguna descripción extra. El texto se incluye en las instrucciones siguientes, pero no modifica las traducciones ya guardadas. |
| **Source locale** | — | El idioma que el modelo trata como original. Lo normal es elegir en-US, el idioma en el que redacta sus catálogos. El signo **—** indica que el idioma de origen lo determina la pantalla desde la que traduce. Este ajuste no cambia el idioma predeterminado de la tienda. |
| **Individual field buttons — shop forms** | Yes | Un botón de traducción junto a cada campo multilingüe de los formularios de la tienda: producto, categoría, CMS y otros. Cada botón traduce solo su campo. Con **No** se ocultan estos botones en toda la tienda. Las traducciones guardadas no cambian. |
| **Individual field checkboxes — shop forms** | Yes | Los campos multilingües de los formularios reciben casillas de selección. La barra del pie del formulario traduce los campos marcados, uno tras otro. Con **No**, las casillas y la barra desaparecen. |
| **Individual field buttons — International → Translations** | Yes | Un botón junto a cada campo de la página **International → Translations**. Los formularios de la tienda no se ven afectados. |
| **Individual field checkboxes — International → Translations** | Yes | Casillas y barra en la página **International → Translations**. Con **No** desaparecen solo de esa página. |

**Límites y costes**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Batch size** | 25 | Cuántos textos van en una misma llamada. Para la primera ejecución le recomendamos entre 10 y 25. El valor debe estar entre 1 y 100. Un lote más grande termina la tarea con menos llamadas; si una llamada falla, se reintenta con una porción mayor. |
| **Dry-run sample** | 10 | Cuántos textos de muestra muestra **Estimate** en **Bulk**. El valor debe estar entre 1 y 50. La estimación no guarda nada. |
| **Max tokens (0 = default)** | 0 | El límite de longitud de una respuesta. Escriba 0 para usar el límite predeterminado de Mistral. Ponga un número si las respuestas se cortan o son demasiado largas. El cambio se aplica desde la siguiente llamada. |
| **Budget USD / month** | 0 | Un tope mensual en dólares, calculado a partir del resumen de costes. Escriba 0 si no quiere ningún tope. Al alcanzar la cantidad, se detienen las traducciones nuevas. El trabajo ya hecho se conserva. |
| **Rate limit / min** | 60 | Cuántas llamadas a la API puede hacer la tienda en un minuto. Escriba 0 para desactivar este límite local. Las llamadas que superen el límite se omiten y quedan registradas en **History**. Mistral puede aplicar además su propio límite. |
| **Temperature** | 0.2 | Cuánta libertad se toma el modelo al reformular el texto. Con 0.2 aproximadamente, se mantiene fiel al original; valores más cercanos a 1 cambian más las frases. El intervalo es 0–1. Las comprobaciones de variables y HTML siguen funcionando. |
| **Log retention days** | 30 | Cuántos días se conservan las entradas de **History**. El mínimo es 1. Las entradas más antiguas se borran. Las tareas, el glosario y las traducciones guardadas no se eliminan. |
| **Allow publish / save** | Yes | Si el módulo puede guardar traducciones en la tienda. Con **No**, el guardado queda bloqueado en **Manual** (botones **Save approved** y **Save now**), en **Bulk** (tareas que no son de prueba) y en **Catalog**. Los botones de las páginas solo rellenan campos; quien guarda es PrestaShop. |

Mensajes tras **Save**:

- **Settings saved. No translation was started.** (verde) – ajustes guardados; no se ha traducido nada.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (amarillo) – falta la clave; péguela.

**Correo y cron**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Email notify on complete** | No | Envía un correo cuando termina una tarea de **Bulk**. La tarea funciona igual; solo cambia el envío. |
| **Notify email** | vacío | La dirección que recibe el correo de fin de tarea. El campo aparece al activar **Email notify on complete**. Guardar la dirección por sí solo no envía ningún mensaje. |
| **CRON URL** | dirección con token | Una dirección que el servidor puede llamar para procesar una porción de una tarea pendiente. Cada llamada procesa una porción y termina. No publique esta dirección: cualquiera que la conozca puede lanzar una porción. Abrir **Settings** no inicia ninguna tarea. |

**Test connection** comprueba la clave y el modelo con una consulta breve. No traduce nada ni guarda nada. El resultado puede ser:

- **Connection OK (N ms). No translation was started.** – la conexión funciona.
- **Connection was not made. Nothing was translated.** con el motivo indicado – revise la clave y el modelo.

Para empezar, pegue la clave, elija el modelo y el idioma de origen y pulse **Test connection**. Deje el resto de valores en sus predeterminados mientras las tareas funcionen bien.

### 3.2. Dashboard

Acceso: la primera pestaña, **Dashboard**.

![Resumen de textos que faltan, filtros del historial y tarjetas de llamadas (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Gráficos de llamadas y de tokens (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Resúmenes y las diez últimas llamadas (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

El **Dashboard** tiene dos partes. La primera es el resumen de los textos que faltan. La segunda es el historial de llamadas a Mistral, en forma de tarjetas y gráficos. La página no traduce ni modifica textos.

**Resumen de textos que faltan**

- **Locale:** elija el idioma cuyos textos pendientes quiere contar.
- **Show:** actualiza la tabla para el idioma elegido.
- La tabla tiene las columnas **Section**, **Total**, **Missing** y **Done**. La columna **Done** incluye una barra de progreso. Las secciones son **Back office**, **Themes**, **Installed modules**, **Emails** y **Others**. **Missing** es el número de textos sin traducción en ese idioma.
- Tras pulsar **Show** aparece el mensaje **Coverage for [idioma]. This page only counts strings. Nothing was translated.**
- Bajo la tabla hay una fila **CRON** con la dirección cron, la misma que en **Settings**.
- Si la tabla está vacía, la tienda todavía no tiene catálogo para ese idioma. Lo crea en **International → Translations**.

**Historial de llamadas**

- **Filter** funciona con los preajustes **Today**, **7 days**, **30 days**, **This month** y **All time**, y con los campos **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** y **Prompt or reply contains**.
- Las tarjetas muestran **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** y **Estimated cost**. El coste es una estimación, no una factura.
- Gráficos: **Requests and errors**, **Tokens sent and received** y **Requests by model**.
- Debajo de los gráficos hay cinco resúmenes: **By day**, **By model**, **By type**, **By language** y **By employee**. Si hay llamadas en el intervalo, cada resumen es una tabla con las columnas **Group**, **Calls**, **Sent**, **Received** y **Total**. Si no hay llamadas, verá **No requests in this range.**
- **Latest prompts** muestra las diez llamadas más recientes, con las columnas **When**, **Status**, **Type**, **Languages** y **Preview**. Si la lista está vacía, aparece **No requests yet.** El botón **View** abre una ventana con la instrucción enviada y la respuesta. **See all** lleva a **History** (3.10).

Qué hacer a continuación: si una sección tiene la mayoría de los textos sin traducir, abra **Manual** para unos pocos o **Bulk** para todo el dominio.

### 3.3. Manual

Acceso: pestaña **Manual**.

![Filtro de Manual. El botón Filter está bajo el campo Search (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** traduce un dominio o un módulo, unas decenas de textos a la vez. Filtrar no guarda nada.

**Campos del filtro**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Section** | Back office | Elige el catálogo de PrestaShop que se lee: **Back office**, **Themes**, **Installed modules**, **Emails** u **Others**. Al cambiar de sección se recarga la página, se muestran solo los campos de esa sección y no se llama a Mistral. |
| **Theme** | — | Visible solo con **Themes**. Limita la lista a un tema. Los demás temas se omiten. |
| **Module** | — | Visible solo con **Installed modules**. Limita la lista a un módulo. Un módulo sin dominios (clásico) muestra todos sus textos a la vez. |
| **Domain** | — | Grupo de textos, igual que en **International → Translations**. Elíjalo y pulse **Filter**. Está oculto para los módulos clásicos y para las secciones sin dominios. |
| **Source** | en-US o el valor de **Settings** | El idioma del que toma los textos. Elija uno que ya tenga buenas traducciones. |
| **Target** | primer idioma de la lista | El idioma que quiere completar. Debe existir en **International → Localization → Languages**. |
| **Only empty** | Yes | Muestra solo los textos sin traducir. Si lo desactiva, verá todos los textos. Las traducciones guardadas no se borran. |
| **Search** | vacío | Deja solo los textos de origen que contengan la palabra escrita. |

Pasos:

1. Establezca **Section**, **Source** y **Target**.
2. En **Themes**, elija un **Theme**. En **Installed modules**, elija un **Module**.
3. Pulse **Filter**. La lista **Domain** se actualiza. Elija un dominio y pulse **Filter** otra vez. En un módulo clásico, omita el dominio: **Filter** cargará todos los textos del módulo.
4. Marque las filas que quiera. Para ello puede usar **Check all**, **Uncheck all** o las casillas de cada fila.
5. Tras **Filter**, la lista muestra las columnas **Source**, **Current** y **Status** (**empty** o **filled**). Encima de la lista están **Translate selected (review)** y la casilla **Save now (skip review)**.
6. Pulse **Translate selected (review)**. Aparecerá la tabla **Review before save** con las columnas casilla, **Source**, **AI proposal** y **Warnings**. Las filas correctas vienen marcadas. Desmarque las que no quiera y, si hace falta, corrija la propuesta en su campo. Pulse **Save approved** para guardar las filas marcadas.
7. En lugar del paso 6, puede marcar **Save now (skip review)** antes de traducir. Así, las filas correctas se guardan al instante, sin pasar por la tabla de revisión.

**Mensajes**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – la lista está lista.
- **No strings match this filter. Nothing was sent to Mistral.** – cambie el filtro o desactive **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – elija un dominio.
- **Nothing was translated. Tick at least one row.** – marque alguna fila.
- **Review is ready. Nothing is saved until you press Save approved.** – la traducción está lista; no se guardará hasta que pulse **Save approved**.
- **Saved. The approved strings were written for the target language.** – tras **Save now (skip review)** se guardaron las filas correctas.
- **Saved N. Only the ticked rows were written.** – tras **Save approved** se guardaron las filas marcadas.
- **Nothing was saved. Tick OK on the rows you want to keep.** – en la tabla de revisión no hay ninguna fila marcada. Marque las que quiera conservar y pulse **Save approved** de nuevo.
- **Not saved because of broken placeholders or HTML: N.** – N filas no superaron la comprobación y se omitieron. Corríjalas a mano en la tabla para que las variables y las etiquetas HTML coincidan con el original.
- **Nothing was saved. Turn on Allow publish in Settings.** – active **Allow publish / save**.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – la lista ha cambiado. Pulse **Filter** y vuelva a marcar las filas.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – módulo clásico, sin dominios. La lista está completa.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – el mismo caso, antes de pulsar **Filter**.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – elija un tema o un módulo.

### 3.4. Bulk

Acceso: pestaña **Bulk**.

![Alcance de la tarea Bulk (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Policy, prueba sin guardado y los botones Start job y Estimate (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** crea una sola tarea para varios dominios e idiomas. La estimación no guarda nada. **Start job** añade la tarea a la lista **Jobs**. Nada se guardará hasta que la tarea se procese y **Allow publish / save** esté activado.

**Campos**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Section** | Back office | El catálogo que lee la tarea. La misma elección que en **Manual**. |
| **Theme** / **Module** | — | Aparecen solo en la sección correspondiente, igual que en **Manual**. |
| **Source** | en-US o el valor de **Settings** | El idioma que se trata como original. Cada idioma de destino se traduce a partir de este. |
| **Targets** | ninguno | Uno o varios idiomas que completar. Para seleccionar varios, mantenga pulsada la tecla Ctrl (Cmd en Mac). Un clic normal sustituye la selección. |
| **Domains** | ninguno | Los dominios que abarca la tarea. Use Ctrl o Cmd para seleccionar varios. Si no marca ninguno, la tarea abarca todos los dominios de la sección elegida. |
| **Policy** | Fill empty | **Fill empty** envía solo los textos sin traducir. **Overwrite all** envía todos, también los ya traducidos, y puede sobrescribirlos. **Outdated if equals source** envía solo los textos cuya traducción es igual al original. |
| **Dry-run job** | No | El modelo hace el trabajo y la tarea aparece en **Jobs**, pero las respuestas no llegan a la tienda. Sirve para comprobar el coste y la calidad. |

**Pasos**

1. Elija la sección, el idioma de origen, los idiomas de destino, los dominios y la política.
2. Pulse **Estimate**. Encima del formulario aparecerá la estimación: número de textos, tokens previstos, coste y una muestra de textos.
3. Si la estimación le parece bien, pulse **Start job**. Se abrirá **Jobs** con la nueva tarea.
4. Procese la tarea en **Jobs** (3.5) o déjela en manos del cron.

**Mensajes**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – resultado de la estimación.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – la tarea está creada y en espera.
- **Nothing was started. Select at least one target language.** – no hay idioma de destino.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – elija un tema o un módulo.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – falta la clave.

### 3.5. Jobs

Acceso: pestaña **Jobs**.

![Lista de tareas. La lista vacía muestra No jobs yet. (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Lista de tareas**

Cuando no hay ninguna tarea, la tabla muestra **No jobs yet.**

Cada fila es una ejecución de **Bulk**. Columnas: **#**, **Status**, **Locales** (idioma de origen → idiomas de destino), **Progress** (hechos/total), **Cost**, **Employee** y **Date**. **Open** abre la tarea.

Estados de la tarea, tal como aparecen en pantalla:

- `pending` – en espera; todavía no se ha procesado nada. No arranca sola.
- `running` – en curso.
- `paused` – en pausa. No sigue procesando hasta que la reanude.
- `cancelled` – cancelada. Los textos que seguían en espera no se tradujeron.
- `completed` – todos los textos procesados sin errores.
- `completed_with_errors` – terminada, pero algunos textos fallaron.
- `failed` – la tarea terminó con un error.

**Pantalla de la tarea**

Al abrir una tarea verá el encabezado **Job #N**, el estado, el progreso (**done/total**), los contadores **failed** y **skipped**, el coste, el empleado y la etiqueta **dry-run** si la tarea es de prueba. La barra de progreso se actualiza sola cada 2–3 segundos mientras la tarea está abierta. La tabla de debajo muestra las filas de la tarea: **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** y **Error**.

Estados de las filas: `pending`, `processing`, `done`, `failed`, `skipped` (omitida porque coincide con una exclusión o porque el texto ya estaba traducido) y `rolled_back` (revertida).

**Botones**

- **Process slice** – procesa una porción (**Batch size** textos) y se detiene. Mensaje: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Si no queda nada por hacer: **The job has no more strings waiting.**
- **Auto-process** – repite porciones hasta que la tarea termine o se produzca un error. Funciona en el navegador, así que solo avanza mientras la pestaña esté abierta. Si cierra la pestaña, se detiene; la tarea se conserva y puede terminarla con otro **Process slice** o con el cron.
- **Pause** – pone la tarea en pausa. Mensaje: **Job paused. It will not translate more strings until you resume it.**
- **Resume** – la devuelve a la cola. Mensaje: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** La tarea no se reanuda sola.
- **Retry failed** – los textos con error vuelven a estar pendientes y la tarea regresa al estado de espera. Mensaje: **Retried N failed items.**
- **Rollback** – restaura la traducción anterior en los casos en que el módulo guardó una copia antes del cambio. Primero debe confirmar **Roll back this job?** Al terminar verá **Rollback: restored N translations.**
- **Error CSV** – descarga un archivo CSV con las filas que fallaron. Columnas: **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – muestra en la tabla solo las filas con error.
- **Review queue** – lleva a **Review** (3.6).

En la pantalla de la tarea no hay botón para cancelar. Para detenerla, use **Pause**.

**Pausa automática**

Si Mistral rechaza llamadas por un límite, la tarea se detiene sola con el estado `paused` y aparece en el campo de error el mensaje **Rate limit — job auto-paused. Resume later.** Espere un poco y pulse **Resume**. El ajuste **Rate limit / min** de **Settings** reduce el número de llamadas por minuto.

**Mensajes de error**

- **Nothing was translated.** seguido de **No Mistral API key. Nothing was translated.** – falta la clave y la tarea no arranca. Pegue la clave en **Settings**.
- **Allow publish is off in Settings.** – una tarea que no es de prueba no arrancará hasta que active **Allow publish / save**.
- **Monthly API budget has been exhausted.** – se ha agotado el presupuesto mensual. Aumente **Budget USD / month** o póngalo a 0.

### 3.6. Review

Acceso: pestaña **Review** o el botón **Review queue** en la pantalla de una tarea.

![Cola de Review. La lista vacía muestra The queue is empty. (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Encima de la tabla aparece el encabezado **Needs-review queue (quality score / flags).** **Review** recoge los textos que la comprobación de calidad no dejó pasar automáticamente. Muestra hasta las 100 filas más recientes.

Columnas: **ID**, **Score**, **Domain**, **Source**, **AI** (propuesta), **Flags** y los botones **Approve** y **Reject**. Si la lista está vacía, verá **The queue is empty.**

**Cómo leer una fila**

- **Score** – puntuación de 0 a 100. Por debajo de 70, la fila pasa a revisión.
- **Flags** – motivos por los que la fila se retuvo:
  - `validation_failed` – el texto no superó la comprobación de variables o de HTML.
  - `warning` – una advertencia menor de la comprobación.
  - `length_explosion` – la traducción es más de dos veces y media más larga que el original.
  - `too_short` – la traducción es claramente más corta que un original más largo.
  - `possible_untranslated` – quedan palabras en inglés en la traducción, por ejemplo the, and, with, your o please.
- **Source** – el texto original. **AI** – la propuesta del modelo.

**Approve** y **Reject** solo cambian el estado de la fila. Mensaje: **Review updated.** La fila desaparece de la lista. Esta acción no envía texto a la tienda ni modifica el resto del dominio.

Si la tarea ya había guardado resultados, es posible que la propuesta ya esté en la tienda. Para deshacer los cambios de una tarea, use **Rollback** en la pantalla de esa tarea, en **Jobs**.

### 3.7. Catalog

Acceso: pestaña **Catalog**.

![Lote de Catalog. El botón Translate batch (max 100) está bajo el campo Start after ID (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** traduce los campos de productos, categorías y páginas CMS guardados en los idiomas de la tienda. No afecta a **International → Translations**. Cada pulsación procesa como máximo 100 registros. El guardado se hace de inmediato en los datos del idioma de destino elegido.

**Campos**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Entity** | product | Qué se traduce: **product**, **category** o **cms**. Al cambiarlo se recarga la página y solo aparece la lista de campos de ese tipo. El cambio por sí solo no traduce nada. |
| **Fields** | todos los campos de la lista | Qué textos envía el lote. Marque solo los que deben cambiar. Los campos sin marcar no se envían ni cambian. Para productos: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Para categorías: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Para CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | primer idioma de la lista | El idioma del que se toman los textos. |
| **Target language** | primer idioma de la lista | El idioma al que va la traducción. Debe ser distinto del idioma de origen. |
| **Only empty** | Yes | Omite los campos que ya tienen texto en el idioma de destino. Desactívelo solo si quiere reemplazar el texto existente. |
| **Start after ID** | 0 | Omite los registros con un ID menor o igual al valor escrito. Después de un lote, el campo se sitúa en el último ID procesado. Pulse el botón otra vez para seguir avanzando. |

Botón: **Translate batch (max 100)**.

**Pasos**

1. Elija **Entity** y marque los campos.
2. Elija **Source language** y **Target language**.
3. Deje **Only empty** activado.
4. Pulse **Translate batch (max 100)**. El resultado será: **Catalog finished: saved N, failed M.**
5. Abra un producto en el idioma de destino y compruebe el resultado. Solo entonces desactive **Only empty** o pase al siguiente lote.

**Mensajes**

- **Nothing was translated. Select at least one field.** – marque algún campo.
- **Nothing was translated. Source and target language must be different.** – elija idiomas distintos.
- **Nothing was saved. Turn on Allow publish in Settings.** – active **Allow publish / save**.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – falta la clave.

### 3.8. Glossary

Acceso: pestaña **Glossary**.

![Añadir un término (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![Importación y exportación de CSV y lista de términos vacía (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

El glosario es una lista de palabras y frases que el modelo debe conservar o traducir siempre de la misma forma. Añadir una fila no cambia las traducciones ya guardadas, pero la siguiente traducción sí tendrá en cuenta la lista.

**Añadir un término**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Source term** | vacío, obligatorio | La palabra o expresión en el idioma de origen. Escríbala exactamente como aparece, con mayúsculas si importan. |
| **Target locale** | vacío | Limita la fila a un idioma, p. ej. pl-PL. Si está vacío, la fila se aplica a cualquier idioma de destino. |
| **Target term** | vacío | La traducción aprobada del término. Solo puede quedar vacío si **Do not translate** está activado. |
| **Do not translate** | No | Activado: el modelo copia el término sin cambios, p. ej. un nombre de marca, un SKU o una etiqueta. Desactivado: usa **Target term**. |

Botón: **Add**. Mensajes: **Glossary term added. Translations already stored were not changed.** o **Nothing was added. Type a source term.**

**Tabla**

Columnas: **Source**, **Locale**, **Target**, **Do not translate** (Yes o No) y el botón **Delete** de cada fila. Solo elimina esa fila. Mensaje: **Glossary term deleted.** Lista vacía: **No glossary terms yet.**

**Importación y exportación de CSV**

- **CSV file** – elija un archivo y pulse **Import CSV**. Mensaje: **Imported N rows.**
- Formato del archivo: la primera fila es el encabezado `source_term`, `target_locale`, `target_term`, `do_not_translate`. El encabezado siempre se omite. Las filas con menos de tres columnas también se omiten. En la cuarta columna, un valor vacío o 0 significa **No**, y cualquier otro valor significa **Yes**.
- La importación añade las filas del archivo. No comprueba si el término ya existe, así que importar dos veces el mismo archivo duplicará las entradas.
- **Export CSV** descarga la lista actual como `glossary.csv`. No necesita ningún archivo de entrada y no cambia nada.

Consejo: use términos cortos y exactos. Un término demasiado general se aplicará cada vez que aparezca.

### 3.9. Excludes

Acceso: pestaña **Excludes**.

![Patrones de exclusión. La lista vacía muestra No patterns yet. (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

Una exclusión es un patrón de texto de origen que el módulo nunca envía a Mistral. Ese texto se queda en la tienda tal cual. Las exclusiones se aplican en todas las vías: **Manual**, **Bulk**, **Catalog** y las páginas de traducción.

**Añadir un patrón**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Pattern** | vacío, obligatorio | Texto o expresión que se compara con cada texto de origen. Cómo se compara depende de **Type**. |
| **Type** | exact | **exact** – el texto completo debe coincidir. **prefix** – el texto empieza por el patrón. **contains** – el patrón aparece en cualquier posición. **regex** – expresión regular de PHP. |

Botón: **Add**. Mensaje: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Si el campo está vacío: **Nothing was added. Type a pattern.**

Un patrón de tipo **regex** se aplica exactamente como lo escribió. Una expresión mal formada no coincide con nada. Empiece con un patrón corto y compruebe qué ha omitido.

**Tabla**

Columnas: **Pattern**, **Type**, **On** y **Delete**. La columna **On** muestra 1 en los patrones activos. En esta pantalla no hay interruptor, así que para desactivar un patrón hay que eliminarlo y volver a añadirlo. **Delete** elimina solo ese patrón; las traducciones existentes no se borran. Mensaje: **Pattern deleted.** Lista vacía: **No patterns yet.**

Use las exclusiones para textos que deben quedarse en el idioma de origen, como una razón social o una marca técnica. Para los textos que siempre deben traducirse de la misma forma, use **Glossary**.

### 3.10. History

Acceso: pestaña **History** o el botón **See all** de **Dashboard**.

![Lista del historial. La lista vacía muestra No requests yet. (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** es la lista completa de llamadas registradas a Mistral: traducciones manuales, páginas de traducción, tareas de **Bulk**, **Catalog** y pruebas de conexión. Cada entrada incluye el texto enviado, la respuesta, el modelo, los idiomas, el número de tokens y la duración de la llamada. Las tarjetas, los gráficos y los filtros están en **Dashboard**, no en esta página. Abrir esta página no envía ninguna consulta ni cambia traducciones. La nota bajo el campo **Model** en **Settings** menciona **Logs**. Esas entradas están aquí. No hay una pestaña Logs aparte.

**Columnas de la lista:** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** y **Prompt**. Tipos: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** y **Not sent** (la llamada no salió, por ejemplo por el límite local o el presupuesto). En las entradas de **Bulk job** verá el número de la tarea.

- **View** abre una ventana con la instrucción enviada y la respuesta. Si hubo un error, en lugar de la respuesta aparece el mensaje de error.
- Una entrada con error de acceso significa que la clave de **Settings** es incorrecta o que la cuenta no tiene permiso para el modelo elegido.
- **Previous**, **Next** y el campo **Page** le permiten moverse por la lista.
- **Clear history** elimina estas entradas. Debe confirmarlo con el mensaje **Clear the stored history? Saved translations stay.** Después verá **History cleared. Saved translations were not changed.**

Si las traducciones se detienen de repente, abra la entrada con error más reciente en esta página antes de modificar el glosario.

### 3.11. Updates

Acceso: pestaña **Updates**, en el extremo derecho del menú.

![Comprobación de actualizaciones (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

El panel se llama **MyPresta Updates**.

- **Manual Check** – el botón **Check Now** comprueba la versión de inmediato.
- **Automatic Notifications** – **Enabled** o **Disabled**. Si está activado, el módulo consulta si hay una versión más reciente en el servidor de MyPresta y muestra un aviso en el back office.
- **Product Page** – enlace a la página del módulo.
- **Save** – guarda la opción elegida en **Automatic Notifications**.

Mensajes: **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Botones en la página International → Translations

Acceso: **International** → **Translations**. Elija el tipo de traducción y el idioma y pulse **Modify**. Los botones junto a los campos aparecen cuando en **Settings** está activado **Individual field buttons — International → Translations**. Las casillas y la barra aparecen cuando está activado **Individual field checkboxes — International → Translations**.

![Barra Mistral translations al pie de la página International → Translations (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**Qué verá**

- Junto a cada campo de texto, un botón que traduce ese campo.
- Junto a cada campo, una casilla de selección (si las casillas están activadas).
- Una barra con **Mistral translations**: el campo **Source** (en-US por defecto o el valor de **Settings**), la lista **Target**, los botones **Check all**, **Uncheck all**, **Check empty**, **Translate empty** y **Translate selected**, y la indicación **Fills the fields. Save with the PrestaShop button.**

**Pasos**

1. Elija **Target**.
2. Marque los campos que quiere rellenar o pulse **Check empty**.
3. Pulse **Translate selected** o **Translate empty**, que rellena todos los campos vacíos de la sección.
4. Espere hasta que la barra muestre **Done (N)**. Mientras trabaja verá **Translating… N/M**.
5. Revise los campos rellenados y guarde la página con el botón **Save** de PrestaShop.

Los botones solo rellenan los campos. Sin **Save** de PrestaShop, el texto no llega a la tienda. Con **Allow publish / save** desactivado, los campos también se rellenan, pero el guardado lo hace PrestaShop.

**Mensajes**

- **Target is not a language from this shop.** – el idioma elegido no existe en esta tienda.
- **Fill the source language field first.** – complete primero el campo del idioma de origen.
- **The source language field is not on this page.** – en esta página no hay un campo para el idioma de origen.
- **The source language mail file was not found.** – no se encontró el archivo de origen del correo. Elija en **Settings** otro **Source locale** para el que existan archivos de correo.

En la sección **Emails**, el texto de origen procede del archivo de origen de la plantilla de correo, no de un campo de la página.

### 3.13. Botones en los formularios de producto, categoría y CMS

Acceso: el formulario de un producto, una categoría, una página CMS u otro formulario de la tienda con campos multilingües. Los botones aparecen cuando en **Settings** están activados **Individual field buttons — shop forms** e **Individual field checkboxes — shop forms**.

![Barra al pie del formulario de producto y casilla junto a un campo multilingüe (pantalla en inglés).](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**Qué verá**

- Junto a cada campo multilingüe, un botón que traduce ese campo.
- Junto a los campos, una casilla para añadirlos a la barra.
- Una barra al pie de la página del producto, con la etiqueta **Mistral translations**, la lista de idiomas **Translate from … to …**, los botones **Check all**, **Uncheck all**, **Check empty**, **Translate empty** y **Translate selected**, y la indicación **Fills the fields. Save with the PrestaShop button.**

**Pasos**

1. Rellene el campo en el idioma de origen. Sin ello, la barra mostrará **Fill the source language field first.**
2. Elija el idioma de destino en la barra.
3. Pulse el botón de un campo concreto, o marque varios campos y pulse **Translate selected**. **Translate empty** rellena los campos vacíos.
4. Cuando termine, pulse **Save** en el formulario de PrestaShop. Si no lo hace, el texto no se guarda.

El botón solo rellena el campo del formulario. Lo guarda el botón **Save** del formulario de producto, categoría o CMS. Los campos que no haya marcado se quedan como estaban.

## 4. Frontend de la tienda

El módulo no añade nada a las páginas de la tienda que ven los clientes. Los clientes no tienen ninguna pantalla ni botón relacionado con el módulo, así que no hay nada que revisar en el tema.

La única dirección fuera del back office es la dirección cron. Está pensada para una tarea programada en el servidor y no para uso de los clientes.

- **Dónde copiarla:** **Settings** → **CRON URL**, o **Dashboard** → fila **CRON**.
- **Qué hacer:** pegue la dirección en el planificador de tareas del servidor, por ejemplo cada pocos minutos. Cada llamada procesa una porción de una tarea pendiente.
- **La dirección funciona por HTTPS.** Si la tienda tiene SSL activado, use la dirección que empieza por `https://`.

| Qué aparece al abrir la dirección | Qué hacer |
|---|---|
| El mensaje **Forbidden** | La dirección está incompleta o cambió. Cópiela de nuevo desde **Settings**. |
| El mensaje **No pending jobs** | No hay tareas en espera ni en curso. Cree una tarea en **Bulk** o reanude una pausada en **Jobs**. |
| Datos en formato JSON con el resultado de la porción (campos `ok`, `finished`, `counts`) | Se ha procesado una porción de la tarea. Revise el progreso en **Jobs**. |

El cron solo atiende las tareas en estado `pending` o `running`. Una tarea `paused` tiene que reanudarla usted a mano.

## 5. Problemas frecuentes

| Síntoma (lo que se ve) | Causa | Qué hacer |
|---|---|---|
| **No Mistral API key.** en todas las páginas del módulo | La clave no se guardó. | Vaya a **Settings**, pegue la clave en **Mistral API key** y pulse **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Se guardaron los ajustes sin clave. | Pegue la clave en **Mistral API key** y pulse **Save**. |
| **Connection was not made. Nothing was translated.** después de **Test connection** | Clave incorrecta, sin conexión con el servidor o modelo no disponible para la cuenta. | Revise la clave, elija otro **Model** o añada un identificador correcto en **Add a Mistral model**. Los detalles están en **History**. |
| Las llamadas fallan con un error de acceso en **History** | La clave es incorrecta o la cuenta no puede usar el modelo elegido. | Corrija la clave o elija un modelo disponible para su cuenta. |
| **Nothing was started. There is no Mistral API key.** en **Bulk** | No hay clave. | Pegue la clave en **Settings** y después vuelva a pulsar **Estimate** y **Start job**. |
| La tarea se queda en `pending` y no pasa nada | Las tareas no arrancan solas. | Pulse **Process slice** o **Auto-process** en **Jobs**, o configure el cron (sección 4). |
| La tarea está en `paused` con el mensaje **Rate limit — job auto-paused. Resume later.** | Mistral rechazó llamadas por un límite. | Espere unos minutos y pulse **Resume**. Reduzca **Batch size** o **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Se superó **Budget USD / month**. | Aumente la cantidad o póngala a 0. Cada mes nuevo empieza de cero. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** está desactivado. | Active **Allow publish / save** en **Settings**. |
| **Not saved because of broken placeholders or HTML: N.** en **Manual** | La traducción cambió variables o etiquetas HTML. | Corrija la fila a mano en la tabla de revisión, para que las variables y las etiquetas coincidan con el original, y guarde. |
| La tarea termina con el estado `completed_with_errors` | Algunos textos fallaron. | Abra la tarea, marque **Failed only**, descargue **Error CSV** y pulse **Retry failed**. |
| Las filas de **Review** tienen una **Score** baja | La comprobación de calidad no las aprobó. | Compare **Source** y **AI**. Apruebe con **Approve** o rechace con **Reject**. Si se guardó una traducción errónea, use **Rollback** en la tarea. |
| La traducción se guardó, pero la tienda sigue mostrando el texto antiguo | El guardado limpia la caché de PrestaShop, pero el tema o el navegador pueden conservar la página anterior. | Vaya a **Advanced Parameters** → **Performance**, limpie la caché y actualice la página de la tienda. |
| Una **Exclude pattern** no omite el texto | El **Type** es incorrecto o la expresión **regex** no es válida. | En **Excludes**, cambie el tipo, o elimine el patrón y añádalo de nuevo con un texto más corto. |
| Un término nuevo del glosario no se aplica en las traducciones guardadas | El glosario se aplica a las traducciones nuevas. Los textos guardados no se modifican. | Vuelva a traducir esos textos en **Bulk** con la política **Overwrite all**, tras revisar antes la estimación en **Estimate**. |
| **The source language mail file was not found.** | El idioma de origen elegido no tiene archivo de correo. | Elija en **Settings**, o en la página de traducciones, otro **Source locale** para el que existan archivos de correo. |
| **No strings match this filter. Nothing was sent to Mistral.** | El filtro no coincide con ningún texto. | Desactive **Only empty**, borre **Search** o elija otro dominio. |
| **Nothing was translated. Tick at least one row.** | No hay ninguna fila marcada. | Marque filas y pulse **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** en **Catalog** | El mismo idioma es el de origen y el de destino. | Elija otro **Target language**. |
| El Dashboard muestra un resumen vacío | La tienda todavía no tiene catálogo para el idioma elegido. | Cree el catálogo en **International → Translations** y vuelva a **Dashboard**. |
| El historial contiene entradas **Not sent** | El límite local o el presupuesto detuvo la llamada. | Revise **Rate limit / min** y **Budget USD / month** en **Settings**. |

## 6. Para desarrolladores

### 6.1. Resumen

- **Clase principal:** `myaitranslationsmistral`, archivo `myaitranslationsmistral.php`.
- **Versión:** 1.2.0.
- **Nombre técnico:** `myaitranslationsmistral`. En la lista de módulos aparece como **AI Translations with Mistral**.
- **Autor:** MyPresta.eu. Pestaña del módulo en Module Manager: `administration`.
- **Pestaña del back office:** `AdminMyaitranslationsmistral`, con padre `AdminInternational` (alternativa: `IMPROVE`).
- **Instalación:** `parent::install()`, tablas definidas en `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), valores predeterminados mediante `installDefaults()` (solo se establecen las claves que falten), registro de los hooks `displayBackOfficeHeader` y `actionAdminControllerSetMedia`, y creación de la pestaña.
- **Desinstalación:** elimina la pestaña, ejecuta `sql/uninstall.php` (borra 11 tablas), elimina las claves `MYAITMI_*` con `removeConfiguration()` y, por último, llama a `parent::uninstall()`.
- El módulo **no** tiene métodos `enable()` ni `disable()`.
- **Configuración:** `getContent()` redirige a `AdminMyaitranslationsmistral` (por defecto, la pestaña `dashboard`).

**Flujo de datos**

1. Los formularios de `MyaitmiForms` (pestaña `settings`) envían sus valores a `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` guarda las claves `MYAITMI_*` en `Configuration`. `MyaitmiApiKeyEncryptor` cifra la clave API (AES-256-CBC, con clave derivada de `_COOKIE_KEY_`) y la guarda en `MYAITMI_API_KEY_ENC`.
3. Traducción: `MyaitmiTranslateService::translateMessages()` construye las instrucciones (`MyaitmiPromptBuilder`), las envía con `MyaitmiMistralTranslationProvider` (cURL, POST a `https://api.mistral.ai/v1/chat/completions`), revisa la respuesta (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), la puntúa (`MyaitmiQualityScorer`) y la guarda a través de `MyaitmiTranslationAdapter`.
4. Guardado de la traducción: mediante el servicio `prestashop.service.translation` y, si ese servicio no existe, directamente en la tabla `_DB_PREFIX_translation`. Las claves de los módulos clásicos (con formato `<{nombre}prestashop>…`) se escriben en el archivo `translations/{iso}.php` de ese módulo (`MyaitmiLegacyModuleCatalogue`).
5. Bulk: `MyaitmiBulkJobFactory` crea la tarea y sus filas en `myaitmi_job` y `myaitmi_job_item`. `MyaitmiJobWorker::processSlice()` procesa una porción (tamaño según `BATCH_SIZE`). La invocan el botón **Process slice** (petición de la pestaña **Jobs**), el bucle **Auto-process** del navegador (AJAX `ProcessJob`) o el cron (`controllers/front/cron.php`).
6. Catalog: `MyaitmiCatalogTranslateService` selecciona los registros (`collect()`, máx. 100) y los guarda directamente en `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` o `_DB_PREFIX_cms_lang`.
7. Cada llamada se registra en `myaitmi_request` (pestaña **History**) y los errores en `myaitmi_api_log`. El coste va a `myaitmi_usage_ledger`. Antes de que una tarea cambie un texto, `MyaitmiSnapshotService` copia el valor anterior en `myaitmi_snapshot`, lo que permite deshacer con **Rollback**.

### 6.2. Archivos

| Archivo | Para qué sirve |
|---|---|
| `myaitranslationsmistral.php` | Clase principal: instalación, desinstalación, pestaña del menú, hooks, carga de assets, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Comprobación de actualizaciones (pestaña **Updates** y aviso en el back office). |
| `logo.png`, `logo.gif` | Logotipo en el encabezado de las pestañas y en el menú del módulo. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | Todo el back office: pestañas, guardados, acciones sobre tareas, glosario, exclusiones, catálogo, CSV y respuestas AJAX. |
| `controllers/front/cron.php` | Dirección cron: procesa una porción de una tarea y devuelve JSON. |
| `sql/install.php`, `sql/uninstall.php` | Creación y eliminación de tablas. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Interfaz de lectura y escritura de las traducciones de PrestaShop. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Lógica común del adaptador: listas de secciones, dominios e idiomas, guardado mediante el servicio o la tabla `translation`, limpieza de la caché. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | Adaptador concreto (lo crea la fábrica). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Crea el adaptador. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Lectura de los catálogos XLF de temas y módulos (dominios). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Módulos clásicos: lectura y escritura de `translations/{iso}.php`, limpieza de OPcache tras guardar. |
| `src/Admin/MyaitmiForms.php` | Construcción de todos los formularios del back office y de las descripciones de los campos (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Textos del panel **Help** de cada pestaña. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Historial de llamadas, tarjetas, gráficos, filtros, limpieza y retención. |
| `src/Audit/MyaitmiApiLogRepository.php` | Registro de errores y advertencias de la API, con retención. |
| `src/Audit/MyaitmiTranslationMemory.php` | Memoria de traducciones (caché): reutiliza el resultado para el mismo texto, idioma, modelo y glosario. |
| `src/Audit/MyaitmiUsageLedger.php` | Coste según la tabla de precios del código y presupuesto mensual. |
| `src/Audit/MyaitmiSnapshotService.php` | Copias previas al guardado y reversión de tareas. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glosario: listado, guardado y eliminación. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Exclusiones: alta, eliminación y coincidencia. |
| `src/Job/MyaitmiJobStatuses.php` | Constantes de los estados de tareas y filas. |
| `src/Job/MyaitmiJobRepository.php` | Tareas y filas: lectura, cambios de estado, obtención de porciones y recálculo de contadores. |
| `src/Job/MyaitmiJobWorker.php` | Procesamiento de porciones, reintento de errores, cierre de tareas, cola de revisión y correo al terminar. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Interfaz del proveedor de traducción. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Llamadas a Mistral (cURL), prueba de conexión y registro del historial. |
| `src/Provider/MyaitmiPromptBuilder.php` | Construcción de las instrucciones de sistema y de usuario (tono, voz de marca, glosario). |
| `src/Provider/MyaitmiProviderFactory.php` | Crea el proveedor. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Comprobación de variables y etiquetas en el texto. |
| `src/Quality/MyaitmiHtmlValidator.php` | Comprobación de la validez del HTML. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Comprobación previa al guardado en la sección **Manual**. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Protección del HTML de las plantillas de correo antes del envío y restauración tras la respuesta. |
| `src/Quality/MyaitmiQualityScorer.php` | Puntuación de 0 a 100, indicadores y decisión sobre la revisión. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Cifrado y descifrado de la clave API. |
| `src/Service/MyaitmiConfigService.php` | Lectura y escritura de ajustes, modelos, token de cron y validación de intervalos. |
| `src/Service/MyaitmiRateLimiter.php` | Límite local de llamadas por minuto (archivo `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Flujo principal de traducción: exclusiones, memoria, llamadas, validación, puntuación, guardado y estimación. |
| `src/Service/MyaitmiBulkJobFactory.php` | Construcción de la tarea **Bulk** y de la estimación. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Selección y guardado de los registros de **Catalog**. |
| `src/Service/MyaitmiDashboardService.php` | Resumen de textos pendientes en **Dashboard**. |
| `translations/*.php` | Traducciones de la interfaz (un archivo por idioma). |
| `views/templates/admin/configure.tpl` | Plantilla de toda la página del back office y del panel **Help**. |
| `views/templates/admin/_partials/*.tpl` | Pestañas: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Estilos del back office. |
| `views/js/admin.js` | Pestaña **Jobs** (progreso, **Auto-process**), marcado de filas y respuestas AJAX. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Botones y barra en **International → Translations**. |
| `views/js/entity-fields.js` | Botones y barra en los formularios de producto, categoría y CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Gráficos del **Dashboard**. |
| `var/rate_limit.json` | Contador del límite local de llamadas en el minuto actual. |
| `index.php` (en cada directorio) | Impide la navegación por los directorios. |

### 6.3. Controladores

**Back office: `AdminMyaitranslationsmistralController`** (clase `ModuleAdminController`, pestaña bajo `AdminInternational`).

- Dirección: `index.php?controller=AdminMyaitranslationsmistral&token=…`, opcionalmente `&myaitmi_tab=…`.
- Valores permitidos de `myaitmi_tab`: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Cualquier otro valor se trata como `dashboard`.
- Parámetros de entrada (GET/POST):
  - Ajustes: los campos `MYAITMI_*` del formulario, `new_mistral_model`, `delete_mistral_model` y los botones `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filtros y traducción: `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk: `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Tareas: `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Revisión: `review_action` (`approve`, `reject`) e `id_review`.
  - Catalog: `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glosario y exclusiones: `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (archivo), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - Historial y tarjetas: `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Devuelve una página HTML (`configure.tpl`) o un archivo: `glossary.csv` (exportación del glosario) o `job-{id}-errors.csv` (errores de la tarea).
- Los mensajes de éxito y error se pasan en los parámetros `flash` y `flash_kind` (`info`, `success`, `warning`, `danger`).

**Acciones AJAX del back office** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`):

| `action` | Parámetros | Devuelve |
|---|---|---|
| `ProcessJob` | `id_job` | Resultado de la porción: `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` y el objeto `job`. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → texto), `error`. No guarda nada. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | El archivo de origen del correo. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | Lista `domains`. |
| `HistoryDetail` | `hist_id` | Detalles de la llamada. |

**Front: `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- Dirección: `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, opcionalmente `&id_job=N`.
- `token` es obligatorio y se compara con `MYAITMI_CRON_TOKEN` mediante `hash_equals()`. Un token incorrecto devuelve el código 403 y el JSON `{"ok":false,"error":"Forbidden"}`.
- Con `id_job`: procesa una porción de esa tarea.
- Sin `id_job`: toma la primera tarea con estado `pending` o `running` de las 20 más recientes. Si no hay ninguna, devuelve `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hooks

Registrados durante la instalación:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: cambia el nombre técnico de la pestaña por su etiqueta (`renameTabIfTechnical()`) y carga los assets del back office (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: carga los assets (`loadBoAssets()`).

Assets que carga `loadBoAssets()`:

- En la pestaña del módulo: `admin.css`, `admin.js` y `admin-help.js`; en la pestaña **Dashboard**, además, `chart.min.js` e `history-charts.js`. `Media::addJsDef` con `aitHelpLabels`.
- En **International → Translations** (`AdminTranslations` o la dirección `/international/translations`), si están activados los botones de esa página: `admin.css` y `translations-tool.js`.
- En las demás páginas del back office (formularios de productos, categorías y CMS), si están activados los botones de formulario: `admin.css` y `entity-fields.js`.
- Datos para JS: `Media::addJsDef(['myaitmiTr' => …])` con la lista de idiomas, los locales, los indicadores de los botones y las etiquetas (`translationClientConfig()`).

El módulo no expone hooks propios (no hay `Hook::exec`).

### 6.5. Sobrescrituras

El módulo no sobrescribe ninguna clase ni controlador de PrestaShop. No hay directorio `override`.

### 6.6. Base de datos

Tablas creadas en `sql/install.php` (`_DB_PREFIX_` es el prefijo de la tienda, por defecto `ps_`). Todas usan el motor `_MYSQL_ENGINE_` y `utf8mb4_unicode_ci`.

| Tabla | Contenido |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Clave `idx_shop_locale` (`id_shop`, `target_locale`). Lectura: `id_shop` IN (0, tienda). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (siempre 1 al añadir), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (único), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Clave `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Clave `idx_job_status`. Una porción corresponde a un idioma de destino. |
| `myaitmi_memory` | Memoria de traducciones: `memory_hash` (único), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. La suma mensual es la que cuenta para el presupuesto. |
| `myaitmi_snapshot` | Copia previa al guardado: `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Registro de errores y advertencias: `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Retención según `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | Cola de revisión: `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Se crea al instalar y se elimina al desinstalar. El código del módulo no escribe en ella; **Catalog** guarda directamente en las tablas de idioma de la tienda. |
| `myaitmi_request` | Historial de llamadas: `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. `ensure()` también crea esta tabla en el primer guardado o al abrir **History**, si no existe. |

La desinstalación borra las 11 tablas de la lista anterior. Las tablas de traducciones de PrestaShop (`_DB_PREFIX_translation`) y las tablas de idioma de productos, categorías y CMS no se tocan.

### 6.7. Claves y traducciones

**Claves de `Configuration`** (prefijo `MYAITMI_`), con los valores predeterminados de `installDefaults()`:

| Clave | Por defecto | Notas |
|---|---|---|
| `API_KEY_ENC` | `''` | Clave API cifrada. Se lee con `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Modelo activo. |
| `EXTRA_MODELS` | `''` | Identificadores de modelos añadidos a mano, uno por línea. |
| `PROVIDER` | `mistral` | Siempre `mistral` tras guardar el formulario. |
| `TONE` | `formal` | `formal`, `casual` o `brand`. |
| `CUSTOM_VOICE` | `''` | Texto de **Brand voice**. |
| `BATCH_SIZE` | `25` | Intervalo 1–100. |
| `MONTHLY_BUDGET` | `0` | USD; 0 = sin límite. |
| `SOURCE_LOCALE` | `''` | Vacío = el idioma lo indica la pantalla. |
| `TEMPERATURE` | `0.2` | Intervalo 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Intervalo 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 desactiva el límite local. |
| `LOG_RETENTION_DAYS` | `30` | Mínimo 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Envía un correo al terminar una tarea (plantilla `contact`). |
| `NOTIFY_EMAIL` | `''` | Dirección del destinatario. Si está vacía, se usa `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Guardado en la tienda. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Botones y barra en los formularios de la tienda. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Botones y barra en la página de traducciones. |
| `MAX_TOKENS` | `0` | 0 = límite predeterminado del proveedor. |
| `CRON_TOKEN` | hex aleatorio de 32 caracteres | Token de la dirección cron. Si falta, se genera en la primera lectura. |

Claves que se eliminan al guardar el formulario o al desinstalar: `DEEPL_API_KEY` y `CLAUDE_API_KEY` (restos de versiones anteriores). Las claves de comprobación de actualizaciones (`mypresta_updates`, `update_{nombre}`, `updatev_{nombre}`) no se borran.

**Traducciones de la interfaz.** Cada idioma está en `translations/{iso}.php` (p. ej. `pl.php`, `de.php`, `fr.php`). El archivo `en.php` es la fuente de los textos. Los textos pasan por `$this->l()` o por los dominios `myaitmiforms` y `sectionhelp` (descripciones de campos y panel **Help**). Los textos de las plantillas se escriben como `{l s='…' mod='myaitranslationsmistral'}`. Los textos que se pasan a JS (`labels` en `translationClientConfig()` y `aitHelpLabels`) también pasan por `$this->l()`.

Para añadir un idioma: copie `translations/en.php` a `translations/{iso}.php`, traduzca los valores y conserve los identificadores de las claves.

### 6.8. Ampliación

- **Tema de la tienda:** el módulo no genera nada en el tema, así que no hay plantilla que sobrescribir.
- **Proveedor de traducción:** un proveedor nuevo necesita una clase que implemente `MyaitmiTranslationProviderInterface` y un cambio en `MyaitmiProviderFactory`. Actualmente la fábrica solo devuelve Mistral.
- **Adaptador de catálogo:** la interfaz `MyaitmiTranslationAdapterInterface` y la fábrica `MyaitmiTranslationAdapterFactory`.
- **Tarifas:** las tarifas por millón de tokens están en `MyaitmiUsageLedger::estimateCost()`. Si Mistral cambia sus precios, hay que actualizarlas en el código.
- **Límite local:** el archivo `var/rate_limit.json` se crea en el directorio del módulo.

## 7. Ayuda

Página del módulo: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

Si necesita ayuda con el módulo:

1. Inicie sesión en su cuenta de cliente en mypresta.eu.
2. Vaya al contacto y elija el tema **Support for paid modules**. El formulario indica que, en los módulos de pago, es necesario iniciar sesión.
3. Una vez dentro, elija este módulo en su historial de compras.
