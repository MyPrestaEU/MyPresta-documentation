---
title: "Microsoft Merchant Center Product Feed - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Microsoft Merchant Center Product Feed de MyPresta.eu."
sidebar:
  label: "Microsoft Merchant Center Product Feed - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Microsoft Merchant Center Product Feed en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Microsoft Merchant Center Product Feed

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Su servidor debe poder ejecutar tareas cron para la generación automatizada del feed.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página principal de configuración del módulo. Aquí es donde configurará el comportamiento general y accederá a las herramientas de gestión de feeds.

#### Ajustes generales

Esta sección generalmente cubre los ajustes globales que afectan cómo el módulo opera y genera los feeds.

- **Qué hace este ajuste:** Estos son los ajustes principales que definen cómo se preparan los datos de sus productos para Microsoft Merchant Center. Normalmente encontrará opciones para seleccionar el idioma, la moneda y el país para su feed, así como las preferencias generales de exportación.
- **Efecto de cambiar este ajuste:**
  - *Idioma:* Determina qué versión lingüística de los nombres, descripciones y categorías de sus productos se incluirá en el feed. Crucial para dirigirse a mercados internacionales específicos.
  - *Moneda:* Establece la moneda para todos los precios en el feed. Debe coincidir con la moneda configurada en su cuenta de Microsoft Merchant Center para el país de destino.
  - *País:* Especifica el país de destino para el feed. Esto influye en las reglas fiscales, la configuración de envío y otros requisitos específicos del país en Microsoft Merchant Center.
  - *Otras opciones de exportación:* Puede incluir ajustes para manejar variantes de productos, excluir ciertas categorías o definir cómo se exportan atributos específicos (como tamaño o color).
- **Valor recomendado:**
  - *Idioma, Moneda, País:* Seleccione el idioma, la moneda y el país principales a los que se dirige con sus anuncios de compras de Microsoft. Si anuncia en varios países/idiomas, probablemente creará feeds separados para cada uno.
  - *Otras opciones:* Siga las recomendaciones del módulo o ajústelas según su catálogo de productos y estrategia publicitaria específicos.
- **Escenario / ejemplo de comerciante:** Si vende en Francia y el idioma predeterminado de su tienda es el francés, seleccionaría francés para el idioma, EUR para la moneda y Francia para el país. Si también vende en Alemania, crearía un feed separado configurado para el idioma alemán, la moneda EUR y Alemania como país.

#### Gestión y generación de feeds

Esta sección proporciona acceso para crear, gestionar y generar sus feeds de productos.

- **Qué hace este ajuste:** Este es el corazón del módulo, permitiéndole definir y generar los archivos de feed de productos reales. Normalmente encontrará opciones para crear nuevos feeds, ver los existentes y activar el proceso de generación.
- **Efecto de cambiar este ajuste:**
  - *Crear un nuevo feed:* Inicia el proceso de configuración de un nuevo feed de productos con sus propios ajustes específicos (idioma, moneda, categorías, etc.).
  - *Generar un feed:* Procesa los datos de sus productos de PrestaShop y crea el archivo CSV, XML o TSV que subirá a Microsoft Merchant Center. Este archivo contiene todos los atributos del producto en el formato requerido por Microsoft.
  - *URL de Cron:* Proporciona una dirección web especial que, al ser visitada, activa automáticamente la generación del feed. Esto es esencial para configurar actualizaciones diarias u horarias automatizadas de su feed de productos sin intervención manual.
- **Valor recomendado:**
  - Cree al menos un feed para su mercado objetivo principal.
  - Configure una tarea cron utilizando la URL proporcionada para asegurar que su feed de productos se actualice regularmente (por ejemplo, diariamente) con la información más reciente del producto (niveles de stock, precios, nuevos productos).
- **Escenario / ejemplo de comerciante:** Acaba de lanzar una nueva línea de productos. Al tener una tarea cron diaria, sus anuncios de compras de Microsoft reflejarán automáticamente estos nuevos productos y sus niveles de stock actuales al día siguiente, sin que tenga que volver a subir el feed manualmente.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminExportProductsFeedMicrosoftController (Back Office > Microsoft Merchant Center > Exportar Feed de Productos)

