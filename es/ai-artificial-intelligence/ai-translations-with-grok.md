---
title: "AI Translations with Grok - documentación y manual de usuario"
description: "Guía de configuración y solución de problemas para tiendas que ya usan AI Translations with Grok."
sidebar:
  label: "AI Translations with Grok - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo AI Translations with Grok en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Requisitos

El módulo funciona en PrestaShop 1.7.0.0 y posteriores, incluidas las versiones 8 y 9.

- **PrestaShop:** 1.7.0.0 o posterior.
- **PHP:** 5.6 o posterior.
- **Extensiones de PHP:** cURL, OpenSSL, SimpleXML y mbstring.
- **Otros módulos:** no necesita ninguno.
- **Fuera de la tienda:** una cuenta de xAI y una clave API de Grok de la consola de xAI. El servidor de la tienda debe poder conectarse a `https://api.x.ai/v1/chat/completions`.
- **Opcional:** una tarea en el programador del servidor que abra la dirección cron que aparece en **Configuración**. Sin ella, tendrá que procesar los trabajos a mano en **Trabajos**.
- **Catálogos grandes:** un dominio con miles de cadenas supone muchísimas llamadas a la API. Un trabajo se divide en porciones del tamaño de **Tamaño de lote (Batch size)**. Antes de empezar, pulse **Estimar** en **Masivo (Bulk)** para ver el número de cadenas y el coste aproximado.
- La tienda necesita al menos dos idiomas. Con uno solo, el back office muestra **La tienda necesita al menos dos idiomas.** y no hay nada que traducir.

## 2. Instalación

1. Abra **Módulos** y después **Gestor de módulos**. Elija la opción para subir un módulo, suba el archivo ZIP y pulse **Instalar** en **AI Translations with Grok**.
2. Cuando termine la instalación, **AI Translations with Grok** aparecerá en el menú **Internacional**.
3. La instalación no vacía la caché de la tienda. El módulo la vacía cuando guarda una traducción.

Después, abra **AI Translations with Grok**, vaya a **Configuración** y pegue su clave de Grok. Mientras no haya una clave guardada, cada página del módulo muestra **No hay clave API de Grok.** con el enlace **Abrir configuración**.

**Desinstalación.** En el **Gestor de módulos**, pulse **Desinstalar** y confirme **¿Eliminar este módulo y sus datos (trabajos, glosario, caché)?**

- La entrada del menú desaparece. Se borran los trabajos, el glosario, los patrones de exclusión, el historial de llamadas, la cola de **Revisar**, las copias para revertir, el registro de costes y los ajustes del módulo, incluida la clave API.
- El texto que el módulo ya escribió en la tienda se conserva: las traducciones del catálogo y los archivos de traducción de los módulos clásicos que escribió. También se conserva su elección sobre la comprobación de actualizaciones.
- Al volver a instalar, no se recuperan los trabajos, el glosario ni el historial que se borraron. Se restauran los valores iniciales y se crea una dirección cron nueva.

## 3. Configuración y uso diario

Todo el módulo está en una sola página: **Internacional** y, dentro, **AI Translations with Grok**. Las pestañas son **Panel de control**, **Manual**, **Masivo (Bulk)**, **Trabajos**, **Revisar**, **Catálogo**, **Glosario**, **Exclusiones**, **Historial** y **Configuración**. **Actualizaciones** está al final de la barra. **Ayuda** abre el panel de la pestaña en la que esté. La pestaña **Actualizaciones** no tiene botón **Ayuda**.

Las capturas de este manual son del back office en inglés. Los nombres de botones y campos que aparecen en el texto son los del back office en español.

El trabajo habitual tiene cuatro pasos.

1. **Conexión.** En **Configuración**, pegue la clave, elija el modelo, pulse **Probar conexión** y después **Guardar**.
2. **Prueba pequeña.** En **Manual**, filtre un dominio, marque unas cuantas cadenas vacías y tradúzcalas. Revise el resultado antes de traducir el catálogo completo.
3. **Trabajo.** En **Masivo (Bulk)**, elija la sección, los idiomas y los dominios, pulse **Estimar** y después **Iniciar tarea**. Abra el trabajo y pulse **Procesar porción** o **Procesamiento automático**, o deje que lo haga la dirección cron.
4. **Control.** Abra **Revisar** para ver las filas que retuvo el control de calidad, y **Historial** cuando una llamada falle. El botón **Revertir** del trabajo restaura el texto anterior, siempre que el módulo haya guardado una copia.

El módulo nunca inicia una traducción por su cuenta. **Estimar**, **Filtrar** y **Guardar** en **Configuración** no escriben texto del catálogo. Un trabajo permanece en **Jobs** hasta que lo procese o lo llame la dirección cron.

### 3.1. Configuración del módulo

Abra **Módulos**, **Gestor de módulos**, busque **AI Translations with Grok** y pulse **Configurar**. Se abre el **Panel de control**. Pase a **Configuración**.

**Guardar** y **Probar conexión** están al final del formulario. Guardar el formulario no inicia ninguna traducción ni sobrescribe las que ya están guardadas.

