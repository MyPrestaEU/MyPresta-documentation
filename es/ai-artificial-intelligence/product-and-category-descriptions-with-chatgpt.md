---
title: "My ChatGPT - generación de contenido con IA - documentación y manual del usuario"
description: "Utilice este manual para configurar OpenAI, generar los textos del catálogo con el módulo que ya tiene y resolver los problemas cuando una generación falla."
sidebar:
  label: "My ChatGPT - generación de contenido con IA - documentación y manual del usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product and Category Descriptions with ChatGPT en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Requisitos

Compruebe estos puntos antes de conectar el módulo con OpenAI.

- Utilice PrestaShop 1.6, 1.7, 8 o 9 (hasta 9.99.99).
- Utilice PHP 7.0 o superior. El instalador se detiene en una versión de PHP más antigua.
- Active las extensiones de PHP cURL y JSON. Cada llamada a OpenAI y la comprobación de actualizaciones usan cURL. Active también mbstring, porque la limpieza de texto de la búsqueda de imágenes y de la pantalla de nuevo producto la utiliza.
- Use el campo opcional **URL de origen opcional** en **Nuevo producto** solo cuando PHP pueda leer páginas web (el ajuste `allow_url_fopen`) y la extensión DOM esté disponible. Sin ellos, el campo se ignora y solo se usa su brief.
- Tenga su propia cuenta de OpenAI y una clave API de platform.openai.com. La clave debe poder llamar al modelo que elija. Usted paga a OpenAI cada solicitud. El módulo no incluye crédito.
- Permita que el servidor llegue a internet por el puerto 443. La tienda contacta con OpenAI en cada generación y con el servidor de actualizaciones de MyPresta.eu para comprobar las actualizaciones.
- Añada una tarea programada (CRON) en el servidor solo si quiere que la generación se ejecute sin que nadie haga clic. Las direcciones cron no hacen nada hasta que el servidor las llama.
- No se necesita ningún otro módulo de PrestaShop.
- Reserve tiempo para catálogos grandes. Cada campo de cada idioma es una solicitud independiente a OpenAI. Una ejecución masiva con 500 productos, cuatro campos y dos idiomas envía 4000 solicitudes, una tras otra, y mantiene ocupada la pestaña del navegador. Empiece con lotes de prueba pequeños o use lotes de cron para catálogos grandes.

## 2. Instalación

1. Abra **Módulos**, luego **Administrador de módulos**.
2. Haga clic en **Subir un módulo** y suba el archivo ZIP.
3. Haga clic en **Instalar** en **Mi ChatGPT - Generación de contenido con IA**.
4. Abra **Módulos** en el menú de la izquierda. Allí aparece una nueva entrada **Generador de Contenido con IA**. Haga clic en ella para abrir el **Panel de control** del módulo. **Configurar** en el **Administrador de módulos** abre el mismo lugar.

La instalación hace lo siguiente:

- Añade la entrada de menú **Generador de Contenido con IA** en **Módulos**. Las demás pantallas del módulo se alcanzan desde el menú superior propio del módulo y no tienen entradas de menú separadas.
- Crea dos tablas: una para las plantillas de prompt y otra para el historial de cada generación.
- Añade 16 plantillas de prompt ya preparadas (nombres de producto, descripciones, meta títulos, meta descripciones y etiquetas). Todas están activadas.
- Crea valores secretos largos para las llamadas internas del módulo y para las dos direcciones cron.
- Desactiva el filtro HTML de toda la tienda (HTMLPurifier). Las descripciones y los textos de categoría conservan entonces sus etiquetas HTML, pero el mismo interruptor queda desactivado para cualquier otro texto de la tienda. Vuelva a activarlo en los ajustes de la tienda si no lo desea.
- No borra la caché de PrestaShop. Bórrela en **Parámetros avanzados**, luego **Rendimiento**, solo si siguen viéndose estilos antiguos o una pantalla antigua.

Si el instalador muestra «Este módulo requiere PHP 7.0.0 o superior», actualice primero PHP. Si muestra «No se pudieron crear las tablas de la base de datos del módulo.», compruebe que el usuario de la base de datos puede crear tablas y vuelva a instalar.

Desinstalación:

- Elimina las entradas de menú, ambas tablas (se pierden todas las plantillas de prompt y todo el **Historial**) y casi todos los ajustes del módulo, incluidos la clave API y los secretos de cron.
- No vuelve a activar el filtro HTML. Actívelo usted mismo si lo desea.
- No borra ningún texto de producto, texto de categoría ni foto de producto que haya creado el módulo. Permanecen en el catálogo.
- Deja unos pocos restos inofensivos en la configuración de la tienda (la elección de categorías de cron guardada, los últimos valores de filtro de **Generar** y los valores de la comprobación de actualizaciones).
- Una nueva instalación crea nuevos secretos, un Historial vacío y de nuevo las 16 plantillas predeterminadas. Las direcciones cron antiguas dejan de funcionar, así que cópielas de nuevo.

## 3. Configuración y trabajo en el back office

Abra **Módulos**, luego **Generador de Contenido con IA**. El menú superior del módulo tiene estas entradas: **Panel de control**, **Configuración**, **Generar**, **Nuevo producto**, **Cron**, **Historial**, **Imágenes** y, a la derecha, **Actualizaciones**. Un botón redondo **Ayuda** en la parte inferior de cada pantalla del módulo abre una breve explicación de la pantalla en la que se encuentra.

Las capturas de pantalla de este manual proceden del back office en inglés. Los nombres de botones, campos y pestañas se dan en este manual en español. En la descripción de cada captura aparece entre paréntesis el texto en inglés de la pantalla.

Siga este proceso:

1. Abra **Configuración**, luego **ChatGPT**. Pegue la clave API de OpenAI y elija un modelo. Haga clic en **Guardar**.
2. Opcionalmente, abra **Estudio** y establezca voz de marca, audiencia, tono, glosario, palabras prohibidas, presupuesto mensual y la puerta de calidad.
3. Abra **Plantillas de prompt**. Revise las 16 plantillas, edítelas o añada las suyas y deje activadas solo las que su equipo deba usar.
4. Genere texto del modo que mejor se adapte a la tarea:
   - Un producto: abra el producto, la pestaña **Módulos**, y use **Generar**, **Simular** o **Fotos**. También funcionan los pequeños botones **Generar con IA** junto a los campos de descripción y meta.
   - Muchos productos o categorías a la vez: abra **Generar**, construya una lista con filtros y pulse **Ejecutar**.
   - Un producto nuevo a partir de un brief corto: abra **Nuevo producto**.
   - Lotes programados sin hacer clic: abra **Cron** y añada la dirección al programador del servidor.
5. Revise el **Historial** para ver cada prompt, respuesta, error y número de tokens. Revise el **Panel de control** para ver totales y gráficos.

El módulo no tiene estados al estilo de los pedidos. Una plantilla de prompt está **Activado** o **Desactivado**. Cada llamada del **Historial** es **Éxito** o **Error**. Una ejecución masiva o de cron termina cuando se ha escrito el último elemento, y el texto se guarda en el producto o la categoría en cuanto llega cada respuesta.

Si **CTA de la barra superior de administración** está activado, un pequeño botón de varita mágica **Mi ChatGPT** aparece en la barra superior de cada página del back office. Abre un pequeño cuadro con una lista de plantillas, un campo de texto y **Generar**. Funciona como la **Zona de pruebas** (sección 3.6): la respuesta se muestra en el cuadro y no se guarda nada en el catálogo.

En la lista de productos de **Catálogo**, **Productos**, el módulo añade también un botón **Mi ChatGPT** que abre **Generar**.

### 3.1 Panel de control

Abra **Generador de Contenido con IA**, **Panel de control**. Esta página es un informe. Nunca escribe textos de producto ni de categoría.