Esta es la pantalla principal dedicada a la gestión de los detalles de sus feeds de productos. Accederá a ella a través de un nuevo elemento de menú añadido por el módulo, probablemente bajo "Catálogo" o una nueva sección "Microsoft Merchant Center".

- **Nombre de la pantalla y ubicación del menú:** **Back Office > Microsoft Merchant Center > Exportar Feed de Productos** (o similar, dependiendo de la versión del módulo y la estructura del menú de PrestaShop).
- **Acciones y configuraciones disponibles:** Esta pantalla es donde define el contenido y la asignación específicos para cada uno de sus feeds de productos. Normalmente verá una lista de feeds existentes, con opciones para "Añadir nuevo feed" o "Editar" uno existente. Al añadir/editar, configurará:
  - **Nombre del feed:** Un nombre descriptivo para su feed (por ejemplo, "Francia - Feed francés", "EE. UU. - Feed inglés").
  - **País de destino:** El país al que está destinado este feed (por ejemplo, Francia, Estados Unidos). Esto afecta la moneda, el idioma y las reglas fiscales.
  - **Idioma del contenido:** El idioma de los datos del producto en este feed (por ejemplo, francés, inglés).
  - **Moneda:** La moneda utilizada para los precios en este feed (por ejemplo, EUR, USD).
  - **Formato de archivo:** Elija entre CSV, XML o TSV, según lo requiera Microsoft Merchant Center.
  - **Mapeo de categorías:** Esta es una sección crucial donde mapea sus categorías de PrestaShop a la taxonomía de productos de Microsoft. Esto ayuda a Microsoft a comprender qué son sus productos y mostrarlos en búsquedas relevantes.
  - **Filtrado de productos:** Opciones para incluir/excluir productos específicos o categorías enteras del feed.
  - **Mapeo de atributos:** Mapee los atributos de productos de PrestaShop (como tamaño, color, material) a los atributos requeridos por Microsoft (por ejemplo, `size`, `color`, `material`).
  - **Etiquetas personalizadas:** Defina hasta 5 etiquetas personalizadas (`custom_label_0` a `custom_label_4`) para segmentar sus productos para estrategias de puja en Microsoft Ads.
  - **Disponibilidad y condición:** Ajustes para definir cómo se exportan la disponibilidad del producto (en stock, agotado, pedido anticipado) y la condición (nuevo, usado, reacondicionado).
  - **GTIN (Número Global de Artículo Comercial):** Ajustes para exportar códigos EAN/UPC como GTIN.
  - **Marca:** Cómo se exportan las marcas de productos.
  - **Descripción:** Opciones para exportar descripciones de productos, a menudo con conversión a texto plano.
  - **Enlaces de imagen:** Cómo se enlazan las imágenes de productos.
  - **Precio y precio de venta:** Cómo se exportan los precios regulares y de venta, incluidas las consideraciones fiscales.
  - **URL de Cron:** La URL única para este feed específico que utilizará para actualizaciones automatizadas.
- **Efecto de los cambios:**
  - Los cambios aquí impactan directamente el contenido y la estructura del archivo de feed de productos generado. Una configuración incorrecta puede llevar a la desaprobación de productos en Microsoft Merchant Center.
  - Un mapeo de categorías adecuado asegura que sus productos aparezcan en las categorías de compras correctas en Bing.
  - Los datos precisos de precios y disponibilidad evitan la frustración del cliente y la desaprobación de anuncios.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Configuración inicial:** Cree un feed para cada combinación de país/idioma objetivo en la que anuncie. Mapee cuidadosamente sus categorías a la taxonomía de Microsoft.
  2. **Revisar atributos:** Asegúrese de que todos los atributos críticos (GTIN, marca, precio, disponibilidad, enlaces de imagen) estén correctamente mapeados y exportados.
  3. **Configurar tareas cron:** Implemente las URL de Cron proporcionadas en su servidor de alojamiento para automatizar la generación diaria (o más frecuente) del feed. Esto es fundamental para mantener sus datos de productos actualizados.
  4. **Monitorear Microsoft Merchant Center:** Revise regularmente su cuenta de Microsoft Merchant Center en busca de desaprobaciones o advertencias de productos, y ajuste la configuración del módulo según sea necesario.
  5. **Actualizaciones de productos:** Al añadir nuevos productos o realizar cambios significativos en los existentes, asegúrese de que su tarea cron esté funcionando, o regenere manualmente el feed si se requiere una actualización inmediata.