![Configuración, back office en inglés. Parte superior: clave API, modelo, añadir modelo, tono y configuración regional de origen.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Conexión**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Clave API de Grok** | vacío | La clave secreta que la tienda envía a Grok. Pegue la clave de la consola de xAI. Si deja el campo vacío, se conserva la clave ya guardada. Si escribe un valor nuevo, lo sustituye. Un campo vacío no borra la clave. Cuando hay una clave guardada, la ayuda muestra **Clave guardada:** seguida de la clave enmascarada. |
| **Modelo** | grok-4.7 | El modelo de Grok que escribe la traducción. La lista incluye los modelos integrados: grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning y grok-4.20-0309-reasoning. Los modelos que añada usted se pueden quitar. La siguiente traducción usará el modelo seleccionado. Si su cuenta no puede usar un modelo, la llamada falla y el error aparece en **Historial**. |
| **Añadir un modelo de Grok** | vacío | Escriba el identificador exacto de su cuenta de xAI y pulse **Añadir modelo**. El texto de ejemplo es grok-4.7. El identificador nuevo aparece en **Modelo** y pasa a ser el modelo activo. **Eliminar** solo borra los identificadores que añadió aquí. Los integrados no se pueden eliminar. |

Mensajes que puede ver: **Modelo añadido.**, **Modelo eliminado.**, **Ese modelo ya está en la lista. Ahora es el modelo activo.**, **Introduce un id de modelo, por ejemplo grok-4.7.**, **Los modelos integrados no se pueden eliminar.**

**Voz y origen**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Tono** | Formal | Añade una instrucción de estilo a cada prompt. **Formal** es para textos de la tienda y del back office, **Casual** suena más ligero, y **Marca** se usa junto con **Voz de marca**. Las traducciones nuevas seguirán ese estilo. Las que ya están guardadas no cambian hasta que las vuelva a lanzar. |
| **Voz de marca** | vacío | Solo se muestra cuando **Tono** está en **Marca**. Escriba unas frases sencillas sobre cómo debe sonar la tienda, o déjelo vacío. El texto se incluye en el siguiente prompt. Si está vacío, no se añade ninguna voz extra. No reescribe las traducciones ya guardadas. |
| **Configuración regional de origen** | vacío | El idioma que el modelo considera el original. La opción vacía aparece como una raya en la lista y significa que el origen es la pantalla que está traduciendo. Normalmente elegirá la configuración regional en la que están escritos sus catálogos, por lo general en-US. **Manual**, **Masivo (Bulk)** y los iconos de **Internacional → Traducciones** usan esa configuración como origen. El idioma predeterminado de la tienda no cambia. |
| **Botones de campo individual — formularios de la tienda** | Sí | Un botón junto a cada campo multilingüe de los formularios de la tienda: producto, categoría, CMS y otros formularios del back office. El botón traduce solo ese campo. **No** oculta estos botones en toda la tienda. Las traducciones guardadas no se modifican. |
| **Casillas de verificación de campo individual — formularios de la tienda** | Sí | Cada uno de esos campos recibe una casilla, y la barra traduce solo los campos marcados. **No** oculta las casillas ni la barra. Los botones de arriba tienen su propio interruptor. |
| **Botones de campo individual — Internacional → Traducciones** | Sí | Un botón en cada campo de **Internacional → Traducciones**. **No** oculta estos botones. Los formularios de la tienda no se ven afectados. Un clic rellena ese campo. Para guardar la página sigue usando el botón **Guardar** de PrestaShop. |
| **Casillas de verificación de campo individual — Internacional → Traducciones** | Sí | Casillas y barra en **Internacional → Traducciones**. **No** las oculta. Los formularios de la tienda no se ven afectados. |

**Límites**

![Configuración, back office en inglés. Tamaño de lote y los campos de límite que van debajo.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Tamaño de lote (Batch size)** | 25 | Cuántas cadenas van en una llamada a la API. Para la primera prueba, use entre 10 y 25. El valor debe quedarse entre 1 y 100. Un lote más grande termina el trabajo con menos llamadas, pero si falla, se reintenta un trozo más grande. |
| **Muestra de prueba (Dry-run)** | 10 | Cuántas cadenas de ejemplo muestra **Estimar** antes de un trabajo masivo. El valor debe quedarse entre 1 y 50. **Estimar** muestra esas cadenas de origen y una estimación de coste. No guarda ninguna traducción. |
| **Tokens máx. (0 = predeterminado)** | 0 | Limita la longitud de una respuesta. Déjelo en 0 para usar la longitud predeterminada de Grok. Escriba un número si las respuestas se cortan o si quiere que sean más breves. El límite solo afecta a la siguiente llamada y no acorta las traducciones ya guardadas. |
| **Presupuesto USD / mes** | 0 | Tope mensual en dólares, calculado a partir del registro de uso. 0 significa sin tope. Escriba el importe que quiere permitir desde el primer día del mes. Cuando el registro llegue a ese importe, las traducciones nuevas se detienen y la pantalla muestra **Monthly API budget has been exhausted.** El trabajo ya guardado se conserva. |
| **Límite de tasa / min** | 60 | Cuántas llamadas a la API puede iniciar esta tienda en un minuto. 60 es un punto de partida prudente. 0 desactiva este límite local. Las llamadas que superen el límite se omiten y se registran en **Historial**. Grok puede aplicar además su propio límite. |
| **Días de retención de logs** | 30 | Cuántos días de filas se conservan en **Historial**. El mínimo es 1. Las filas más antiguas se eliminan cuando se guarda una llamada nueva. Este número no borra trabajos, glosario ni traducciones guardadas. |
| **Temperatura** | 0.2 | Cuánta libertad tiene el modelo para reformular una frase. Un valor cercano a 0,2 se mantiene fiel al original. Los valores más cercanos a 1 cambian más las frases. El valor debe quedarse entre 0 y 1. Los marcadores y el HTML se comprueban después. La siguiente traducción usará este valor. |
| **Permitir publicar / guardar** | Sí | Indica si el módulo puede escribir traducciones en PrestaShop. **No** bloquea el guardado desde **Manual**, desde los trabajos masivos ni desde **Catálogo**. Los iconos de la página de traducciones y de los formularios de la tienda solo rellenan el formulario. El botón **Guardar** de PrestaShop es independiente. |

Tras pulsar **Guardar**, verá uno de estos mensajes:

- **Configuración guardada. No se inició ninguna traducción.** Los ajustes están guardados y no se ha traducido nada.
- **Configuración guardada. No hay clave API almacenada, por lo que no se puede traducir hasta que pegues una.** Pegue la clave en **Clave API de Grok** y pulse **Guardar** de nuevo.

**Correo y cron**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Notificación por correo al completar** | No | Envía un correo cuando termina un trabajo masivo. El trabajo se ejecuta igual; solo cambia si se envía el correo. |
| **Correo de notificación** | vacío | La dirección que recibe ese correo. El campo solo aparece cuando el interruptor de arriba está activado. Si está vacío, se usa el correo de la tienda. Guardar la dirección no envía ningún mensaje. El asunto empieza con el nombre del módulo, el número del trabajo y el estado. |
| **URL de CRON** | dirección con token | La dirección secreta con la que el servidor puede procesar una porción de un trabajo en espera. Cópiela en el programador del servidor y no la publique. Quien conozca la dirección puede lanzar una porción. Abrir **Configuración** no inicia ningún trabajo. |

**Probar conexión** comprueba la clave y el modelo con una llamada corta. No traduce ni guarda nada.

- **Conexión correcta (N ms). No se inició ninguna traducción.** La conexión funciona.
- **No se pudo establecer la conexión. No se tradujo nada.** seguido del motivo. Revise la clave y el modelo. Los detalles están en **Historial**.

Para empezar, lo práctico es pegar la clave, elegir el modelo y la configuración regional de origen, pulsar **Probar conexión** y después **Guardar**. Mantenga los valores numéricos de la instalación hasta que un trabajo empiece a fallar.

### 3.2. Panel de control

Abra la pestaña **Panel de control**. Cuenta las cadenas que faltan en el catálogo y después muestra el uso de Grok en tarjetas, gráficos y los diez prompts más recientes. La página no traduce ni modifica cadenas.

![Panel de control, back office en inglés. Cobertura de una configuración regional, línea cron y filtros del historial.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Cobertura**

- **Configuración regional:** la configuración de la tienda cuyas cadenas faltantes se cuentan.
- **Mostrar:** vuelve a dibujar la tabla para esa configuración regional.
- Columnas: **Sección**, **Total**, **Faltantes**, **Hecho** y una barra de progreso. Las secciones son **Back office**, **Plantillas**, **Módulos instalados**, **Emails** y **Otros**. **Faltantes** es el número de cadenas que no tienen traducción en esa configuración regional.
- Debajo de la tabla, **CRON** muestra la misma dirección que **URL de CRON** en **Configuración**.
- Una tabla vacía significa que la tienda todavía no tiene catálogo para esa configuración regional. Créelo en **Internacional → Traducciones**.

Tras pulsar **Mostrar**, el mensaje es **Cobertura para {configuración regional}. Esta página solo cuenta cadenas. No se tradujo nada.**

**Uso**

- Preajustes: **Hoy**, **7 días**, **30 días**, **Este mes** y **Todo el tiempo**.
- Filtros: **Desde**, **Hasta**, **Modelo**, **Tipo**, **Estado** (**Cualquiera**, **Éxito**, **Error**), **Idioma**, **Empleado** y **El prompt o la respuesta contiene**. Pulse **Filtrar**.
- Tarjetas: **Solicitudes**, **Éxito**, **Errores**, **Tokens enviados**, **Tokens recibidos**, **Tokens totales**, **Tiempo promedio** y **Coste estimado**. El coste estimado es un cálculo local, no una factura de xAI. Una raya indica que Grok no devolvió el número de tokens de esa llamada.
- Gráficos: **Solicitudes y errores**, **Tokens enviados y recibidos** y **Solicitudes por modelo**. Debajo hay grupos: **Por día**, **Por modelo**, **Por tipo**, **Por idioma** y **Por empleado**, con las columnas **Grupo**, **Llamadas**, **Enviado**, **Recibido** y **Total**. Un grupo sin datos muestra **No hay solicitudes en este rango.**
- **Últimos prompts** muestra las diez llamadas más recientes. **Ver** abre el prompt y la respuesta. **Ver todo** abre el **Historial** (apartado 3.10). Si la lista está vacía, aparece **Aún no hay solicitudes.**

Filtrar no borra el historial ni cambia las traducciones.

Si una sección está casi vacía, abra **Manual** para unas pocas cadenas o **Masivo (Bulk)** para todo un dominio.

### 3.3. Manual

Abra **Manual**. Sirve para traducir un dominio o un módulo clásico, unas decenas de cadenas cada vez. Filtrar no guarda nada.

![Manual, back office en inglés. Sección, origen, destino, dominio, solo vacíos y buscar.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Sección** | Back office | Qué catálogo se lee: **Back office**, **Plantillas**, **Módulos instalados**, **Emails** u **Otros**. Al cambiar de sección se recarga la página y solo aparecen los campos de esa sección. No llama a Grok. |
| **Tema** | vacío | Solo para **Plantillas**. Limita la lista a un tema. |
| **Módulo** | vacío | Solo para **Módulos instalados**. Limita la lista a un módulo. Un módulo clásico sin dominio carga todas las cadenas de ese módulo. |
| **Dominio** | vacío | La misma agrupación que en **Internacional → Traducciones**. Elija uno y pulse **Filtrar**. Se oculta en los módulos clásicos y en las secciones sin dominios. La fila vacía muestra una raya con el texto de selección. |
| **Origen** | **Configuración regional de origen** de **Configuración**, o en-US | El idioma del que se toman las cadenas. Elija uno que ya tenga un buen texto. |
| **Destino** | el primer idioma de la lista | El idioma que quiere completar. Debe existir en **Internacional → Localización → Idiomas**. |
| **Solo vacíos** | Sí | Muestra solo las cadenas sin traducción. Si lo desactiva, aparecen todas las cadenas. Las traducciones guardadas no se borran. |
| **Buscar** | vacío | Deja solo las cadenas de origen que contienen la palabra que escriba. |

Pasos:

1. Ajuste **Sección**, **Origen** y **Destino**.
2. En **Plantillas**, elija un **Tema**. En **Módulos instalados**, elija un **Módulo**.
3. Pulse **Filtrar**. La lista **Dominio** se actualiza. Elija un dominio y vuelva a pulsar **Filtrar**. En un módulo clásico, omita el dominio: **Filtrar** carga todas las cadenas del módulo.
4. Marque las filas que quiera. **Marcar todo** y **Desmarcar todo** seleccionan o limpian la lista.
5. Pulse **Traducir seleccionados (revisar)**. Se abre la tabla **Revisar antes de guardar**, con las columnas **Origen**, **Propuesta de IA** y **Advertencias**. Quite la marca de las filas que no quiera guardar y corrija la propuesta directamente en el campo. Después pulse **Guardar aprobados**.
6. También puede marcar **Guardar ahora (omitir revisión)** antes de traducir. Las filas válidas se guardan al instante, sin pasar por la tabla de revisión.

Las columnas de la lista de cadenas son **Origen**, **Actual** y **Estado** (**vacío** o **relleno**).

Mensajes que puede ver:

- **Se cargaron N cadenas. Marque las filas que quiera y pulse Traducir seleccionados. Todavía no se ha guardado nada.**
- **Se cargaron N cadenas de todo el módulo. Marque las filas que quiera y pulse Traducir seleccionados. Todavía no se ha guardado nada.** Es la lista de un módulo clásico.
- **Este módulo no tiene dominio de traducción. Pulse Filtrar para cargar todas las cadenas del módulo. No se envió nada a Grok.**
- **Ninguna cadena coincide con este filtro. No se envió nada a Grok.**
- **Ninguna cadena coincide con este filtro. Desactive Solo vacíos o este módulo no tiene cadenas clásicas. No se envió nada a Grok.**
- **No se tradujo nada. Elija un dominio y pulse Filtrar para cargar las cadenas.**
- **No se tradujo nada. Elija un tema y pulse Filtrar.**
- **No se tradujo nada. Elija un módulo y pulse Filtrar.**
- **No se tradujo nada. Marque al menos una fila.**
- **No se tradujo nada. No hay clave API de Grok. Abra Configuración y pegue la clave.**
- **La revisión está lista. No se guardará nada hasta que pulse Guardar aprobados.**
- **Guardado. Las cadenas aprobadas se escribieron para el idioma de destino.**
- **Se guardaron N. Solo se escribieron las filas marcadas.**
- **No se guardó nada. Marque OK en las filas que quiera conservar.**
- **No se guardó por marcadores o HTML dañados: N.** Esas filas se omitieron. Ajuste los marcadores y las etiquetas para que coincidan con el origen y guarde de nuevo.
- **No se guardó nada. Active Permitir publicación en Configuración.**
- **No se tradujo nada. Esas filas no están en la lista actual. Pulse Filtrar y vuelva a marcarlas.**

Al cambiar de sección también aparece una línea breve, por ejemplo **La sección es Back office. No se usan el tema ni el módulo.**, junto con **No se envió nada a Grok.** El mismo patrón se usa para **Plantillas**, **Módulos instalados**, **Emails** y **Otros**.

### 3.4. Masivo

Abra **Masivo (Bulk)**. Crea un único trabajo para varios dominios e idiomas. **Estimar** no guarda nada. **Iniciar tarea** añade una fila en **Trabajos**. No se escribe nada hasta que el trabajo se procesa y **Permitir publicar / guardar** está activado.

![Masivo, back office en inglés. Sección, origen, destinos, dominios, política y tarea de prueba.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Sección** | Back office | Qué catálogo lee el trabajo. La página se recarga y muestra **Tema** solo en **Plantillas**, y **Módulo** solo en **Módulos instalados**. Las cadenas fuera de esa sección no entran. Cambiar de sección no inicia el trabajo. |
| **Tema** | vacío | Solo para **Plantillas**. Los demás temas quedan fuera. |
| **Módulo** | vacío | Solo para **Módulos instalados**. Un módulo clásico no tiene dominios, así que **Estimar** e **Iniciar tarea** abarcan todas sus cadenas. |
| **Origen** | **Configuración regional de origen** de **Configuración**, o en-US | La configuración regional que el trabajo considera original. Cada destino se traduce desde esta configuración. |
| **Destinos** | ninguno marcado | Las configuraciones regionales que el trabajo va a completar. Marque una o varias. Un clic sin Ctrl sustituye la selección actual. El trabajo guarda un conjunto de cadenas por cada configuración regional marcada. |
| **Dominios** | ninguno marcado | Los dominios incluidos en el trabajo. Mantenga pulsado Ctrl o Cmd para marcar varias filas. Los dominios sin marcar se omiten. Déjelos todos sin marcar solo si quiere un trabajo vacío. Se oculta en los módulos clásicos. |
| **Política** | Rellenar vacíos | **Rellenar vacíos** omite las cadenas que ya tienen traducción. **Sobrescribir todo** envía todas las cadenas y reemplaza el trabajo ya hecho, siempre que el trabajo pueda guardar. **Desactualizado si es igual al origen** envía las cadenas cuya traducción sigue siendo idéntica al origen. |
| **Tarea de prueba (Dry-run)** | No | Ejecuta el modelo, pero no escribe la respuesta en PrestaShop. El trabajo aparece igualmente en **Trabajos**. Los archivos del catálogo y las traducciones de la base de datos no cambian. |

Pasos:

1. Ajuste **Sección**, **Origen** y **Destinos**.
2. En **Plantillas**, elija un **Tema**. En **Módulos instalados**, elija un **Módulo**.
3. Elija **Dominios** cuando aparezca la lista. Mantenga pulsado Ctrl o Cmd.
4. Pulse **Estimar**. Revise el recuento, la estimación de tokens, la estimación de coste y la **Muestra**. No se ha enviado nada a Grok ni se ha guardado nada. Verá el mensaje: **Solo estimación: N cadenas, ~N tokens, ~$N. No se envió nada a Grok ni se guardó nada.**
5. Pulse **Iniciar tarea**. El módulo abre ese trabajo. Verá el mensaje: **La tarea n.º N está en espera (N cadenas, est. $N). Aún no se ha ejecutado.**

Si falta una selección obligatoria, verá uno de estos mensajes:

- **No se inició nada. Seleccione al menos un idioma de destino.**
- **No se inició nada. Elija un tema.**
- **No se inició nada. Elija un módulo.**
- **No se inició nada. No hay clave API de Grok. Abra Configuración y pegue la clave. No se creó ninguna tarea.**

### 3.5. Trabajos

Abra **Trabajos**. La lista muestra todos los trabajos. Si está vacía, aparece **Aún no hay trabajos.**

![Trabajos, back office en inglés. La lista de trabajos con estado, idiomas, progreso, coste, empleado y fecha.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Columnas: **#**, **Estado**, **Idiomas (Locales)**, **Progreso**, **Coste**, **Empleado**, **Fecha** y **Abrir**.

Los estados de esta pantalla se quedan en inglés: **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** y **failed**.

Pulse **Abrir** en una fila. El detalle muestra el **Estado**, el progreso como hecho/total, **fallido**, **omitido**, el coste, el número de empleado y **simulación (dry-run)** si ese interruptor estaba activado. Debajo aparece una barra de progreso.

Botones del trabajo abierto:

- **Procesar porción** traduce un lote y se detiene. Mensaje: **Se procesó una porción. Revise las filas de abajo para ver qué se guardó, omitió o falló.** Cuando no queda nada, verá **La tarea no tiene más cadenas en espera.**
- **Procesamiento automático** pide la siguiente porción hasta que el trabajo termina o se detiene.
- **Pausar** detiene las porciones siguientes. Mensaje: **Tarea pausada. No traducirá más cadenas hasta que la reanude.**
- **Reanudar** devuelve un trabajo pausado a la espera. Mensaje: **La tarea vuelve a estar en espera. No se ejecuta sola. Pulse Procesar porción, Procesamiento automático o deje que la llame el cron.**
- **Reintentar fallidos** devuelve las filas fallidas a la cola. Mensaje: **Se reintentaron N elementos fallidos.**
- **Revertir** pregunta **¿Revertir este trabajo?** y restaura el texto anterior donde el módulo guardó una copia. Mensaje: **Reversión (rollback): se restauraron N traducciones.**
- **CSV de errores** descarga las filas fallidas.
- **Solo fallidos** muestra únicamente las filas con el estado **failed**.
- **Cola de revisión** abre **Revisar**.

En esta pantalla no hay botón para cancelar. Si no quiere que un trabajo termine, puede dejarlo en **paused**.

Las columnas de la tabla de filas son **ID**, **Dominio**, **Configuración regional**, **Estado**, **Origen**, **Nuevo** y **Error**. Los estados de cada elemento también se quedan en inglés: **pending**, **processing**, **done**, **failed**, **skipped** y **rolled_back**.

Si la tienda alcanza su propio límite por minuto durante una porción, el trabajo se pausa y la línea de error queda en inglés: **Rate limit — job auto-paused. Resume later.** Pulse **Reanudar** más tarde y después **Procesar porción**.

Un trabajo de prueba llama a Grok y guarda la propuesta en el trabajo. No escribe en el catálogo.

### 3.6. Revisar

Abra **Revisar**. Es la cola de revisión de los trabajos masivos. La página indica **Cola de revisión necesaria (puntuación de calidad / indicadores).** Si la cola está vacía, verá **La cola está vacía.**

![Revisar, back office en inglés. La cola de revisión.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Columnas: **ID**, **Puntuación**, **Dominio**, **Origen**, **IA**, **Indicadores**, **Aprobar** y **Rechazar**.

Una fila llega aquí cuando el control de calidad le da una puntuación inferior a 70, cuando los marcadores o el HTML no coinciden, o cuando la traducción es mucho más larga que el origen. Si el trabajo podía publicar y la cadena pasó la validación, el catálogo ya puede contener la propuesta. **Aprobar** y **Rechazar** solo cambian esta cola. No escriben una traducción nueva ni restauran la anterior. Después de cualquiera de los dos botones aparece **Revisión actualizada.** y la fila sale de la cola.

La tabla de revisión de **Manual** es otra pantalla, y en ella está el botón **Guardar aprobados**.

### 3.7. Catálogo

Abra **Catálogo**. Sirve para traducir campos de productos, categorías o CMS. No es el mismo catálogo que **Internacional → Traducciones**. Cada pulsación procesa como máximo 100 registros.

![Catálogo, back office en inglés. Entidad, campos, idioma de origen, idioma de destino, solo vacíos y empezar tras ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Entidad** | product | Qué registros se leen: **product**, **category** o **cms**. Estas tres palabras se quedan en inglés. La página se recarga y muestra solo la lista de campos de ese tipo. Cambiar la entidad no traduce nada. Mensaje: **Mostrando campos para {entidad}. No se tradujo nada.** |
| **Campos** | todos los campos de la entidad | Los textos que envía este lote. Mantenga pulsado Ctrl o Cmd para seleccionar varios. **Título** es el nombre del producto, el nombre de la categoría o el título de la página CMS. **Contenido** es el cuerpo de la página CMS. Si quiere que los enlaces se queden como están, deje fuera **URL amigable**. Solo se traducen los campos seleccionados. |
| **Idioma de origen** | la lista de idiomas de la tienda | El idioma del que se copian los campos. El idioma de origen no se modifica. |
| **Idioma de destino** | la lista de idiomas de la tienda | El idioma que recibe la traducción. Debe ser distinto del origen. Se escriben hasta 100 registros. |
| **Solo vacíos** | Sí | Omite los campos que ya tienen texto en el idioma de destino. **No** permite sustituir ese texto cuando la publicación está permitida. |
| **Empezar tras ID** | 0 | Omite los registros hasta este ID. Déjelo en 0 para empezar por el primero. Tras cada lote, el campo muestra el último ID leído. Vuelva a pulsar el botón para seguir. |

Campos de producto: **Título**, **Descripción corta**, **Descripción**, **Meta-título**, **Meta-descripción** y **URL amigable**.

Campos de categoría: **Título**, **Descripción**, **Meta-título**, **Meta-descripción** y **URL amigable**.

Campos de CMS: **Título**, **Meta-descripción**, **Meta-palabras clave**, **Contenido** y **URL amigable**.

Pulse **Traducir lote (máx. 100)**. Al terminar, verá **Catálogo finalizado: se guardaron N, fallaron N.** Debajo del formulario también aparecen los contadores **Guardado** y **fallido**.

- **No se tradujo nada. No hay clave API de Grok. Abra Configuración y pegue la clave.**
- **No se guardó nada. Active Permitir publicación en Configuración.**
- **No se tradujo nada. El idioma de origen y el de destino deben ser distintos.**
- **No se tradujo nada. Seleccione al menos un campo.**

### 3.8. Glosario

Abra **Glosario**. La lista guarda palabras que el modelo debe conservar o escribir siempre de la misma forma. Añadir un término no reescribe las traducciones guardadas, pero la siguiente traducción sí usará la lista.

![Glosario, back office en inglés. Añadir término y el formulario CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Término de origen** | vacío | Cómo aparece la palabra en el idioma de origen. Escriba la palabra o frase exacta, con mayúsculas si importan. Obligatorio. |
| **Configuración regional de destino** | vacío | Limita la fila a una configuración regional de destino, por ejemplo es-ES. Si está vacío, la fila se aplica a todos los destinos. Una configuración rellenada se ignora en los demás idiomas. |
| **Término de destino** | vacío | La forma que debe aparecer en la traducción. Déjelo vacío solo cuando **No traducir** esté activado. |
| **No traducir** | No | **Sí** indica al modelo que copie el término de origen sin cambios. Úselo para nombres de marca, SKU y marcadores. **No** significa que el **Término de destino** es la traducción que quiere. |

Pulse **Añadir**.

- **Término de glosario añadido. Las traducciones ya guardadas no se modificaron.**
- **No se añadió nada. Escriba un término de origen.**

Las columnas de la tabla son **Origen**, **Configuración regional**, **Destino**, **No traducir** (**Sí** o **No**) y **Eliminar**. Si la tabla está vacía, verá **Aún no hay términos en el glosario.** **Eliminar** quita esa fila. Mensaje: **Término de glosario eliminado.**

**CSV del glosario**

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Archivo CSV** | vacío | El archivo necesita las columnas source_term, target_locale, target_term y do_not_translate. **Importar CSV** añade las filas que puede leer. **Exportar CSV** descarga la lista actual e ignora el campo de archivo. Exportar no cambia el glosario. |

- **Se importaron N filas.**
- **Falta el archivo CSV.** Elija un archivo y pulse **Importar CSV** de nuevo.
- **No se puede abrir el archivo CSV.** Guarde el archivo como CSV e inténtelo otra vez.

### 3.9. Exclusiones

Abra **Exclusiones**. La lista contiene cadenas de origen que el módulo debe omitir. Una cadena que coincide no se envía a Grok ni se borra de PrestaShop. Guardar un patrón no cambia las cadenas ya guardadas.

![Exclusiones, back office en inglés. Patrón, tipo y la tabla de patrones.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Patrón** | vacío | El texto que se compara con cada cadena de origen. Obligatorio. |
| **Tipo** | exact | **exact** coincide con la cadena completa, **prefix** con el principio, **contains** con un fragmento y **regex** es una expresión regular de PHP que se aplica tal como está escrita. Pruebe primero con un patrón corto. Un tipo mal elegido puede excluir demasiado o nada. |

Pulse **Añadir**.

- **Patrón de exclusión añadido. Las cadenas coincidentes se omitirán en la próxima ejecución. Ahora mismo no se tradujo nada.**
- **No se añadió nada. Escriba un patrón.**

Las columnas de la tabla son **Patrón**, **Tipo**, **Activo** y **Eliminar**. **Activo** muestra 1 cuando el patrón se está usando. Si la tabla está vacía, verá **Aún no hay patrones.** **Eliminar** quita esa fila. Mensaje: **Patrón eliminado.**

### 3.10. Historial

Abra **Historial**. Es la lista completa de llamadas a Grok, incluidas las pruebas de conexión y las llamadas bloqueadas antes de enviarse. Los gráficos y los diez prompts más recientes están en el **Panel de control**, donde **Ver todo** abre esta pestaña.

![Historial, back office en inglés. La lista de llamadas y borrar historial.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Columnas: **ID**, **Cuándo**, **Estado**, **Tipo**, **Modelo**, **Idiomas**, **Enviado**, **Recibido**, **Total**, **Tiempo**, **Prompt** y **Ver**.

**Tipo** es uno de estos: **Manual**, **Página de traducción**, **Trabajo masivo**, **Catálogo**, **Prueba de conexión**, **Traducir** o **No enviado**. **Estado** es **Éxito** o **Error**.

**Ver** abre el prompt y la **Respuesta**, además de **HTTP**, **Enviado**, **Recibido** y **Total**. **Volver a la lista** regresa a la tabla. Si la fila se ha eliminado, la página muestra **Esta fila del historial ya no existe.** Si el detalle no se puede cargar, la página muestra **No se pudo cargar esta solicitud.**

**Anterior** y **Siguiente** cambian de página. La línea muestra **Página N / N**.

**Borrar historial** pregunta **¿Borrar el historial guardado? Las traducciones guardadas se mantienen.** Al confirmar, solo se borran estas filas. Mensaje: **Historial borrado. Las traducciones guardadas no se modificaron.** Si la lista está vacía, aparece **Aún no hay solicitudes.**

Los **Días de retención de logs** en **Configuración** también eliminan las filas más antiguas que ese número cuando se guarda una llamada nueva.

### 3.11. Actualizaciones

Abra **Actualizaciones**. Esta página comprueba si hay un paquete más reciente. No traduce nada.

![Actualizaciones, back office en inglés. Comprobación manual, notificaciones automáticas y página del producto.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Comprobación manual** | el botón **Comprobar ahora** | Consulta al editor una vez. **¡El módulo está actualizado!** significa que esta instalación corresponde al paquete actual. **¡Nueva versión disponible!** significa que hay un paquete más reciente. Descárguelo desde la página del producto e instálelo desde el **Gestor de módulos**. |
| **Notificaciones automáticas** | Activadas | **Activadas** permite que el back office muestre un aviso cuando existe un paquete más reciente. **Desactivadas** apaga ese aviso. Pulse **Guardar** para conservar la elección. Desinstalar el módulo no borra esta elección. |
| **Página del producto** | un enlace con el nombre del módulo | Abre la página del módulo. La dirección aparece en el apartado 7. |

Cuando hay un paquete más reciente, el back office también puede mostrar **Nueva versión disponible, consulte http://MyPresta.eu para más información** con el enlace **Más detalles en el registro de cambios**.

### 3.12. Botones en Internacional → Traducciones

Abra **Internacional**, después **Traducciones**, y abra un catálogo. Cuando **Botones de campo individual — Internacional → Traducciones** está en **Sí**, cada campo tiene un botón **Traducir**. Un clic rellena ese campo. Para guardar la página sigue usando el botón **Guardar** de PrestaShop.

Cuando **Casillas de verificación de campo individual — Internacional → Traducciones** está en **Sí**, la página muestra además una barra **Traducciones de Grok**.

- **Origen** toma su valor de la **Configuración regional de origen** en **Configuración**. Si ese ajuste está vacío, la barra usa en-US. Puede editar el campo.
- **Destino** es el idioma del catálogo que tiene abierto.
- **Marcar todo**, **Desmarcar todo** y **Marcar vacíos** cambian las marcas.
- **Traducir vacíos** rellena los campos vacíos. **Traducir seleccionados** rellena los campos marcados.
- La ayuda dice **Rellena los campos. Guarde con el botón de PrestaShop.**
- Mientras trabaja, la barra muestra **Traduciendo…**. Al terminar, muestra **Hecho**.
- **Seleccionado** indica cuántos campos están marcados.
- **Seleccione al menos un campo.** aparece cuando pulsa **Traducir seleccionados** sin tener nada marcado.
- **Rellene primero el campo del idioma de origen.** aparece cuando el texto de origen está vacío.
- **No se encontró el archivo de correo del idioma de origen.** aparece en una pantalla de correo cuando falta el archivo de correo de origen.
- **Traducir vacíos en esta sección** rellena las cadenas vacías de la sección que está viendo.

Estos botones no sustituyen al **Guardar** de la página de PrestaShop. **Permitir publicar / guardar** no los bloquea, porque solo rellenan el formulario.

### 3.13. Botones en los formularios de producto, categoría y CMS

Abra un producto, una categoría, una página CMS u otro formulario del back office que tenga un campo por idioma. Cuando **Botones de campo individual — formularios de la tienda** está en **Sí**, cada uno de esos campos tiene un botón **Traducir**. Un clic rellena ese campo a partir del idioma de origen del mismo formulario.

![Formulario de producto, back office en inglés. La barra Traducciones de Grok bajo los campos de descripción.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

Cuando **Casillas de verificación de campo individual — formularios de la tienda** está en **Sí**, el formulario muestra además la barra **Traducciones de Grok**.

- **Origen** empieza con la **Configuración regional de origen**, o con en-US si ese ajuste está vacío.
- **Destino** enumera los demás idiomas de la tienda y **todos los demás idiomas**.
- **Marcar todo**, **Desmarcar todo**, **Marcar vacíos**, **Traducir vacíos** y **Traducir seleccionados** funcionan igual que en la página de traducciones.
- La ayuda dice **Rellena los campos. Guarde con el botón de PrestaShop.**
- **Seleccione al menos un campo.**, **Rellene primero el campo del idioma de origen.** y **El campo del idioma de origen no está en esta página.** indican qué hay que corregir.
- **El idioma de destino no pertenece a esta tienda.** significa que el destino no coincide con ningún idioma de la tienda.
- La línea sobre un campo puede decir **Traducir desde** el nombre del origen **a** el nombre del destino.

Pulse el **Guardar** de PrestaShop en ese formulario para guardar los campos rellenados. La barra no guarda el producto por sí sola.

## 4. Tienda

El tema de la tienda no muestra este módulo. El cliente no ve ningún botón de traducción, ningún formulario ni ninguna página de estado.

La única dirección que sale del back office es la **URL de CRON** de **Configuración**, que también aparece bajo la tabla de cobertura del **Panel de control**. Copie esa dirección en el programador del servidor. Cada llamada procesa una porción del primer trabajo en espera o en curso y luego termina. Abrir **Configuración** no la llama.

| Lo que ve | Qué hacer |
|---|---|
| Una línea JSON con el resultado de la porción | La porción se ejecutó. Abra **Trabajos** y lea las filas. |
| **No pending jobs** | No hay ningún trabajo en espera. Cree uno en **Masivo (Bulk)**, o el anterior ya ha terminado, está en pausa o se canceló. Este texto se queda en inglés. |
| **Forbidden** | La dirección es incorrecta, o el token se regeneró al reinstalar. Copie de nuevo la **URL de CRON**. No publique la dirección. Este texto se queda en inglés. |

No añada parámetros propios. La dirección que copia es exactamente la que lee el módulo.

## 5. Problemas

**No hay clave API de Grok.** y **Abrir configuración** aparecen en todas las pestañas. Pegue la clave en **Configuración**, pulse **Probar conexión** y después **Guardar**.

**La tienda necesita al menos dos idiomas.** Añada un idioma en **Internacional → Localización → Idiomas** y vuelva a abrir el módulo.

**No se pudo establecer la conexión. No se tradujo nada.** El motivo aparece justo después de esta frase. Revise la clave, el modelo y si el servidor puede llegar a la dirección de Grok. Abra **Historial** y pulse **Ver** en la fila con el error.

**Monthly API budget has been exhausted.** Este mensaje se queda en inglés. Suba el **Presupuesto USD / mes** o déjelo en 0 si no quiere tope, y pulse **Guardar**. El texto ya guardado se mantiene.

**Grok rate limit (429). Try again later.** Este mensaje se queda en inglés. Espere y vuelva a lanzar la porción. Si el trabajo muestra **Rate limit — job auto-paused. Resume later.**, pulse **Reanudar** y luego **Procesar porción**. Si se repite, reduzca el **Tamaño de lote (Batch size)** o alargue la pausa entre llamadas del cron. **Límite de tasa / min** es el tope de esta tienda, y Grok puede rechazar la llamada de todos modos.

**No se guardó nada. Active Permitir publicación en Configuración.** Ponga **Permitir publicar / guardar** en **Sí**, pulse **Guardar** y vuelva a guardar. Los iconos de los formularios siguen rellenando solo el formulario.

**No se guardó por marcadores o HTML dañados: N.** La propuesta cambió un marcador o una etiqueta. Ajuste la propuesta para que coincida con el origen, o deje esa fila sin marcar y pulse **Guardar aprobados** otra vez.

**No se tradujo nada. Elija un tema y después pulse Filtrar.** o **Elija un módulo.** La sección necesita esa elección antes de poder cargar la lista.

**Ninguna cadena coincide con este filtro. No se envió nada a Grok.** Desactive **Solo vacíos**, vacíe **Buscar** o elija otro dominio.

**Falta el archivo CSV.** o **No se puede abrir el archivo CSV.** Elija un CSV con las cuatro columnas y pulse **Importar CSV** de nuevo.

**No se encontró el archivo de correo del idioma de origen.** En **Internacional → Traducciones**, abra la sección de correo de un idioma que ya tenga el archivo, o genere antes las traducciones de correo en PrestaShop.

**Esta fila del historial ya no existe.** La fila se borró o la eliminaron los **Días de retención de logs**. La traducción que se guardó sigue en la tienda.

Falta la entrada del menú, o el back office indica que no se encontró el controlador. Abra el **Gestor de módulos**, busque **AI Translations with Grok** y pulse **Configurar**. Así se vuelve a crear la entrada del menú **Internacional**. Si el módulo ya no aparece en la lista, instale el ZIP otra vez.

La instalación se detiene en **No se pudieron crear las tablas del módulo.** El usuario de la base de datos no puede crear tablas. Corrija los permisos de la base de datos y pulse **Instalar** de nuevo. **No se pudo añadir la pestaña del menú.** significa que no se pudo crear la entrada del menú. Después de una instalación correcta, pulse **Configurar** o vuelva a instalar.

## 6. Para desarrolladores

### 6.1. Visión general

Nombre técnico `myaitranslationsgrok`, versión `1.2.0`, autor MyPresta.eu, pestaña del módulo `administration`. El nombre en la lista de módulos y la etiqueta del menú **Internacional** son **AI Translations with Grok**. La clase es `myaitranslationsgrok`. El mínimo de `ps_versions_compliancy` es `1.7.0.0`.

`getContent()` llama a `ensureTab()` y redirige a `AdminMyaitranslationsgrok`. La configuración la lee `MyaitgkConfigService` (claves `MYAITGK_*`). La clave API está cifrada en `MYAITGK_API_KEY_ENC`. Las llamadas de traducción pasan por `MyaitgkTranslateService` hasta `MyaitgkGrokTranslationProvider`, que envía un JSON por POST a `https://api.x.ai/v1/chat/completions`. Las escrituras del catálogo pasan por `MyaitgkTranslationAdapter`. Las escrituras de productos, categorías y CMS pasan por `MyaitgkCatalogTranslateService`. Al guardar una traducción de catálogo, el módulo llama a `Tools::clearCache()`.

El módulo no define `enable()` ni `disable()`. Desactivarlo en el **Gestor de módulos** no ejecuta ninguna limpieza adicional. Lo que elimina la pestaña del menú, las tablas y las claves `MYAITGK_*` es la desinstalación.

### 6.2. Archivos

- `myaitranslationsgrok.php` - instalación, desinstalación, hooks, pestaña y configuración de los botones de campo.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - cada pestaña del back office y las acciones AJAX.
- `controllers/front/cron.php` - procesa una porción del trabajo para la dirección cron.
- `lib/updateChecker.php` - la pestaña **Actualizaciones** y la comprobación de versión.
- `sql/install.php`, `sql/uninstall.php` - crean y borran las tablas.
- `src/Admin/MyaitgkForms.php` - campos de HelperForm y textos `desc`.
- `src/Admin/MyaitgkSectionHelp.php` - el panel **Ayuda**.
- `src/Service/MyaitgkConfigService.php` - claves, lista de modelos y token del cron.
- `src/Service/MyaitgkTranslateService.php` - presupuesto, límite, glosario, exclusiones y guardado.
- `src/Service/MyaitgkBulkJobFactory.php` - crea un trabajo desde **Masivo (Bulk)**.
- `src/Service/MyaitgkCatalogTranslateService.php` - lotes de productos, categorías y CMS.
- `src/Service/MyaitgkDashboardService.php` - recuentos de cobertura.
- `src/Service/MyaitgkRateLimiter.php` - límite por minuto guardado en `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - la petición a xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - prompts de sistema y de usuario.
- `src/Job/MyaitgkJobWorker.php` - porción, reintento y correo al terminar.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - filas de trabajo y constantes de estado.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - comprobaciones antes de guardar.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - glosario y exclusiones.
- `src/Audit/MyaitgkRequestLogRepository.php` - **Historial** y el informe del panel.
- `src/Audit/MyaitgkSnapshotService.php` - copias para revertir.
- `src/Security/MyaitgkApiKeyEncryptor.php` - cifrado OpenSSL de la clave.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - catálogos de PrestaShop y módulos clásicos `translations/{iso}.php`.
- `views/templates/admin/configure.tpl` y `views/templates/admin/_partials/*.tpl` - las pestañas.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - textos del back office.

### 6.3. Controladores

`AdminMyaitranslationsgrok` extiende `ModuleAdminController`. La clase padre de la pestaña es `AdminInternational` (alternativa: `IMPROVE`). El parámetro de la consulta es `myaitgk_tab` y admite los valores `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings` y `updates`. Los valores desconocidos vuelven a `dashboard`.

Las acciones visibles son los botones de envío del capítulo 3. Otros puntos de entrada de administración que usan los scripts de la página: `ajax=1&action=HistoryDetail` para **Ver**, la consulta del estado del trabajo para **Procesamiento automático**, y las acciones de traducción de campos de `translations-tool.js` y `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) lee el parámetro `token`. Si falta o es incorrecto, responde con HTTP 403 y `{"ok":false,"error":"Forbidden"}`. Un token correcto sin `id_job` procesa una porción del primer trabajo en estado `pending` o `running`. Con `id_job`, procesa ese trabajo concreto. Si no hay nada en espera, el cuerpo es `{"ok":true,"message":"No pending jobs"}`.

`job_action` en la pestaña de trabajos acepta `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` y `export_errors`. La plantilla muestra todas las acciones excepto `cancel`.

### 6.4. Hooks

Registrados en `install()`:

- `displayBackOfficeHeader` - corrige la etiqueta técnica de la pestaña y carga los recursos del back office.
- `actionAdminControllerSetMedia` - carga los mismos recursos.

En `AdminMyaitranslationsgrok`, el módulo añade `views/css/admin.css`, `views/js/admin.js` y `views/js/admin-help.js`. El **Panel de control** añade además `chart.min.js` y `history-charts.js`. En **Internacional → Traducciones** añade `translations-tool.js` cuando los interruptores de esa página están activados. En los demás formularios del back office añade `entity-fields.js` cuando están activados los interruptores de los formularios de la tienda. Ambos pasan `myaitgkTr` a JavaScript.

El módulo no registra ningún hook de tienda y no expone un hook propio.

### 6.5. Overrides

El módulo no sobrescribe ninguna clase ni controlador de PrestaShop.

### 6.6. Base de datos

La desinstalación ejecuta `sql/uninstall.php` y borra todas las tablas de la lista siguiente. La instalación usa `CREATE TABLE IF NOT EXISTS`, así que una tabla que haya quedado de algún modo se conserva.

| Tabla | Contenido |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | Un trabajo masivo: configuraciones regionales, `scope_json`, `policy_json`, `dry_run`, contadores, coste, estado y empleado. |
| `myaitgk_job_item` | Una cadena de un trabajo: dominio, clave, tema, configuraciones regionales, origen, texto anterior, texto nuevo, estado y avisos. |
| `myaitgk_memory` | Traducción reutilizada, identificada por `memory_hash`, modelo y `hit_count`. |
| `myaitgk_usage_ledger` | Filas diarias de tokens y coste, de las que se calcula **Presupuesto USD / mes**. |
| `myaitgk_snapshot` | Texto anterior a una escritura del trabajo, usado por **Revertir**. |
| `myaitgk_api_log` | Contexto breve del error. La clave API se elimina antes de guardar. |
| `myaitgk_request` | Las filas de **Historial**: prompt, respuesta, tokens, modelo, estado y duración. El repositorio vuelve a crear la tabla si falta. |
| `myaitgk_review` | Filas de la cola con `needs_review`, `approved` o `rejected`, además de `quality_score` y `flags_json`. |
| `myaitgk_catalog_item` | Filas de los lotes de catálogo: entidad, campo, idiomas, origen, texto anterior, texto nuevo y estado. |

`var/rate_limit.json` es un archivo, no una tabla. La desinstalación no borra `mypresta_updates`, `update_myaitranslationsgrok` ni `updatev_myaitranslationsgrok`.

### 6.7. Claves y traducciones

El prefijo es `MYAITGK_`. `installDefaults()` escribe una clave solo cuando falta. Valores que se usan si la clave no existe:

| Clave | Valor si falta |
|---|---|
| `API_KEY_ENC` | vacío |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | vacío |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | vacío |
| `BATCH_SIZE` | `25` (se guarda entre 1 y 100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | vacío |
| `TEMPERATURE` | `0.2` (se guarda entre 0 y 1) |
| `DRY_RUN_SAMPLE` | `10` (se guarda entre 1 y 50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (se guarda como mínimo 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | vacío |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (con 0 se omite del cuerpo de la traducción; con un valor mayor que 0 se envía como `max_tokens`) |
| `CRON_TOKEN` | 32 caracteres hexadecimales, se regenera si está vacío |

Al guardar **Configuración**, `PROVIDER` se fuerza a `grok` y se borran `MYAITGK_DEEPL_API_KEY` y `MYAITGK_CLAUDE_API_KEY` si siguen existiendo de versiones anteriores. Un campo de clave API vacío no borra `API_KEY_ENC`.

Los identificadores de modelo integrados son `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` y `grok-4.20-0309-reasoning`. Un interruptor que no existe se considera activado, por lo que las tiendas instaladas antes de esos interruptores conservan los iconos.

Las descripciones de los campos las genera `MyaitgkForms::help()` con los epígrafes **Qué hace:**, **Cómo configurar:** y **Efecto:**. Los paneles de ayuda son `MyaitgkSectionHelp`. Los textos del back office pasan por `$this->l()`. Para añadir un idioma, copie `translations/en.php` a `translations/{iso}.php`. Algunos mensajes están escritos en inglés directamente en el PHP y se mostrarán así: `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.` y los mensajes JSON del cron.

### 6.8. Ampliar

El tema de la tienda no tiene plantilla que sobrescribir. El módulo no renderiza ningún archivo Smarty de la tienda. El marcado del back office está en `views/templates/admin/`. Los botones de campo los inyectan `views/js/translations-tool.js` y `views/js/entity-fields.js`. No hay ningún hook de tienda al que engancharse.

## 7. Ayuda

Página del módulo: [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

Para escribir sobre este módulo, inicie sesión en su cuenta de cliente de mypresta.eu, abra el formulario de contacto y elija el tema **Support for paid modules**. El formulario indica que para los módulos de pago es necesario iniciar sesión. Una vez dentro, elija este módulo de su historial de compras.