![Panel de control (Dashboard)](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Haga clic en un botón de periodo: **Hoy**, **7 días**, **30 días** (abierto por defecto), **90 días**, **Este mes** o **Todo el tiempo**. O escriba **Desde** y **Hasta** y haga clic en **Aplicar**.
- La línea **Servicio activo** muestra ChatGPT y el modelo guardado en **Configuración**, **ChatGPT**.
- Lea las tarjetas **Solicitudes**, **Éxito**, **Errores**, **Tokens enviados** y **Tokens recibidos** del periodo elegido. **Solicitudes** cuenta cada llamada almacenada en el **Historial**. **Errores** cuenta las fallidas. Los tokens enviados son el tamaño de su instrucción; los tokens recibidos, el tamaño de la respuesta.
- Lea los gráficos **Solicitudes y errores**, **Tokens enviados y recibidos** y **Solicitudes por modelo**.
- Los gráficos vacíos significan que no se generó nada en ese periodo. Cambiar las fechas solo vuelve a dibujar la página. No se borra nada.

### 3.2 Configuración – General

Abra **Configuración**, luego **General**. Haga clic en **Guardar** después de cambiar algo. Verá «Configuración actualizada».

![Configuración general (General settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Modo en vivo** | No | Marca el módulo como en funcionamiento en la tienda real y no en una configuración de prueba. Actívelo en producción. Desactivado mantiene las mismas herramientas pero señala que no es la configuración de producción. |
| **Modo de depuración** | No | Escribe detalles técnicos adicionales cuando falla una llamada a OpenAI. Actívelo solo mientras investiga un problema. Los detalles aparecen en **Parámetros avanzados**, **Registros**. Los clientes nunca los ven. |
| **Tiempo de espera de la API (segundos)** | 120 | Cuánto puede tardar una llamada a OpenAI antes de que el módulo se rinda. 120 sirve para descripciones normales. Súbalo hasta 600 para textos largos o modelos lentos. Los valores inferiores a 10 se suben a 10, los superiores a 600 se bajan a 600, y un valor vacío o no numérico pasa a 120. Un tiempo de espera corto falla rápido y escribe un error en el Historial. |
| **Historial de edición de productos** | Sí | Añade en la página del producto una lista **Historial** con un botón **Restaurar**, para que los editores puedan recuperar un texto anterior. Desactivado oculta esa lista. Las filas permanecen en el **Historial** en cualquier caso. |
| **CTA de la barra superior de administración** | Sí | Añade el botón de acceso directo **Mi ChatGPT** a la barra superior del back office en todas las páginas. Desactivado elimina solo ese botón. La entrada de menú **Generador de Contenido con IA** permanece. |
| **Formulario de la página de edición de producto** | Sí | Muestra el panel del generador (**Generar**, **Simular**, **Fotos**) en la pestaña **Módulos** del producto y los botones **Generar con IA** junto a los campos de descripción y meta. Desactivado los oculta. Use No cuando solo deban usarse la generación masiva y el cron. |
| **Buscador de imágenes con IA** | Sí | Permite a un editor pedir al modelo páginas web que probablemente muestren fotos del producto actual. Activado muestra la pestaña **Fotos** en el producto. Desactivado la oculta. No se descarga nada hasta que alguien confirma las fotos. El mismo interruptor está en **Imágenes** (sección 3.12). |
| **Prompt de búsqueda de imágenes con IA** | Texto largo predeterminado | La instrucción que se envía cuando alguien busca fotos. Por defecto pide exactamente cinco direcciones de página como lista simple, con preferencia por páginas de fabricantes, grandes distribuidores y catálogos. Las palabras `{product_name}` y `{product_description}` se sustituyen por el producto actual. Mantenga la petición de una lista simple de direcciones. Un prompt preciso devuelve páginas relevantes. Un prompt vago devuelve enlaces sin relación. El mismo texto está en **Imágenes**. |

### 3.3 Configuración – ChatGPT

Abra **Configuración**, luego **ChatGPT**. El formulario se titula **Configuración de OpenAI**. Cada generación, incluidos los botones del producto, las ejecuciones masivas y el cron, usa estos valores. Haga clic en **Guardar**. Verá «Configuración de OpenAI actualizada».

![Configuración de ChatGPT (ChatGPT settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **CLAVE API de OpenAI** | Vacío | El secreto que permite a esta tienda llamar a su cuenta de OpenAI. Pegue la clave creada en platform.openai.com en su cuenta de OpenAI. Los espacios alrededor se eliminan al guardar. Deje el cuadro sin tocar para conservar la clave ya almacenada. Una clave vacía o incorrecta hace que toda generación falle, y el error se escribe en el Historial. Si guarda una clave nueva de menos de 10 caracteres mientras no hay ninguna clave almacenada, verá «¡El campo CLAVE API de OpenAI no es válido!». |
| **Modelo** | gpt-3.5-turbo | El modelo de ChatGPT que escribe el texto. La lista contiene los modelos integrados (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini y otros) y los modelos que usted añadió. Elija uno y haga clic en **Guardar**. Un modelo que su clave no puede usar devuelve un error de OpenAI en lugar de texto. Un modelo vacío da «¡El campo Modelo de OpenAI no es válido!». |
| **Añadir un modelo de ChatGPT** | Vacío | Añade un nombre de modelo que no está en la lista integrada. Escriba el nombre exacto de su cuenta de OpenAI (por ejemplo `gpt-4.1`) y haga clic en **Añadir modelo**. El nombre aparece en **Modelo** y se convierte en el modelo activo. **Eliminar** junto a un nombre añadido lo borra. Los nombres integrados no se pueden eliminar. Si elimina el modelo añadido que está activo, el módulo cambia a gpt-4o. Mensajes: «Modelo añadido.», «Ese modelo ya está incorporado.», «Modelo eliminado.», «Los modelos incorporados no se pueden eliminar.», «Introduzca un ID de modelo como gpt-4.1.». |
| **Máximo de tokens** | 3200 | El límite superior de la longitud de una respuesta, contado en tokens, no en palabras. Use alrededor de 256 para una meta descripción y 1000 o más para una descripción HTML completa. Demasiado bajo corta la respuesta. Demasiado alto permite texto largo y encarece su factura de OpenAI. Un valor de 0 se trata como vacío y se sustituye por 256. |
| **Temperatura** | 0.7 | Con qué libertad elige palabras el modelo. Manténgase entre 0 y 1. Use alrededor de 0.2 para especificaciones y texto meta, y alrededor de 0.7 para descripciones. Cambie este valor o **Top P**, no ambos. Los valores bajos repiten una estructura parecida. Los altos varían más y pueden desviarse del brief. Un valor de 0 se trata como vacío y se sustituye por 0.7. |
| **Top P** | 1 | Otra forma de limitar lo sorprendente que puede ser la siguiente palabra. 1 considera todo el rango. Deje 1 si ya ha fijado la **Temperatura**. Un valor más bajo, como 0.9, da un vocabulario más ajustado. Un valor de 0 se sustituye por 1. |
| **Valor de penalización de frecuencia** | 0 | Reduce las frases que se repiten dentro de una misma respuesta. Use 0 salvo que las descripciones copien una y otra vez la misma frase; entonces pruebe 0.3–0.6. Rango permitido de -2 a 2. No compara productos entre sí. |
| **Valor de penalización de presencia** | 0 | Empuja la respuesta hacia temas nuevos. Use 0 por defecto. Pruebe un número positivo pequeño si cada párrafo dice lo mismo. Rango permitido de -2 a 2. Algunos modelos más recientes ignoran este campo. |

El módulo aprende por sí solo qué ajustes rechaza un modelo (algunos modelos de razonamiento rechazan la temperatura o las penalizaciones) y deja de enviárselos.

### 3.4 Configuración – Estudio

Abra **Configuración**, luego **Estudio**. El estudio añade reglas de la casa a cada prompt: botones del producto, ejecuciones masivas, cron y la zona de pruebas. Los cuadros vacíos se omiten. Haga clic en **Guardar estudio**. Verá «Configuración del estudio guardada.». El texto que ya está en el catálogo no se reescribe.

![Configuración del Estudio (Studio settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Voz de la marca** | Vacío | Indica al modelo quién habla, para que el texto encaje con su tienda y no con un asistente genérico. Escriba un brief corto, por ejemplo «taller especializado, frases cortas, sin exageraciones». Cada generación posterior parte de esta voz. |
| **Audiencia** | Vacío | Nombra al lector para el que escribir, por ejemplo «instaladores profesionales» o «compradores primerizos». Las respuestas usan vocabulario y ejemplos dirigidos a ese lector. |
| **Tono** | Vacío | El carácter de la redacción: formal, cercano, técnico. Una o dos palabras bastan. No cambia el modelo ni la temperatura. |
| **Glosario** | Vacío | Nombres de marca, materiales y grafías que el modelo debe copiar exactamente. Ponga un término por línea. El texto nuevo prefiere esas grafías. Los términos que no figuran pueden seguir reformulándose. |
| **Palabras prohibidas** | Vacío | Palabras y frases que no deben aparecer en una respuesta guardada. Una por línea. La lista solo funciona cuando la **Puerta de calidad** está activada. Una respuesta que contenga una de las líneas (también dentro de una palabra más larga) se rechaza, no se escribe en el producto y se guarda en el Historial como error. |
| **Presupuesto de generación mensual** | 0 | El máximo de generaciones correctas que la tienda puede ejecutar en el mes natural en curso. Introduzca un número entero. 0 significa sin límite. El contador vuelve a empezar el primer día del mes. Al alcanzar el tope, las generaciones nuevas se detienen con un mensaje de presupuesto. Las llamadas fallidas no se cuentan. La zona de pruebas, los botones del producto, las ejecuciones masivas y el cron cuentan todos. |
| **Puerta de calidad** | Sí | Comprueba cada respuesta contra las **Palabras prohibidas** antes de guardar nada. Activada bloquea una respuesta coincidente. Desactivada guarda la respuesta aunque contenga una palabra de la lista. |

### 3.5 Configuración – Plantillas de prompt

Abra **Configuración**, luego **Plantillas de prompt**. Una plantilla es una instrucción guardada que los editores eligen por su título en lugar de escribir el mismo brief una y otra vez. El título es solo una etiqueta para el desplegable. El modelo recibe el texto del prompt. Las plantillas activadas aparecen en el panel del producto, en el generador masivo y en el formulario de cron. Las desactivadas permanecen en la lista pero no se ofrecen (el formulario de cron todavía las lista, así que elija una activada).

![Plantillas de prompt (Prompt templates)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

La lista **Plantillas de prompt** muestra **ID**, **Título**, **Prompt**, **Estado** y **Marca de tiempo**, las más recientes primero, 50 por página.

- Haga clic en el botón verde **+** para crear una plantilla.
- Haga clic en la marca de estado de una fila para alternar una plantilla entre activada y desactivada.
- Use **Editar** o **Eliminar** en una fila. Marque varias filas y use la acción masiva **Eliminar** (debe confirmar «¿Estás seguro de que quieres eliminar los prompts seleccionados?»).

El formulario **Generar plantilla de prompt**:

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Estado** | Desactivado en una plantilla nueva | Muestra u oculta esta plantilla en los desplegables de la página del producto, de la generación masiva y del cron. Active las plantillas que deba usar su personal. Desactive un borrador en lugar de eliminarlo. |
| **Título del prompt** | Vacío (obligatorio) | El nombre que los editores ven en el desplegable, por ejemplo «Descripción HTML con características». No se envía al modelo. |
| **Contenido del prompt** | Vacío (obligatorio) | La instrucción que se envía al modelo. Escríbala como si diera un brief a un redactor: longitud, HTML, idioma. Los marcadores de posición se rellenan con los datos del elemento que se escribe. Las comillas dobles se cambian por comillas simples al guardar. |

Haga clic en **Guardar prompt**. Verá «¡Plantilla de prompt añadida con éxito!» o «¡Plantilla de prompt actualizada con éxito!». **Volver a la configuración del módulo** vuelve a la lista. Al eliminar verá «Plantilla de prompt eliminada.».

Marcadores de posición que puede usar en una plantilla:

| Para | Marcadores | Se sustituyen por |
|---|---|---|
| Productos | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | El valor de ese producto en el idioma que se escribe. |
| Productos | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Los datos de marca y categoría del producto. |
| Productos | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Atributos separados por comas, nombres de características, pares nombre:valor de características y direcciones de fotos del producto. |
| Categorías | `{category_name}`, `{category_description}`, `{category_parent_name}` | La categoría y su categoría padre. |
| Productos y categorías | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Los datos de su tienda. |

Las 16 plantillas predeterminadas son **Nombre del producto 1–2**, **Descripción del producto 1–7**, **Meta título del producto 1–3**, **Meta descripción del producto 1–3** y **Etiquetas del producto**. Algunas contienen redacción de ejemplo (por ejemplo, un smartwatch). Revíselas antes de la primera ejecución masiva.

### 3.6 Configuración – Zona de pruebas

Abra **Configuración**, luego **Zona de pruebas**. La zona de pruebas es un borrador que llama al modelo activo y muestra la respuesta en la página. Úsela para probar un prompt antes de guardarlo como plantilla, o para comprobar que su clave API funciona.

![Zona de pruebas (Playground)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Escriba una instrucción en el cuadro. La indicación gris dice «Pregunte al modelo cualquier cosa sobre su catálogo».
2. Haga clic en **Generar**.
3. Lea la respuesta y el número de tokens debajo del botón.

La llamada usa el modelo, los valores de muestreo y las reglas del Estudio que haya guardado. La respuesta se almacena en el Historial. No se modifica ningún producto, categoría ni campo meta. Escriba nombres y detalles reales: los marcadores de posición entre llaves no se rellenan en la zona de pruebas.

### 3.7 Generar – Productos

Abra **Generar**, luego la subpestaña **Productos**. Trabaje en dos pasos. El paso 1 solo construye una lista. No se envía nada a OpenAI y no se guarda nada como ajuste de la tienda.

![Generar productos (Generate products)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Paso 1 – el formulario **Filtrar productos para actualizar**. Todos los filtros se combinan. Un filtro que deja vacío se ignora.

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Categorías de producto** | Nada marcado | Conserva los productos de las categorías marcadas (incluidos los productos cuya categoría predeterminada es una de ellas). Un árbol vacío desactiva este filtro. |
| **Marca** | Seleccionar marca | Conserva los productos de un fabricante. La opción vacía incluye todas las marcas. |
| **Estado del producto** | Activo | **Activo** conserva los productos a la venta, **Desactivado** conserva los borradores, **Ambos** conserva todos. |
| **Stock del producto** | Todos los productos | **Solo productos en stock** elimina los productos sin cantidad disponible. **Todos los productos** ignora el stock. |
| **Actualizar solo** | Actualizar todo | **Productos que aún no se han actualizado con contenido de OpenAI** sirve para una primera pasada (productos sin fila en el Historial). **Productos que ya se han actualizado con contenido de OpenAI** sirve para reescribir. **Actualizar todo** ignora el Historial. |
| **ID de productos** | Vacío | Solo estos números de producto, separados por comas, por ejemplo 12,45,103. |
| **Referencia del producto** | Vacío | Solo los productos con estos códigos de referencia, separados por comas. |
| **Fecha de alta del producto desde** | Vacío | Omite los productos creados antes de esta fecha y hora. |
| **Fecha de alta del producto hasta** | Vacío | Omite los productos creados después de esta fecha y hora. |
| **ID mínimo de producto** | Vacío | Omite los productos con un número menor. |
| **ID máximo de producto** | Vacío | Omite los productos con un número mayor. |
| **Límite de productos** | Vacío | El máximo de productos cargados en la lista, por ejemplo 20. La lista nunca muestra más, de modo que una ejecución no recorra por accidente todo el catálogo. |

Haga clic en **Ir al siguiente paso**. **Configuración del módulo** abre la configuración del módulo.

Paso 2 – el panel **Generación masiva de productos** y la tabla de productos (**ID**, **Referencia**, **Resultado**):

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Plantilla** | Elegir una plantilla | Rellena el cuadro del prompt a partir de una plantilla activada. También puede escribir su propio prompt. El título no se envía. Si el cuadro queda vacío, el módulo usa un brief estándar para cada campo. |
| Cuadro del prompt | Vacío | La instrucción para cada producto de la tabla. Si escribe un texto, se usa el mismo texto para cada campo elegido, así que ejecute un campo cada vez cuando los campos necesiten redacciones distintas. |
| **Qué generar** | Descripciones | **Descripciones** escribe la descripción larga y la corta. **Meta título y meta descripción** escribe ambos campos meta. **Descripciones y meta juntos** escribe los cuatro. Cada campo es una solicitud independiente. Los nombres y las etiquetas se escriben desde la página del producto, no desde aquí. |
| **Texto existente** | Reemplazar | **Reemplazar** sobrescribe. **Omitir si está lleno** deja en paz un campo con contenido y no llama al modelo para él. **Añadir arriba** y **Añadir abajo** conservan el texto antiguo y añaden el nuevo. |
| **Idiomas** | Su idioma actual marcado | Marque cada idioma que desee escribir. Cada idioma marcado se genera por separado. Los idiomas sin marcar conservan su texto. |

Haga clic en **Ejecutar en la lista siguiente**. La línea de estado muestra el progreso, por ejemplo «3 / 40 – description». Cada fila muestra sus propios resultados en cuanto ese producto termina, por ejemplo «description: success Content successfully generated and updated to product.», «description_short: skipped Product skipped.» o «meta_title: error …» con el motivo. Al final verá «Finished N products.». Sin ningún idioma marcado verá «Select at least one language.».

Mantenga abierta la pestaña del navegador hasta que termine la ejecución. Cerrarla detiene la ejecución, y los productos ya escritos permanecen guardados. Para continuar, construya la lista de nuevo con **Actualizar solo** establecido en los productos que no se han actualizado. Un fallo en un campo no deshace los ya guardados. Empiece con un **Límite de productos** pequeño, como 20, y revise primero la redacción.

### 3.8 Generar – Categorías

Abra **Generar**, luego la subpestaña **Categorías**. Los dos pasos funcionan como en la pantalla de productos.

![Generar categorías (Generate categories)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Paso 1 – el formulario **Filtrar categorías para actualizar**:

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Categorías** | Nada marcado | Elige las categorías para el paso siguiente. Un árbol vacío no limita la lista por categoría, así que la lista contiene entonces todas las categorías con el estado elegido, incluidas **Inicio** y la categoría raíz. Marque las categorías que desee. |
| **Estado de la categoría** | Activo | **Activo**, **Desactivado** o **Ambos**. |

Haga clic en **Ir al siguiente paso**.

Paso 2 – el panel **Generación masiva de categorías** y la tabla de categorías (**ID**, **Resultado**):

| Campo | Valor inicial | Qué hace |
|---|---|---|
| Cuadro del prompt (primer cuadro) | Vacío | La instrucción que se envía para cada categoría. Describa el tono, la longitud y el HTML. Nombre el tema en el texto. Este cuadro no inserta marcadores de producto. Este panel no tiene selector de plantillas. |
| Lista de campos | Descripción | El campo que escribir: **Descripción**, **Nombre**, **Meta título**, **Meta descripción** o **Descripción adicional**. Solo se guarda ese campo. |
| Lista de texto existente | Reemplazar | **Reemplazar** sobrescribe. **Omitir si está lleno** deja en paz un campo con contenido y no llama al modelo para esa categoría. |
| Lista de idiomas | Su idioma actual | Un idioma. Vuelva a ejecutar para otro idioma. |

Haga clic en **Ejecutar en las categorías siguientes**. Los resultados aparecen por fila, como en la pantalla de productos. Una categoría sin campo **Descripción adicional** en su versión de PrestaShop muestra «Error! This PrestaShop version does not support the category Additional Description field.».

Debajo de la tabla, la pantalla muestra también el formulario **Generar contenido de categoría**. Su introducción dice «This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives.» En esta versión, ese formulario no inicia una ejecución. Use **Ejecutar en las categorías siguientes**, más arriba. El formulario tiene estos campos:

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Campo que actualizar** | Descripción | El campo de categoría que reescribiría este formulario: **Nombre de la categoría**, **Descripción**, **Meta título**, **Meta descripción** o **Descripción adicional**. Solo ese campo se envía al modelo y se guarda. Los demás campos quedan como están. Descripción y meta son ejecuciones separadas. |
| **Datos existentes** | Conservar los datos existentes y añadir el nuevo contenido generado al principio | Qué ocurre cuando el campo elegido ya tiene texto: **Conservar los datos existentes y añadir el nuevo contenido generado al principio**, **Conservar los datos existentes y añadir el nuevo contenido generado al final**, **Conservar los datos existentes y omitir la categoría** o **Eliminar los datos y añadir el nuevo contenido generado**. Reemplazar cambia el texto almacenado. Omitir no llama al modelo para una categoría que ya tiene ese campo. Añadir conserva ambas versiones en un solo campo. |
| **Idioma** | Primer idioma de la lista | La versión de idioma que se escribe. Solo cambia ese idioma. |
| **Prompt de contenido** | Vacío (obligatorio) | La instrucción para cada categoría de la lista. Describa el tono, la longitud y el HTML. Nombre el tema de la categoría en el texto, porque los marcadores de producto no se insertan. |
| **Retraso entre llamadas a la API** | Vacío | Una pausa en segundos entre una categoría y la siguiente, para no alcanzar el límite de frecuencia de OpenAI. Use 1 o 2 con una clave de nivel bajo. Ponga 0 para enviar la siguiente solicitud de inmediato. El panel **Ejecutar** de arriba no usa esta pausa. |

Los botones **Generar contenido** y **Volver al filtro de categorías** no generan texto. **Generar contenido** solo almacena los valores que escribió y vuelve a mostrar el filtro. **Configuración del módulo** abre la configuración del módulo.

### 3.9 Nuevo producto

Abra **Nuevo producto**. El panel **Crear un producto a partir de un brief** pide al modelo un borrador de producto y puede insertar ese borrador como producto nuevo. Sirve para productos que todavía no están en el catálogo. Para rellenar un producto existente, use **Generar** o la página del producto.

![Nuevo producto (New product)](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

Si no hay ninguna clave guardada, verá «Añada una clave API en la configuración del módulo primero.».

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **¿Qué es el producto?** | Vacío (obligatorio) | El brief que el modelo amplía a nombre, descripciones, meta, etiquetas, características, referencia y precio. Escriba unas frases con material, público y nombres que deban mantenerse. Un cuadro vacío se rechaza con «Prompt is required». |
| **URL de origen opcional** | Vacío | Una dirección web completa de una página pública sobre el producto. Una página legible añade al brief su título, descripción y texto de precio. Una página que no se puede leer se ignora. |
| **Idioma** | Idioma predeterminado de la tienda | El idioma en el que se guarda el texto. Los demás idiomas no se rellenan. Elija el idioma predeterminado de su tienda, porque PrestaShop necesita un nombre en el idioma predeterminado para crear un producto. |
| **ID de categoría predeterminada** | 2 | El número de categoría de **Catálogo**, **Categorías**. 2 suele ser **Inicio**. El producto se coloca en esa categoría y esta pasa a ser su categoría predeterminada. |

1. Haga clic en **Generar datos**. El borrador aparece como texto en el cuadro de debajo (nombre, descripción, descripción corta, meta título, meta descripción, palabras clave, etiquetas, referencia, precio, características). Todavía no se guarda nada. Haga clic de nuevo para obtener un borrador nuevo. No puede editar el borrador en esta pantalla.
2. Revise el borrador, en especial el precio y la referencia sugeridos.
3. Haga clic en **Crear producto**. La línea de resultado muestra «Product #» y el número del producto nuevo.

El producto nuevo está activo, disponible para pedido, visible en el catálogo y en la búsqueda, con condición nuevo, con el grupo de reglas de impuestos número 1, un stock de 100 unidades y el precio sugerido. Nombre, descripciones, meta, etiquetas y características se guardan solo en el idioma elegido. Esta pantalla no añade fotos. Abra el producto nuevo, pestaña **Módulos**, **Fotos**, para añadirlas. Compruebe precio, impuesto, cantidad y categoría antes de publicar. La generación aquí no se registra en el Historial y no cuenta para el presupuesto mensual.

### 3.10 Cron

Abra **Cron**. El cron es para el servidor, no para una persona que hace clic en **Ejecutar**. Esta pantalla guarda sus elecciones y muestra las direcciones secretas que su servidor llama según un calendario. Cada llamada real escribe un pequeño lote y se detiene. La tienda no hace nada hasta que el servidor solicita la dirección.

![Cron (Cron)](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

El panel superior **Cron de categoría** y el panel **Parámetros de Cron** muestran las direcciones de su tienda con los secretos. Trate los secretos como contraseñas: nunca publique una dirección completa. Este manual los muestra como `YOUR_SECURE_KEY`, por ejemplo `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. A cada dirección hay que añadirle los ajustes del formulario (campo, idioma, plantilla, tamaño del lote, etc.). La sección 6.3 los enumera. Pida a su desarrollador o a su proveedor de alojamiento que los añada al configurar el programador.

Formulario de productos **CRON JOB Settings – Generate product content using OpenAI**. Haga clic en **Guardar** después de cambiarlo.

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Activar la función cron** | No | Permite al servidor generar textos de productos y categorías según un calendario. Actívela solo después de guardar el secreto, el campo, el idioma y la plantilla. Mientras esté desactivada, cada dirección cron responde que la función está desactivada. Este único interruptor también es necesario para el cron de categorías. |
| **Token secreto del trabajo cron** | Valor aleatorio largo | Una contraseña larga que debe formar parte de la dirección cron de productos. Sin ella, la tienda rechaza la llamada. Conserve el valor generado. Cambiarlo invalida de inmediato la dirección antigua. El botón **Generar token** no crea un valor nuevo en esta versión, así que conserve el valor creado en la instalación. |
| **Campo que actualizar** | description | El único campo de producto que escribe este cron: name, description, description_short, meta_title, meta_description o tags. Para rellenar varios campos, cree varios comandos de cron. |
| **Productos seleccionados** | pendingOpenAI | Decide qué productos siguen esperando. **pendingOpenAI**: productos que el módulo aún no ha escrito (cualquier campo). **pendingField**: productos aún no escritos para este campo concreto, de modo que varios comandos (por ejemplo description y name) puedan trabajar sobre los mismos productos. **emptyField**: solo productos en los que el campo elegido está vacío. Cada ejecución omite los productos que ya no coinciden, de modo que un catálogo terminado deja de cambiar. |
| **Categorías de producto** | Nada marcado | Limita la ejecución a las categorías marcadas. Un árbol vacío significa que la categoría no es un filtro. |
| **Lista de ID de producto** | Vacío | Limita la ejecución a estos números de producto, separados por comas. Las letras y otros caracteres se eliminan al guardar. |
| **Idioma** | Idioma predeterminado de la tienda | La versión de idioma que se escribe. Los demás idiomas necesitan su propio comando. |
| **Productos que actualizar** | 5 productos | Cuántos productos coincidentes procesa una llamada (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 o 1000). Empiece con 5 o 10 para que un modelo lento no alcance el límite de tiempo del servidor. |
| **Plantilla de prompt** | Primera plantilla de la lista | La instrucción guardada que se usa para cada producto de la ejecución. Los marcadores se rellenan por producto. Elija una plantilla activada. |
| **Activar depuración** | No | Cuando la dirección se abre con la depuración activada, imprime el plan (ajustes, productos seleccionados, prompts finales) y no escribe nada. Compruebe un comando con ella una vez. Desactívela antes de que el programador use la dirección. |
| **Intervalo del trabajo cron** | Cada hora | El ritmo que planea usar (cada 1, 2, 5, 10 o 30 minutos, cada hora, cada 2 o cada 6 horas). Documenta su plan. El módulo no inicia el programador. |
| **Comando del trabajo cron de productos** | – | Muestra la línea de comando que debe copiar en el programador. Guarde primero el formulario. |

Formulario de categorías **CRON JOB Settings – Generate category content using OpenAI**. Tiene su propio secreto y su propio botón **Guardar**, y no necesita su propio interruptor de activación:

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Token secreto del trabajo cron** | Valor aleatorio largo | La contraseña de la dirección de categorías. Es independiente del secreto de productos. Cambiarlo invalida la dirección antigua de categorías. |
| **Campo que actualizar** | description | El único campo de categoría que se escribe: name, description, meta_title o meta_description. |
| **Categorías seleccionadas** | pendingOpenAI | Las mismas tres reglas que para los productos, aplicadas a las categorías. **pendingField** permite que varios comandos compartan las mismas categorías. |
| **Idioma** | Idioma predeterminado de la tienda | La versión de idioma que se escribe. |
| **Categorías que actualizar** | 5 categorías | Cuántas categorías procesa una llamada (de 2 a 1000). |
| **Plantilla de prompt** | Primera plantilla de la lista | Escriba la plantilla para una categoría, no para un producto, por ejemplo con `{category_name}`. |
| **Activar depuración** | No | Imprime el plan y no guarda categorías. |
| **Intervalo del trabajo cron** | Cada hora | El ritmo que planea usar. |
| **Comando del trabajo cron de categorías** | – | La línea de comando que debe copiar después de guardar. |

El cron de categorías nunca toca **Inicio** ni la categoría raíz.

### 3.11 Historial

Abra **Historial**. El Historial es el registro de lo que se pidió y de lo que se obtuvo. Abrir o filtrar la página no borra nada ni modifica ningún producto.

![Historial (History)](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

La barra de filtros se abre en **Este mes**. Use los botones de periodo **Hoy**, **7 días**, **30 días**, **Este mes** y **Todo el tiempo**, o **Desde** y **Hasta**. También puede acotar por **Modelo**, **Tipo**, **Estado** (**Cualquiera**, **Éxito**, **Error**), **Idioma**, **Empleado**, **ID de producto / categoría** y **La instrucción o respuesta contiene**. Haga clic en **Filtrar**.

- Las tarjetas muestran **Solicitudes**, **Éxito**, **Errores**, **Tokens enviados**, **Tokens recibidos**, **Tokens totales** y **Tiempo promedio** para el filtro. Un guion significa que OpenAI no devolvió el número de tokens de esa llamada.
- Los paneles **Por día**, **Por modelo**, **Por tipo**, **Por idioma** y **Por empleado** agrupan las mismas filas por **Grupo**, **Llamadas**, **Enviado**, **Recibido** y **Total**. Un pequeño número en cursiva junto a las llamadas es el número de errores.
- La lista **Historial de prompts** tiene las columnas **ID**, **Estado**, **Prompt**, **Respuesta / Error**, **Proveedor** (modelo, código de error, segundos), **Enviado**, **Recibido**, **Total**, **ID de entidad**, **Tipo** y **Marca de tiempo**. El prompt y la respuesta aparecen abreviados. Haga clic en **Ver** en una fila para leer el prompt y la respuesta completos con los tokens, y luego en **Volver a la lista**. Una fila de error muestra el texto del error en lugar de una respuesta. **Tipo** muestra lo que se escribió, por ejemplo product_description o category_meta_title. Las simulaciones y la zona de pruebas también crean filas.
- El botón **Borrar lista** elimina todas las filas de golpe, sin preguntar, también las que están fuera de su filtro. Después, los contadores del **Panel de control**, el filtro **Actualizar solo**, la regla **pendingOpenAI** y el contador del presupuesto mensual empiezan desde cero, y **Restaurar** ya no es posible para textos antiguos.

### 3.12 Imágenes

Abra **Imágenes**. Esta página no descarga imágenes. Activa o desactiva la búsqueda de imágenes de la página del producto y guarda la instrucción usada para esa búsqueda.

![Imágenes (Images)](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Buscador de imágenes con IA** | Activado | **Activado** muestra la pestaña **Fotos** en la página de edición del producto. **Desactivado** la elimina. Una imagen solo se importa después de que alguien la confirme. |
| **Prompt de búsqueda de imágenes con IA** | El mismo texto largo que en **General** | La instrucción que se envía cuando alguien busca. `{product_name}` y `{product_description}` se sustituyen por el producto actual. Mantenga la petición de una lista simple de direcciones de página. |

Haga clic en **Guardar**. Verá «Configuración guardada.». La búsqueda de páginas y la importación de fotos se describen en la sección 3.13.

### 3.13 Edición del producto (pestaña Módulos)

Abra **Catálogo**, **Productos**, edite un producto y abra la pestaña **Módulos**. El panel **Mi ChatGPT** tiene las pestañas **Generar**, **Simular**, **Fotos** e **Historial**. Si **Formulario de la página de edición de producto** está desactivado, solo queda **Historial**. Si **Historial de edición de productos** también está desactivado, no aparece nada. Guarde un producto nuevo una vez antes de generar, para que tenga un número.

![Edición del producto (Product edit)](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Generar** escribe un campo y lo guarda en el producto de inmediato.

1. Elija un chip de **Idioma**, o **Todos los idiomas**.
2. En **Si el campo ya tiene texto** elija **Reemplazar**, **Añadir arriba**, **Añadir abajo** u **Omitir si está lleno**.
3. Haga clic en **Rellenar** en una tarjeta de campo: **Descripción** (texto largo con una breve introducción y una lista de características), **Descripción corta** (resumen en texto plano de menos de unos 400 caracteres), **Nombre**, **Meta título** (unos 70 caracteres), **Meta descripción** (unos 160 caracteres) o **Etiquetas** (palabras separadas por comas).
4. **Paquete SEO** con **Rellenar todo** escribe el nombre, ambas descripciones y ambos campos meta de una vez. Reemplaza esos campos sea cual sea su elección en **Si el campo ya tiene texto**.
5. Opcional: abra **Use su propia instrucción o una instrucción guardada**. Escriba en **Filtrar por título o texto**, elija **Brief estándar** (un brief ya preparado para el campo que pulse) o una plantilla activada, o escriba su propia **Instrucción**.

Debajo de los botones verá la instrucción enviada y la respuesta, y «Content successfully generated and updated to product.». El formulario del producto en pantalla no se actualiza. Recargue la página del producto antes de volver a editar. Si pulsa **Guardar** en el formulario antiguo, PrestaShop vuelve a escribir el texto antiguo. El módulo acorta las respuestas largas al tamaño del campo: nombre 128 caracteres, descripción corta 800, meta título 69, meta descripción 159.

**Simular** tiene las mismas opciones y los botones **Probar**. Muestra la respuesta en la página y no modifica el producto. El intento se escribe en el Historial.

**Fotos** (requiere **Buscador de imágenes con IA** activado):

1. Haga clic en **Buscar páginas**. El modelo sugiere páginas que probablemente muestren este producto.
2. Haga clic en la dirección de una página. La tienda lee la página (las direcciones de redes privadas o locales se rechazan) y enumera hasta 24 imágenes. Los iconos pequeños y los píxeles de seguimiento se omiten.
3. Marque las fotos que desee. La primera foto que marque pasa a ser la imagen de portada del producto y sustituye a la portada actual. Las demás se añaden después de las fotos existentes.
4. Haga clic en **Añadir seleccionados a este producto**. No se guarda nada antes de este clic. Recargue el producto para ver las fotos.

Las búsquedas de fotos no se escriben en el Historial y no cuentan para el presupuesto. Respete los derechos de autor de las fotos que importe.

**Historial** enumera las escrituras anteriores de este producto con **Cuándo**, **Tipo** y **Estado**. **Restaurar** devuelve el texto anterior después de que confirme «Restore the previous value?». Verá «Content successfully restored. Refresh this page to see changes.». El Historial de toda la tienda no se borra.

Junto a los campos de descripción, descripción corta, meta título y meta descripción (en cualquier formulario de producto) verá también un pequeño botón redondo con el logotipo de OpenAI, **Generar con IA**. Haga clic en él. Si la tienda tiene más de un idioma, elija **Idioma actual**, **Todos los idiomas** o **Cancelar**. El campo recibe un brief ya preparado para ese campo, y el texto va solo al campo del formulario, con «El texto está en el campo. Guarde el producto para conservarlo.». Haga clic en **Guardar** en el producto para conservarlo. Este botón no usa plantillas ni el cuadro **Instrucción**.

### 3.14 Actualizaciones

Abra **Actualizaciones** (lado derecho del menú superior). El formulario **Actualizaciones de MyPresta** comprueba en MyPresta.eu si hay un archivo de módulo más reciente. No modifica su catálogo y no instala nada.

![Actualizaciones (Updates)](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Campo | Valor inicial | Qué hace |
|---|---|---|
| **Comprobación manual** | – | Haga clic en **Comprobar ahora**. La tienda consulta una vez el servidor de actualizaciones de MyPresta.eu y muestra «¡El módulo está actualizado!» o «¡Nueva versión disponible!» junto al botón. |
| **Notificaciones automáticas** | Activado | **Activado** permite que el back office compruebe aproximadamente cada tres días y muestre un aviso con un enlace cuando existe una versión más reciente. **Desactivado** lo detiene. |
| **Página del producto** | – | Un enlace a la página del módulo en MyPresta.eu. |

Haga clic en **Guardar** para almacenar la elección de las notificaciones. Verá «Configuración de actualización guardada.». El número de versión junto al nombre del módulo en el menú es la versión instalada en su tienda, no la más reciente.

## 4. Parte pública de la tienda

El módulo no muestra nada a sus clientes. No añade ningún bloque, página, script ni estilo al front de la tienda. El tema no tiene nada que sobrescribir. Todo lo que ve está en el back office: el botón **Mi ChatGPT** de la barra superior, las pantallas del módulo y el panel de la página del producto.

El módulo tiene dos direcciones web que existen solo para servidores y para el back office:

- La **dirección cron**. Cópiela de **Cron** (sección 3.10) y colóquela únicamente en el programador de su servidor. Cualquiera que conozca la dirección completa con el secreto puede iniciar un lote, así que nunca la publique ni la pegue en chats o tickets.
- Una dirección técnica que utilizan los botones del back office en cada generación. No la abra ni la comparta.

Abrir la dirección cron en un navegador muestra texto sin formato. Estos son los mensajes que puede leer:

| Qué ve | Qué hacer |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Abra **Cron**, ponga **Activar la función cron** en **Sí** y haga clic en **Guardar**. |
| The token does not exist or it’s wrong! | El secreto falta o no coincide. Vuelva a copiar la dirección desde **Cron** después de guardar. |
| Invalid action! | La dirección no tiene la parte de la tarea. Añada los ajustes enumerados en la sección 6.3. |
| updatedField parameter is wrong! | El nombre del campo de la dirección no es uno de los campos permitidos. Use un campo de **Campo que actualizar**. |
| All must include all mandatory parameters! | A la dirección le falta el campo, la regla de selección, el tamaño del lote, el idioma o la plantilla. Añádalos (sección 6.3). |
| productTarget parameter is wrong! Allowed values: … (o categoryTarget) | Use pendingOpenAI, pendingField o emptyField. |
| No valid product IDs provided. | La **Lista de ID de producto** no contiene números utilizables. Corrija o vacíe la lista. |
| No products to update. / No categories to update. | Ya nada cumple la regla. El trabajo ha terminado, o cambie **Productos seleccionados** o los filtros. |
| N products have been updated. / N categories have been updated. | Se escribió un lote. La siguiente llamada continúa con los elementos siguientes. |
| N pending products. | La depuración está activada. No se escribió nada. Desactive la depuración para las ejecuciones reales. |
| Error!Monthly generation budget reached. | Suba el **Presupuesto de generación mensual** o espere al mes siguiente. |
| Error!Reply rejected by the studio quality gate. | La respuesta contenía una palabra prohibida. Edite **Palabras prohibidas** o desactive la **Puerta de calidad**. |
| Error! The model returned an empty response. | Aumente **Máximo de tokens**, pruebe otro modelo u otra plantilla. |
| Error! seguido de un mensaje de OpenAI | Lea el mensaje. Las causas típicas son una clave incorrecta, falta de crédito o un modelo desconocido. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop rechazó el texto de ese elemento. Revise el producto y vuelva a ejecutar. |

## 5. Solución de problemas

### 5.1 Conexión y ajustes

| Síntoma | Causa | Qué hacer |
|---|---|---|
| «The OpenAI API key is not set. Add it in the module settings.» o «The ChatGPT API key is not set. Add it in the module settings.» | No hay ninguna clave almacenada. | Abra **Configuración**, **ChatGPT**, pegue la clave en **CLAVE API de OpenAI** y haga clic en **Guardar**. |
| «¡El campo CLAVE API de OpenAI no es válido!» | Guardó una clave nueva de menos de 10 caracteres mientras no había ninguna clave almacenada. | Pegue la clave completa. |
| «¡El campo Modelo de OpenAI no es válido!» | **Modelo** tiene menos de 3 caracteres. | Elija un modelo de la lista y guarde de nuevo. |
| Mensaje de OpenAI sobre una clave incorrecta, una cuota o un modelo que no existe | OpenAI rechazó la llamada. El módulo muestra el texto propio de OpenAI. | Revise la clave, la facturación de OpenAI y el nombre del modelo en **Configuración**, **ChatGPT**. Un modelo que haya añadido debe estar disponible para su cuenta. |
| «Error! Invalid token!» | La página se abrió antes de que el módulo renovara su secreto interno, o llevaba abierta mucho tiempo. | Recargue la página e inténtelo de nuevo. |
| «OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.» | OpenAI respondió demasiado despacio. | Suba **Tiempo de espera de la API (segundos)** en **Configuración**, **General** (hasta 600), use un modelo más rápido o pida un texto más corto. |
| «The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking.» | **Máximo de tokens** es demasiado bajo para este modelo. | Suba **Máximo de tokens** en **Configuración**, **ChatGPT**. |
| «The response was blocked by the provider content filter. Try rewording the prompt.» | El filtro de OpenAI detuvo la respuesta. | Reformule el prompt o los datos del producto que utiliza. |
| «The model returned an empty response.» | El modelo no devolvió texto. | Inténtelo de nuevo, con otro modelo o con un prompt menos estricto. |
| «Monthly generation budget reached. Raise it in the studio settings or wait until next month.» | El número de generaciones correctas alcanzó el **Presupuesto de generación mensual**. | Suba el número en **Configuración**, **Estudio**, póngalo en 0 o espere al mes siguiente. Borrar el **Historial** también reinicia el contador. |
| «The reply was rejected because it contains a forbidden word from the studio settings.» | Una línea de **Palabras prohibidas** aparece en la respuesta, también dentro de una palabra más larga. | Acorte o edite la lista, o ponga **Puerta de calidad** en **No**. No se escribió nada en el producto. |

### 5.2 Página del producto y resultados de la generación

| Síntoma | Causa | Qué hacer |
|---|---|---|
| Falta el panel **Mi ChatGPT** en la página del producto. | **Formulario de la página de edición de producto** e **Historial de edición de productos** están ambos desactivados, o no está en la pestaña **Módulos**. | Active los interruptores en **Configuración**, **General** y abra la pestaña **Módulos**. |
| «Guarde el producto una vez antes de generar.» | El producto aún no tiene número. | Guarde el producto y luego genere. |
| El texto nuevo desapareció después de guardar el producto. | El formulario del producto en pantalla todavía contenía el texto antiguo. | Después de **Rellenar**, recargue la página del producto antes de editar y guardar. |
| «Product skipped.» o «Category skipped.» | **Omitir si está lleno** encontró texto en el campo. No es un error. | Elija **Reemplazar**, **Añadir arriba** o **Añadir abajo** si quiere escribir de todos modos. |
| «Error! Content retrieve has failed! Details: …» | OpenAI o el servidor devolvió un error. | Lea los detalles después de «Details:». Abra el **Historial**, filtre **Estado** por **Error** y abra la fila. |
| «Error! The generated content could not be saved to the product.» o «… to the category.» | PrestaShop rechazó el texto, por ejemplo por un carácter no permitido. | Lea el motivo después de la frase. Pruebe otro prompt o un campo más corto. |
| «Error! Prompt is missing or too short!» | La instrucción tiene menos de 4 caracteres. | Escriba una instrucción más larga o deje el cuadro vacío para usar el brief estándar. |
| «Error! Product not found!» / «Error! Category not found!» | El elemento se eliminó o el número es incorrecto. | Reconstruya la lista y vuelva a ejecutar. |
| «Error! This log entry has no previous value to restore.» o «Error! Nothing to restore for this entry.» | Esa fila del Historial no tiene texto antiguo. | Use otra fila. Las filas escritas por **Simular** o los errores no pueden restaurar nada útil. |
| «The model did not return a usable SEO pack.» | La respuesta no tenía el formato esperado. | Haga clic de nuevo en **Rellenar todo** o rellene los campos uno a uno. |
| «Error de generación.» en un botón **Generar con IA** | La llamada falló. | Inténtelo de nuevo. Consulte el motivo en el **Historial**. |
| «Error! This PrestaShop version does not support the category Additional Description field.» | Su tienda no tiene ese campo de categoría. | Elija otro campo de categoría. |

### 5.3 Generación masiva

| Síntoma | Causa | Qué hacer |
|---|---|---|
| La tabla después de **Ir al siguiente paso** está vacía. | Los filtros no coinciden con nada. | Relaje los filtros. Revise **Estado del producto**, **Stock del producto** y **Actualizar solo**. |
| «Select at least one language.» | No hay ningún idioma marcado. | Marque al menos un idioma. |
| La ejecución se detuvo a mitad de camino. | Se cerró la pestaña, se cortó la conexión o se detuvo el servidor. | Reconstruya la lista con **Actualizar solo** establecido en los productos que no se han actualizado y vuelva a ejecutar. |
| Muchas filas muestran errores. | Un problema de presupuesto, clave o tiempo de espera. | Abra el **Historial**, lea el primer error, corríjalo y vuelva a ejecutar. |
| Inicio y la categoría raíz aparecen en la lista de categorías. | **Categorías** se dejó vacío. | Marque las categorías que desee antes de **Ir al siguiente paso**. |

### 5.4 Cron

| Síntoma | Causa | Qué hacer |
|---|---|---|
| No cambia nada en el catálogo. | **Activar la función cron** está desactivada, el programador no llama a la dirección o ningún elemento cumple la regla. | Revise el interruptor, el registro del programador y **Productos seleccionados**. Abra la dirección una vez con la depuración activada para ver el plan. |
| La dirección responde con un mensaje de la tabla de la sección 4. | Consulte esa tabla. | Haga lo que dice la tabla. |
| Los mismos productos se escriben una y otra vez. | **Productos seleccionados** es **emptyField** y el campo sigue vacío, o se usa **pendingOpenAI** y se borró el Historial. | Use **pendingField**, o corrija el prompt para que se escriba texto. |
| Una dirección antigua dejó de funcionar. | El módulo sustituye los secretos de menos de 24 caracteres, o se cambió el secreto, o se reinstaló el módulo. | Vuelva a copiar la dirección desde **Cron** y actualice el programador. |
| **Generar token** no hace nada. | El botón no tiene función en esta versión. | Conserve el secreto creado en la instalación. |

### 5.5 Imágenes, nuevo producto y menú

| Síntoma | Causa | Qué hacer |
|---|---|---|
| Falta la pestaña **Fotos**. | **Buscador de imágenes con IA** está desactivado. | Actívelo en **Configuración**, **General** o **Imágenes** y recargue el producto. |
| «No pages were suggested.» o «The search failed.» | El modelo no devolvió direcciones utilizables, o la clave tiene un problema. | Haga clic de nuevo en **Buscar páginas** o revise el **Prompt de búsqueda de imágenes con IA**. |
| «That page could not be read.», «URL not allowed (private network)» o un error que empieza por HTTP | La página bloquea la tienda, requiere inicio de sesión o está en una red privada. | Elija otra página. |
| «No photos were found on that page.» | La página no tiene imágenes utilizables. | Elija otra página. |
| «No images could be imported. Details: …» | Las imágenes no se pudieron descargar o no son imágenes reales. | Lea los detalles. Elija otras fotos. |
| «Failed to parse AI response. Please try again.» en **Nuevo producto** | La respuesta no tenía el formato esperado. | Haga clic de nuevo en **Generar datos**. |
| «Error creating product: …» o «Failed to create product» | PrestaShop rechazó el producto, a menudo porque el **Idioma** elegido no es el idioma predeterminado de la tienda. | Elija el idioma predeterminado y revise el número de categoría. |
| «Generate the product first.» | Hizo clic en **Crear producto** antes de **Generar datos**. | Haga clic primero en **Generar datos**. |
| Falta la entrada de menú **Generador de Contenido con IA**. | El módulo está desactivado, o la entrada se movió. | Active el módulo en el **Administrador de módulos** y abra una vez cualquier página del back office. El módulo vuelve a poner la entrada en **Módulos**. Si sigue sin aparecer, compruebe que su perfil de empleado puede abrir **Módulos**. |
| El Panel de control y el Historial están vacíos. | No se generó nada en el periodo elegido, o se usó **Borrar lista**. | Elija **Todo el tiempo**. |

## 6. Para desarrolladores

### 6.1 Resumen

| Elemento | Valor |
|---|---|
| Nombre técnico | mychatgpt |
| Versión | 1.1.0 |
| Nombre en la lista de módulos | My ChatGPT - AI content generation |
| Autor | MyPresta.eu |
| Pestaña del módulo | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| PHP mínimo | 7.0.0 (comprobado en `install()`) |
| Clase principal | `mychatgpt extends Module`, con las clases auxiliares `mychatgptUpdate` y `searchToolmychatgpt` que la extienden |

Flujo de datos: el JavaScript del back office llama al controlador de front `ajax` con `secret_token` (leído de `MYPRESTA_MYCHATGPT_TOKEN`) o a un controlador de administración. El controlador lee las claves de modelo y de muestreo, aplica el Estudio (`MyChatGPT\Studio`), llama a OpenAI mediante `MyChatGPT\OpenAIService` (cURL al endpoint de chat completions de la API de OpenAI), escribe el texto con el modelo de objetos de PrestaShop e inserta una fila en `mychatgpt_log`. `cron` hace lo mismo sin navegador. `getServiceName()` siempre devuelve `openai`. Se eliminó el código sobrante de otros proveedores. Las claves de ajustes de un segundo proveedor anterior (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) se eliminan cada vez que se abre la pantalla de ajustes.

### 6.2 Archivos

| Ruta | Finalidad |
|---|---|
| `mychatgpt.php` | Clase principal: instalación y desinstalación, pestañas, formularios de ajustes, plantillas de prompt, panel de control, hooks, pestaña del producto, catálogo de modelos. |
| `autoload.php` | Pequeño cargador de clases para el espacio de nombres `MyChatGPT\` (sin Composer). |
| `src/OpenAIService.php` | Cliente cURL para chat completions y listado de modelos. Tiempo de espera 10–600 s, descarta los parámetros que un modelo rechaza (hasta 6 reintentos), desactiva la verificación de certificados solo en localhost. |
| `src/Studio.php` | Comprobación del presupuesto, decoración del prompt (idioma, voz, audiencia, tono, glosario, prohibidas), inspección de la respuesta, paquete SEO y prompts de texto alternativo. |
| `controllers/admin/*.php` | Siete controladores de administración (sección 6.3). |
| `controllers/front/ajax.php` | Endpoint JSON para toda la generación activada desde el navegador. |
| `controllers/front/cron.php` | Endpoint cron de texto sin formato. |
| `lib/updateChecker.php` | Comprobación de actualizaciones contra dev.mypresta.eu cada 3 días y el formulario Actualizaciones. |
| `lib/sectionHelp.php` | Textos del cajón de Ayuda. |
| `lib/searchTool/` | Clase auxiliar `searchToolmychatgpt` (herramienta de autocompletado en las pantallas del módulo). |
| `lib/prestashop9compatibility.php` | Envoltorios para la visualización de precios, el hash y las redirecciones en PrestaShop 9. |
| `views/templates/hook/*.tpl` | Pantallas y paneles del módulo (panel de control, navegación, subnavegación, generadores masivos, pestaña del producto, historial, información de cron, cuadro de la barra superior). |
| `views/templates/admin/product_creator.tpl` | Pantalla de nuevo producto. |
| `views/js/back.js` | Ejecuciones masivas, panel del producto, zona de pruebas, cuadro de la barra superior, nuevo producto, restauración. |
| `views/js/product-fields.js` | Botones **Generar con IA** junto a los campos del producto. |
| `views/js/image-finder.js` | Pestaña **Fotos**. |
| `views/js/admin-products-bulk.js` | Añade el botón **Mi ChatGPT** a la lista de productos. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Gráficos y cajón de Ayuda. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Estilos. |
| `translations/*.php` | 34 archivos de idioma. |
| `upgrade/index.php` | Solo un archivo de redirección. No hay scripts de actualización. |

Las clases `AdminMyChatGPTMain` y `AdminMyChatGPTSettings` llaman a `addJS`/`addCSS` para `views/js/admin.js` y `views/css/admin.css`, y el controlador de nuevo producto para `product_creator.js` y `product_creator.css`. Ninguno de estos archivos se incluye. El formulario de cron espera las funciones JavaScript `generateTokenAndFill()` y `generateCategoryTokenAndFill()` y rellena los span `.cron-parameters`. Ese script tampoco se incluye.

### 6.3 Controladores

| Controlador | Padre y ruta | Finalidad |
|---|---|---|
| `AdminMyChatGPTMain` | Bajo **Módulos**, visible. Redirige a la configuración del módulo, Panel de control. | La entrada de menú **Generador de Contenido con IA**. |
| `AdminMyChatGPTSettings` | Pestaña oculta (`active = 0`). Redirige a la configuración, Configuración. | Entrada de compatibilidad. |
| `AdminMyChatGPT` (archivo `AdminMyChatGPT.php`, clase `AdminMyChatGPTController`) | Pestaña oculta. `mcg_sub=products` o `categories`. | Filtros y generadores masivos. `renderProductUpdateForm()` y el formulario de actualización de categorías no tienen manejador. Los envíos `generateProductContent` y `generateCategoryContent` solo guardan los valores del formulario. La generación se ejecuta desde `back.js`. |
| `AdminMyChatGPTProductCreator` | Pestaña oculta. Acciones Ajax `generateProductData`, `createProduct`, `extractImages`, `generateImages` (stub). | Nuevo producto. |
| `AdminMyChatGPTCron` | Pestaña oculta. Formularios `submitCronUpdate`, `submitCatCronUpdate`. | Ajustes de cron. |
| `AdminMyChatGPTUsage` | Pestaña oculta. Parámetros `stats_*`, `view` y `clear_log`. | Historial. `clear_log` ejecuta `DELETE` sobre toda la tabla de registro. |
| `AdminMyChatGPTImageFinder` | Pestaña oculta. Acciones Ajax `searchImages`, `extractImages`, `saveImages`. | Formulario **Imágenes** y búsqueda de fotos. |

Todos los controladores de administración redirigen a la pantalla de inicio si el módulo está inactivo. La página de configuración del módulo (`getContent`) muestra Panel de control, Configuración (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) y Actualizaciones (`mcg_tab=updates`).

Controlador de front `ajax` (`secret_token` debe ser igual a `_TOKEN`; no hay comprobación de empleado). Acciones: `initiatePrompt`, `updateSettings` (escribe max tokens, temperature, top p y ambas penalizaciones), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (ningún botón la usa; 8 imágenes como máximo), `generateSeoPack`. `updateProduct` y `updateCategory` reciben `target` (campo), `behavior` (`replace`, `keep`, `keep_top`, `keep_end` o `single_product` para una vista previa que no se guarda), `prompt`, el idioma y el número del elemento. Las respuestas son JSON con `status` (`success`, `error`, `skipped`), `msg` y `date`.

Controlador de front `cron`: rechaza con el mensaje «disabled» cuando `_ENABLE_CRON` es 0. El parámetro `secret` debe ser igual a `_SECRET` o `_CAT_SECRET` (cualquiera de los dos secretos abre cualquiera de los dos trabajos). Parámetros:

| Parámetro | Usado por | Significado |
|---|---|---|
| `secret` | ambos | Secreto de productos o de categorías. |
| `action` | ambos | `generateProductContent` o `generateCategoryContent`. |
| `updatedField` | ambos | Productos: name, description, description_short, meta_title, meta_description, tags. Categorías: name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | cada uno | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | cada uno | Tamaño del lote (`LIMIT`). |
| `languageId` | ambos | Número de idioma. |
| `promptTemplateId` | ambos | Número de plantilla de `mychatgpt_prompt`. |
| `debug` | ambos | Cualquier valor distinto de 0 imprime el plan y no escribe nada. |
| `categories` | productos | Números de categoría separados por comas. |
| `productIds` | productos | Números de producto separados por comas. |

Ejemplo (use `YOUR_SECURE_KEY` solo como marcador de posición):

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` y `pendingField` examinan las filas correctas de `mychatgpt_log` (las filas con estado error se ignoran, por lo que los elementos fallidos se reintentan). El trabajo de categorías excluye las categorías con un número hasta la categoría de inicio inclusive.

### 6.4 Hooks

Registrados en `install()`:

| Hook | Comportamiento |
|---|---|
| `displayAdminProductsExtra` | Muestra el panel de la pestaña **Módulos** (`product-tab-wrapper.tpl`) cuando `_PRODUCT` o `_PRODUCT_LOG` es 1. |
| `displayBackOfficeHeader` | Carga los recursos; ejecuta `ensureLongSecrets()` (sustituye `_TOKEN`, `_SECRET`, `_CAT_SECRET` de menos de 24 caracteres) y `placeModuleMenu()`; registra una vez la pestaña **Buscador de imágenes con IA** (`_IMAGEFINDER_TAB_OK`); pone en cola `product-fields.js`, `admin-products-bulk.js` y `image-finder.js` en `AdminProducts`; vuelve a registrar `dashboardZoneTwo` si falta. `product-fields.js` se pone en cola en cada página de producto, sea cual sea el valor de `_PRODUCT`. |
| `displayBackOfficeTop` | Define valores de JavaScript (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) y muestra el cuadro de la barra superior cuando `_TOPCTA` es 1. |
| `dashboardZoneTwo` | Muestra `dashboard.tpl`, que lee variables `mcg_*` que este hook no asigna. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Stub vacío, devuelve una cadena vacía. |
| `displayAdminProductsMainStepLeftColumnBottom` | Stub vacío, devuelve una cadena vacía. |
| `actionProductFormBuilderModifier` | Sin efecto, no devuelve nada. |
| `displayHeader` | Stub vacío. |
| `displayFooter` | Stub vacío. |

El método `hookActionProductGridDataModifier` existe pero no está registrado. El módulo no sobrescribe `enable()` ni `disable()` y no expone hooks propios.

### 6.5 Sobrescrituras

El módulo no tiene sobrescrituras.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Inicializada con 16 filas. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pares `old_*` y `new_*` para name, description, description_short, meta_title, meta_description y tags, `date_updated`. Claves sobre `id_product` y `status`. |

La desinstalación elimina ambas tablas. `ensureUsageColumns()` añade las tres columnas de tokens al abrir una pantalla, si una tabla más antigua no las tiene. Las filas de productos, categorías e imágenes que escribe el módulo son datos estándar de PrestaShop y no se tocan en la desinstalación.

### 6.7 Claves y traducciones

Las claves usan el prefijo `MYPRESTA_MYCHATGPT_`. Valores establecidos en la instalación:

| Clave | Valor predeterminado |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | 32 caracteres aleatorios |
| `_API_KEY` | Un espacio |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Vacío (el segundo se rellena en tiempo de ejecución con los parámetros rechazados por modelo) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Vacío |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, prompt largo predeterminado |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, vacío, idioma predeterminado, vacío, 0, vacío |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, vacío, idioma predeterminado, 0 |
| `PS_USE_HTMLPURIFIER` | Establecido en 0 (en toda la tienda) |

Las claves de cron sin prefijo (`updatedField`, `debug` y las demás de arriba) son nombres globales y pueden chocar con otros módulos.

Creadas más tarde: `_IMAGEFINDER_TAB_OK`, `categories` (elección de categorías de cron), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` también escribe cada campo de filtro (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) en la configuración en cada petición de ese controlador, pero nada los vuelve a leer.

La desinstalación elimina las claves enumeradas en `uninstall()`. No restaura `PS_USE_HTMLPURIFIER`. Deja `categories`, las claves de filtro anteriores y las claves de actualización.

Los generadores, el cron y la validación habitual usan `Tools::getValue` con listas blancas. La clave API se almacena en texto sin formato en la tabla de configuración. `randomString()` usa `rand()`.

Traducciones: añada `translations/{iso}.php` en el formato estándar de módulos de PrestaShop (se incluyen 34 idiomas). Los textos pasan por `$this->l()` en la clase principal, en el comprobador de actualizaciones y en el cajón de ayuda. En PrestaShop 8 y 9, los controladores de administración usan `trans()` con los dominios `Admin.MyChatGPT`, `Admin.MyChatGPTCron` y `Admin.MyChatGPTUsage`. No se traducen: los mensajes dentro de `back.js` y `image-finder.js`, las instrucciones predeterminadas que usan **Rellenar** y **Generar con IA**, la salida de `cron` y los textos de error de `AdminMyChatGPTProductCreator` y `AdminMyChatGPTImageFinder`. Los textos largos de ayuda («What it does / How to configure / Effect») los construye `fieldHelp()` y residen en las definiciones de formulario de `mychatgpt.php` y de los controladores de administración (método `help()`), en las plantillas y en `lib/sectionHelp.php`. Los nombres de las plantillas predeterminadas y los nombres de menú se escriben en la base de datos en los idiomas de la tienda durante la instalación.

### 6.8 Ampliación

- Añada o edite plantillas de prompt en la pantalla del módulo o en `mychatgpt_prompt`.
- Añada marcadores de posición en los constructores de prompts de `ajax.php` (`updateProduct`, `updateCategory`) y de `cron.php`.
- Añada modelos en **Configuración**, **ChatGPT** sin cambiar código. El módulo aprende por sí solo los parámetros no admitidos.
- Cambie las instrucciones estándar de **Rellenar**, **Generar con IA** y las ejecuciones masivas en `back.js` y `product-fields.js`.
- El front office no tiene plantilla, así que el tema no tiene nada que sobrescribir. Las plantillas del back office de `views/templates` se cambian en la carpeta del módulo.

## 7. Ayuda

Página del producto: https://mypresta.eu/modules/administration-tools/my-chatgpt.html

Para escribir sobre el módulo:

1. Inicie sesión en su cuenta de cliente en mypresta.eu.
2. Abra la página de contacto.
3. Elija **Support for paid modules**.
4. Describa el problema. Indique el mensaje exacto de la pantalla y los pasos que llevan hasta él. Nunca pegue su clave API de OpenAI ni una dirección cron completa con el secreto.