#### index.php (mmcfeed/controllers/admin/index.php)

Este controlador probablemente sirve como un panel de control o una vista de gestión general para el módulo dentro del Back Office de PrestaShop.

- **Nombre de la pantalla y ubicación del menú:** Probablemente parte de la sección principal del menú "Microsoft Merchant Center", posiblemente la página de aterrizaje predeterminada.
- **Acciones y configuraciones disponibles:** Esta pantalla probablemente muestra una visión general de sus feeds configurados, su última fecha de generación, estado y enlaces rápidos para editarlos o generarlos. También podría mostrar el estado general del módulo o alertas importantes.
- **Efecto de los cambios:** Esta vista proporciona un vistazo rápido a la configuración de su feed. Las acciones aquí (como hacer clic en "Generar feed") activarán el proceso de generación del feed.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla como un panel de control rápido para monitorear la salud de sus feeds de productos. Si necesita activar manualmente una actualización del feed, aquí es donde lo haría.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Idioma de destino | El idioma principal de su tienda | Determina el idioma para nombres de productos, descripciones, etc. |
|  | Moneda de destino | La moneda principal de su tienda | Establece la moneda para todos los precios en el feed. |
|  | País de destino | Su mercado objetivo principal | Influye en impuestos, envío y reglas específicas del país. |
|  | URL de Cron | Proporcionada por el módulo | Automatiza la generación del feed a intervalos programados. |
| **AdminExportProductsFeedMicrosoftController** | Nombre del feed | Descriptivo (ej., "Francia - FR") | Identifica el feed específico. |
|  | Formato de archivo | CSV, XML o TSV | Elija según los requisitos de Microsoft Merchant Center. |
|  | Mapeo de categorías | Mapear PrestaShop a la taxonomía de Microsoft | Asegura que los productos aparezcan en las categorías de compra correctas. |
|  | Filtrado de productos | Basado en su estrategia | Incluir/excluir productos o categorías específicas. |
|  | Mapeo de atributos | Mapear atributos de PrestaShop a Microsoft | Proporciona información detallada del producto para los anuncios. |
|  | Etiquetas personalizadas (0-4) | Según sea necesario para campañas publicitarias | Segmenta productos para estrategias de puja. |
|  | Exportación GTIN | Habilitado si está disponible | Exporta EAN/UPC para la identificación del producto. |
|  | Fecha de disponibilidad | Habilitado si aplica | Exporta la fecha de disponibilidad del producto para pedidos anticipados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis productos no aparecen en los anuncios de compras de Microsoft. ¿Qué debo verificar?**
R:

1. **Estado de carga del feed:** Primero, revise su cuenta de Microsoft Merchant Center para asegurarse de que su feed se haya cargado y procesado correctamente sin errores importantes.
2. **Desaprobaciones de productos:** Busque cualquier desaprobación de productos en la sección "Diagnósticos" de Microsoft Merchant Center. Esto le indicará exactamente por qué los productos no se muestran. Las razones comunes incluyen GTINs faltantes, enlaces de imagen incorrectos o violaciones de políticas.
3. **Configuración del módulo:** Verifique que la configuración de su módulo (idioma, moneda, país, mapeo de categorías) sea correcta y coincida con la configuración de su cuenta de Microsoft Merchant Center.
4. **Generación del feed:** Asegúrese de que el feed se esté generando correctamente por el módulo. Intente generarlo manualmente y verifique el archivo de salida.
5. **Campañas publicitarias:** Confirme que sus campañas de Microsoft Ads estén activas, correctamente segmentadas y vinculadas al feed de productos correcto.

**P: Los precios o niveles de stock de mis productos están desactualizados en los anuncios de compras de Microsoft.**
R: Esto generalmente significa que su feed de productos no se está actualizando con la suficiente frecuencia.

1. **Tarea Cron:** Asegúrese de que su tarea cron esté configurada correctamente en su servidor de alojamiento y se ejecute con la frecuencia deseada (por ejemplo, diariamente). El módulo proporciona una URL única para esto.
2. **Generación manual:** Si ha realizado cambios urgentes, puede regenerar manualmente el feed desde la página de configuración del módulo y volver a subirlo a Microsoft Merchant Center (si no utiliza recuperaciones programadas).

**P: Algunos de mis productos faltan en el feed.**
R:

1. **Exclusión de categorías:** Verifique si las categorías que contienen estos productos han sido excluidas accidentalmente en la configuración del módulo.
2. **Estado del producto:** Asegúrese de que los productos estén activos, visibles y en stock en su tienda PrestaShop. Los productos marcados como "desactivados" o "agotados" (dependiendo de su configuración) podrían ser excluidos.
3. **Filtros específicos:** Revise cualquier filtro de producto específico que haya aplicado en la configuración del módulo.

**P: ¿Cómo mapeo mis categorías de PrestaShop a la taxonomía de productos de Microsoft?**
R: En la pantalla de configuración del feed del módulo, habrá una sección para "Mapeo de categorías". Normalmente verá una lista de sus categorías de PrestaShop. Para cada una, deberá seleccionar la categoría más apropiada de la lista de taxonomía predefinida de Microsoft. Este es un paso crucial para la relevancia de los anuncios. Tómese su tiempo para hacerlo correctamente.

**P: Mi tema personalizado está causando problemas de visualización con la interfaz de administración del módulo.**
R: Si bien el impacto del módulo en el front-office es nulo, su interfaz de back-office a veces puede entrar en conflicto con temas de administración muy personalizados.

1. **Borrar caché:** Primero, intente borrar la caché de Smarty de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).
2. **Tema predeterminado:** Cambie temporalmente su tema de back-office al tema predeterminado de PrestaShop para ver si el problema persiste. Si se resuelve, el conflicto es con su tema de administración personalizado.
3. **Contactar soporte:** Si el problema continúa, recopile capturas de pantalla y detalles y contacte al soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Microsoft Merchant Center Product Feed` (`mmcfeed`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los Controladores de Administración para la gestión del back-office y los Controladores Frontales para generar el feed de productos a través de tareas cron. No introduce nuevas clases `ObjectModel`, sino que consulta los datos de productos existentes de PrestaShop y los formatea según las especificaciones de Microsoft Merchant Center. El módulo depende en gran medida de los valores de configuración almacenados en `ps_configuration` y utiliza plantillas Smarty para renderizar tanto las interfaces de administración como, potencialmente, partes de la lógica de generación del feed (aunque normalmente los feeds se generan programáticamente).

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `mmcfeed/controllers/front/feed.php`
  - **Nombre de la clase y clase padre:** `MmcfeedFeedModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es el punto final principal para generar el feed de productos. Está diseñado para ser llamado a través de una URL única (la "URL cron") para la generación automatizada del feed. Maneja la lógica de consultar datos de productos, aplicar reglas de filtrado y mapeo definidas en el back office, y generar el feed de productos en el formato especificado (CSV, XML, TSV). Normalmente no renderiza una página visual, sino que genera datos sin procesar.
- `mmcfeed/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `MmcfeedIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es un controlador frontal de marcador de posición o de reserva. En muchos módulos, `index.php` en un directorio de controlador sirve como un punto de entrada predeterminado o simple. Podría redirigir o simplemente devolver una respuesta vacía si no se define ninguna acción específica. Su función funcional directa en la generación del feed es probablemente mínima en comparación con `feed.php`.

#### Controladores de Administración del Back-Office

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Nombre de la pestaña y entidad gestionada:** Gestiona la configuración y generación de feeds de productos individuales de Microsoft Merchant Center. Crea un nuevo elemento de menú en el back office de PrestaShop.
  - **Responsabilidad:** Este controlador maneja las operaciones CRUD para las configuraciones de feeds de productos. Muestra la lista de feeds configurados, permite añadir nuevos feeds, editar los existentes y activar su generación. Procesa los envíos de formularios para definir configuraciones específicas del feed, como el país de destino, el idioma, la moneda, el formato de archivo, el mapeo de categorías, el filtrado de productos y el mapeo de atributos (por ejemplo, `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). Interactúa con `ps_configuration` para almacenar estas configuraciones y orquesta la recuperación y el formato de los datos para el proceso de generación del feed.
- `mmcfeed/controllers/admin/index.php`
  - **Nombre de la pestaña y entidad gestionada:** Probablemente un panel de control o página de resumen para el módulo en el back office de PrestaShop.
  - **Responsabilidad:** Este controlador probablemente sirve como el punto de entrada principal para la interfaz de administración del módulo, proporcionando un resumen de los feeds configurados, su estado y acciones rápidas. Podría renderizar una plantilla similar a un panel de control (`dashboard.tpl`) para dar una visión general de la actividad del módulo.

### 4.3 Clases y modelos principales (`classes/`)

La información proporcionada indica que no hay clases o modelos personalizados dentro del directorio `classes/`. Esto sugiere que el módulo opera principalmente consultando directamente las clases `ObjectModel` principales de PrestaShop como `Product`, `Category`, `Language`, `Currency`, etc., y `ps_configuration` para sus configuraciones. La lógica para el procesamiento de datos y la generación del feed probablemente está encapsulada dentro del archivo principal del módulo `mmcfeed.php` y los controladores de administración/frontales.

### 4.4 Activos JavaScript (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado, probablemente para buscar productos, categorías o atributos dentro de los formularios de configuración del módulo. Esto mejora la experiencia del usuario al mapear categorías o filtrar productos. Se vincula a los campos de entrada y realiza solicitudes AJAX para obtener sugerencias.
- `mmcfeed/views/js/admin-app.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Este es el archivo JavaScript principal para la interfaz de back-office del módulo. Maneja varios elementos interactivos, validaciones de formularios, carga dinámica de contenido (por ejemplo, modales Fancybox para la selección de categorías) y llamadas AJAX relacionadas con el guardado de configuraciones o la activación de la generación del feed. Probablemente vincula oyentes de eventos a botones, selectores y campos de entrada dentro de los formularios del controlador `AdminExportProductsFeedMicrosoft`.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Estilo de formulario de administración del back-office.
  - **Responsabilidad:** Estiliza los desplegables de autocompletado y los campos de entrada utilizados por el script `autocomplete.js`, asegurando una apariencia consistente y fácil de usar dentro del back office de PrestaShop.
- `mmcfeed/views/admin-theme.css`
  - **Alcance:** Estilo de formulario de administración del back-office.
  - **Responsabilidad:** Proporciona ajustes de estilo generales y anulaciones para las páginas del back-office del módulo para integrarse sin problemas con el tema de administración de PrestaShop. Podría definir estilos para el diseño, botones, tablas y elementos de formulario específicos del módulo.
- `mmcfeed/views/css/admin-app.css`
  - **Alcance:** Estilo de formulario de administración del back-office.
  - **Responsabilidad:** Contiene estilos específicos para los componentes de la interfaz de usuario personalizados del módulo y los diseños dentro del panel de administración, como interfaces de mapeo de categorías, listas de exclusión de productos o elementos del panel de control. Funciona en conjunto con `admin-theme.css` para proporcionar la identidad visual del módulo en el back office.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de gancho (`views/templates/hook/`)**: Ninguna listada explícitamente, lo que indica que el módulo no renderiza contenido directamente en ganchos estándar del front-office.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `mmcfeed/views/templates/admin/dashboard.tpl`: Probablemente la plantilla principal del panel de control renderizada por `controllers/admin/index.php`, que proporciona una visión general del módulo y sus feeds configurados.
  - `mmcfeed/views/templates/admin/feeds.tpl`: Probablemente renderiza la lista de feeds de productos gestionados por `AdminExportProductsFeedMicrosoftController`, mostrando su estado, última fecha de generación y acciones.
  - `mmcfeed/views/templates/admin/form-chrome.tpl`: Una plantilla genérica para envolver formularios en la interfaz de administración de PrestaShop, proporcionando un estilo y una estructura consistentes (por ejemplo, encabezado, pie de página, botones de guardar).
  - `mmcfeed/views/templates/admin/layout.tpl`: Una plantilla de diseño base para las páginas de administración del módulo, que define la estructura general, incluidos encabezados, menús y áreas de contenido.
- **Otras plantillas (`views/`)**:
  - `mmcfeed/lib/searchTool/views/scripts.tpl`: Contiene código JavaScript o inclusiones de scripts relacionados con la herramienta de búsqueda/funcionalidad de autocompletado.
  - `mmcfeed/views/categories-fancybox.tpl`: Renderiza el contenido de un modal Fancybox utilizado para la selección o mapeo de categorías, probablemente proporcionando una estructura similar a un árbol para una fácil navegación.
  - `mmcfeed/views/category_taxonomy.tpl`: Una plantilla parcial utilizada dentro de `categories-fancybox.tpl` o el formulario principal de configuración del feed para mostrar y gestionar el mapeo de categorías de PrestaShop a la taxonomía de Microsoft.
  - `mmcfeed/views/exclude-products.tpl`: Renderiza la interfaz para seleccionar y gestionar los productos que se excluirán del feed.
  - `mmcfeed/views/google_lang_links.tpl`: Este nombre de plantilla es curioso para un módulo de Microsoft. Podría ser un remanente de un módulo de Google Merchant Center o un componente genérico para manejar enlaces específicos de idioma, potencialmente para las propias URL del feed.
  - `mmcfeed/views/returnAlert.tpl`: Una plantilla genérica para mostrar mensajes de éxito o error al usuario en el back office.
  - `mmcfeed/views/script-fancybox.tpl`: Contiene código JavaScript o inclusiones de scripts específicamente para la biblioteca Fancybox, utilizada para ventanas emergentes modales.
  - `mmcfeed/views/script.tpl`: Una plantilla de inclusión de script general, potencialmente para variables JavaScript o inicializaciones de todo el módulo.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas según la información proporcionada.
  - Todas las configuraciones del módulo se almacenan en la tabla `ps_configuration`, utilizando claves con el prefijo `mmc_` (por ejemplo, `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - Interactúa con tablas estándar de PrestaShop como `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule`, etc., para recuperar datos de productos.
- **Tabla de ganchos registrados**:
  El módulo utiliza principalmente ganchos de back-office para su interfaz de administración y, potencialmente, ganchos `action` para la lógica interna. Los ganchos de front-office no se utilizan para renderizar contenido, pero el controlador frontal del módulo `feed.php` actúa como un punto final directo para servicios externos (como tareas cron).

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de las páginas del front-office. | *No se utiliza para renderizar contenido.* Si está registrado, probablemente para la carga interna de JS/CSS, pero la función principal del módulo es la generación de feeds, no la visualización en el front-office. |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | *No se utiliza para renderizar contenido.* |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | *No se utiliza para renderizar contenido.* |
| `displayFooter` | En el pie de página de las páginas del front-office. | *No se utiliza para renderizar contenido.* |
| `displayAdminProductsExtra` | En la página de edición de productos en el back office. | *Potencialmente utilizado* para añadir una pestaña o sección para exclusiones o anulaciones de feeds específicos del producto. |
| `actionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y antes de que se carguen sus medios (JS/CSS). | Se utiliza para registrar JavaScript (`admin-app.js`, `autocomplete.js`) y CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) específicos del módulo para la interfaz del back-office. |
| `actionModuleInstall` | Durante la instalación del módulo. | Para crear entradas de configuración en `ps_configuration` y potencialmente registrar pestañas de administración. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para limpiar entradas de configuración y eliminar pestañas de administración. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | *Improbable para este módulo.* Si está presente, sería para rastrear conversiones o actualizar datos del feed basados en ventas, pero no es una función principal para un generador de feeds. |
| `actionProductUpdate` | Después de que un producto ha sido actualizado. | *Potencialmente utilizado* para activar una bandera para la regeneración del feed o para actualizar cachés internos si el módulo mantiene alguno. |
| `actionProductAdd` | Después de que se ha añadido un nuevo producto. | *Potencialmente utilizado* para activar una bandera para la regeneración del feed o para actualizar cachés internos. |
| `displayAdminNavBarBefore` | Antes de la barra de navegación principal en el back office. | *Potencialmente utilizado* para añadir un enlace rápido o una notificación relacionada con el módulo. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu proporciona soporte dedicado para todos los módulos comprados, asegurando que su tienda permanezca actualizada y funcional.
"""
