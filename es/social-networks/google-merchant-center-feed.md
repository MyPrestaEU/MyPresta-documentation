---
title: "Google merchant center feed - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Google merchant center feed de MyPresta.eu."
sidebar:
  label: "Google merchant center feed - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google merchant center feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-merchant-center-feed/)
>
> ---


# Google merchant center feed

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Pueden ser necesarios recursos de servidor suficientes (CPU, RAM) para generar feeds de productos muy grandes, especialmente para tiendas con decenas de miles de productos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de Módulos.

-   **Qué hace este ajuste:** Esta opción controla si se muestra un selector de árbol de categorías en la pantalla de exportación de productos, lo que le permite incluir o excluir productos según su categoría.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (marcado):* En la pantalla de exportación de productos (AdminExportProductsFeedGoogle), verá un árbol visual de las categorías de su tienda. Esto le permite seleccionar fácilmente qué categorías de productos deben incluirse o excluirse de su feed de Google Merchant Center. Esto es crucial para filtrar su feed y que solo incluya productos relevantes o para excluir categorías específicas que no desea anunciar en Google.
    -   *Cuando está deshabilitado (desmarcado):* El selector de árbol de categorías no aparecerá en la pantalla de exportación. Esto significa que no podrá filtrar productos por categoría directamente dentro de la interfaz del módulo. Entonces exportaría todos los productos, o dependería de otras opciones de filtrado si están disponibles (por ejemplo, exclusiones específicas de productos).
-   **Valor recomendado:** **SÍ (marcado)**.
-   **Escenario / ejemplo de comerciante:** Usted vende tanto ropa como descargas digitales. Solo desea anunciar sus productos de ropa en Google Shopping. Al habilitar "Mostrar árbol de categorías", puede seleccionar fácilmente solo sus categorías de "Ropa" para incluirlas en el feed, excluyendo su categoría de "Descargas Digitales".

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminExportProductsFeedGoogleController (Back Office > Módulos > Google merchant center feed > Exportar Feed de Productos)

Esta es la pantalla principal donde generará y gestionará sus feeds de productos de Google Merchant Center. Se accede a ella navegando a **Módulos > Gestor de Módulos**, buscando "Google merchant center feed" y luego haciendo clic en el enlace "Exportar Feed de Productos" (o similar, dependiendo de la versión de PrestaShop, podría ser un elemento de submenú bajo la entrada principal del módulo).

Esta pantalla le permite definir el contenido y el formato de su feed de productos.

**Acciones y ajustes disponibles:**

La pantalla presenta un formulario con varios campos correspondientes a los atributos requeridos por Google Merchant Center. Los rellenará para personalizar su feed.

-   **ID:**
    -   **Propósito:** Este es el identificador único para cada producto en su feed. Google lo utiliza para hacer coincidir su producto con sus datos.
    -   **Efecto de los cambios:** Asegura que cada producto tenga un ID distinto, lo cual es crítico para que Google procese correctamente su feed.
    -   **Valor recomendado:** Generalmente se asigna al ID interno o referencia de su producto.
-   **GTIN (Número Global de Artículo Comercial):**
    -   **Propósito:** Los Números Globales de Artículo Comercial (como EAN, UPC, ISBN) son identificadores de producto únicos utilizados globalmente. Google los requiere para la mayoría de los productos.
    -   **Efecto de los cambios:** Incluir GTINs correctos ayuda a Google a identificar sus productos con precisión, mejorando la visibilidad y la confianza. Los GTINs faltantes o incorrectos pueden llevar a la desaprobación de productos.
    -   **Valor recomendado:** Asignar al campo EAN/UPC de su producto.
-   **Identifier\_exists:**
    -   **Propósito:** Indica si existe un identificador de producto único (como GTIN, Marca, MPN) para el producto.
    -   **Efecto de los cambios:** Si vende productos personalizados o productos sin identificadores estándar, establecer esto en 'no' (o 'false') puede evitar desaprobaciones. Para la mayoría de los productos estándar, debería ser 'sí'.
    -   **Valor recomendado:** Generalmente 'sí' si se proporcionan GTINs.
-   **Title:**
    -   **Propósito:** El nombre de su producto tal como aparecerá en Google Shopping. Este es un campo crucial para atraer clics.
    -   **Efecto de los cambios:** Un título claro y descriptivo con palabras clave relevantes mejora la visibilidad en la búsqueda y las tasas de clics.
    -   **Valor recomendado:** El nombre de su producto, potencialmente mejorado con atributos clave (por ejemplo, "Camiseta Roja - Talla M - Algodón").
-   **Availability:**
    -   **Propósito:** Indica si el producto está en stock, agotado o disponible para pre-pedido.
    -   **Efecto de los cambios:** La disponibilidad precisa evita que los clientes hagan clic en artículos agotados, mejorando la experiencia del usuario y reduciendo el gasto publicitario desperdiciado.
    -   **Valor recomendado:** Se extrae automáticamente del estado de stock de su producto.
-   **Availability\_date:**
    -   **Propósito:** La fecha en que un producto pre-pedido estará disponible.
    -   **Efecto de los cambios:** Proporciona transparencia a los clientes interesados en artículos de pre-pedido.
    -   **Valor recomendado:** Establecer si ofrece pre-pedidos.
-   **Inventory:**
    -   **Propósito:** La cantidad de producto actualmente en stock.
    -   **Efecto de los cambios:** Mantiene sus listados de Google sincronizados con sus niveles de stock reales, evitando la sobreventa.
    -   **Valor recomendado:** Se extrae automáticamente de la cantidad de stock de su producto.
-   **Brand:**
    -   **Propósito:** El nombre de la marca de su producto.
    -   **Efecto de los cambios:** Ayuda a los clientes a identificar marcas conocidas y mejora la categorización de productos en Google.
    -   **Valor recomendado:** La marca/fabricante de su producto.
-   **Link:**
    -   **Propósito:** La URL directa a la página de su producto en su tienda.
    -   **Efecto de los cambios:** Esencial para dirigir a los clientes de Google a su sitio web.
    -   **Valor recomendado:** La URL canónica de su producto.
-   **Image link:**
    -   **Propósito:** La URL de la imagen principal de su producto.
    -   **Efecto de los cambios:** Las imágenes claras y de alta calidad son fundamentales para atraer clics en Google Shopping.
    -   **Valor recomendado:** La URL de la imagen principal de su producto.
-   **Additional\_image\_link:**
    -   **Propósito:** URLs para imágenes adicionales de su producto.
    -   **Efecto de los cambios:** Proporciona más información visual a los clientes potenciales, ayudándoles a tomar decisiones de compra.
    -   **Valor recomendado:** URLs de imágenes secundarias del producto.
-   **Item subtitle:**
    -   **Propósito:** Una descripción opcional más corta o un detalle adicional para el producto.
    -   **Efecto de los cambios:** Se puede utilizar para resaltar características clave o promociones.
    -   **Valor recomendado:** Opcional, usar para detalles cortos e impactantes.
-   **Description:**
    -   **Propósito:** Una descripción detallada de su producto.
    -   **Efecto de los cambios:** Proporciona información completa a los clientes y ayuda a Google a comprender la relevancia de su producto.
    -   **Valor recomendado:** La descripción completa de su producto.
-   **Product\_type:**
    -   **Propósito:** Su propia categorización del producto dentro de su tienda.
    -   **Efecto de los cambios:** Ayuda a Google a comprender su jerarquía de productos y se puede utilizar para la segmentación de campañas.
    -   **Valor recomendado:** Su ruta de categoría interna (por ejemplo, "Ropa > Camisetas > Camisetas de Hombre").
-   **Condition:**
    -   **Propósito:** La condición del producto (por ejemplo, nuevo, usado, reacondicionado).
    -   **Efecto de los cambios:** La información precisa sobre la condición es vital para la confianza del cliente y las políticas de Google.
    -   **Valor recomendado:** Generalmente 'nuevo' para la mayoría de las tiendas de comercio electrónico.
-   **Price:**
    -   **Propósito:** El precio de venta actual de su producto.
    -   **Efecto de los cambios:** La precisión de los precios es primordial. Las discrepancias entre su feed y su sitio web pueden llevar a desaprobaciones.
    -   **Valor recomendado:** El precio actual de su producto.
-   **Sale Price:**
    -   **Propósito:** El precio con descuento de su producto si está en oferta.
    -   **Efecto de los cambios:** Destaca las promociones y atrae a los clientes que buscan ofertas.
    -   **Valor recomendado:** El precio específico de su producto.
-   **Tax rate:**
    -   **Propósito:** La tasa de impuestos aplicable al producto.
    -   **Efecto de los cambios:** Asegura información de precios precisa, especialmente para regiones donde el impuesto se calcula al finalizar la compra.
    -   **Valor recomendado:** La tasa de impuestos aplicable de su tienda.
-   **Contextual keywords:**
    -   **Propósito:** Palabras clave adicionales para ayudar a Google a comprender su producto.
    -   **Efecto de los cambios:** Puede mejorar la relevancia de su producto en los resultados de búsqueda.
    -   **Valor recomendado:** Términos de búsqueda relevantes que no estén ya en el título o la descripción.
-   **Google product category:**
    -   **Propósito:** La categorización estandarizada de productos de Google. Este es un campo crítico para que Google entienda lo que está vendiendo.
    -   **Efecto de los cambios:** Categorizar correctamente sus productos según la taxonomía de Google mejora la visibilidad y asegura que sus productos aparezcan en búsquedas relevantes. Las categorías incorrectas pueden llevar a desaprobaciones.
    -   **Valor recomendado:** Seleccione la Categoría de Producto de Google más específica que se aplique a su producto.

**Otros ajustes y opciones:**

-   **Export Size Attribute:**
    -   **Propósito:** Determina si los atributos de tamaño del producto deben incluirse en el feed, lo cual es importante para la ropa y otros productos dependientes del tamaño.
    -   **Efecto de los cambios:**
        -   *Cuando está habilitado:* Los tamaños de los productos (por ejemplo, S, M, L) se exportarán, permitiendo a Google mostrar información de tamaño y opciones de filtro.
        -   *Cuando está deshabilitado:* La información de tamaño no se incluirá.
    -   **Valor recomendado:** **SÍ** para tiendas de ropa/prendas, **NO** para otros tipos de productos.
-   **Export Exclude Categories:**
    -   **Propósito:** Le permite seleccionar categorías específicas cuyos productos deben ser *excluidos* del feed. Esto funciona en conjunto con el ajuste "Mostrar árbol de categorías" de la configuración principal.
    -   **Efecto de los cambios:** Los productos que pertenecen a las categorías seleccionadas no aparecerán en el feed generado.
    -   **Valor recomendado:** Utilice esto para filtrar productos que no desea anunciar en Google (por ejemplo, categorías agotadas, servicios o productos con bajos márgenes).
-   **Export Availability Date:**
    -   **Propósito:** Controla si el atributo `availability_date` se incluye en el feed.
    -   **Efecto de los cambios:**
        -   *Cuando está habilitado:* Se incluirá la fecha en que un producto estará disponible (para pre-pedidos).
        -   *Cuando está deshabilitado:* Esta información se omitirá.
    -   **Valor recomendado:** **SÍ** si utiliza la funcionalidad de pre-pedido de PrestaShop y desea comunicar las fechas de disponibilidad a Google.
-   **Generate Feed Button:**
    -   **Propósito:** Inicia el proceso de generación del feed de productos XML/CSV basado en todas sus opciones seleccionadas.
    -   **Efecto de los cambios:** Crea el archivo de feed, que luego puede descargar o proporcionar la URL a Google Merchant Center para las recuperaciones programadas.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Configuración inicial:** Asigne cuidadosamente todos los atributos de Google Merchant Center a los campos de producto de su PrestaShop. Preste especial atención a GTIN, Marca y Categoría de producto de Google.
2.  **Filtrado de categorías:** Utilice la opción "Exportar Excluir Categorías" para ajustar qué productos se envían a Google.
3.  **Generar y probar:** Genere un feed y súbalo a Google Merchant Center. Supervise si hay errores o advertencias en su cuenta de Google Merchant Center.
4.  **Recuperaciones programadas:** Una vez que su feed sea aprobado, configure una recuperación programada en Google Merchant Center utilizando la URL proporcionada por el módulo. Esto asegura que Google siempre tenga los datos de producto más recientes.
5.  **Revisión regular:** Revise periódicamente los diagnósticos de su Google Merchant Center para detectar desaprobaciones o advertencias, y ajuste la configuración de su módulo o los datos de producto en PrestaShop en consecuencia.

#### index.php (gmfeed/controllers/admin/index.php)

Este archivo probablemente sirve como un marcador de posición o una redirección dentro de la estructura del controlador de administración del módulo y no representa una pantalla distinta y configurable para el comerciante. La configuración y gestión principal se realiza a través de `AdminExportProductsFeedGoogleController`.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Mostrar árbol de categorías | SÍ | Habilita el filtrado de categorías en la pantalla de exportación para una selección precisa de productos. |
| **AdminExportProductsFeedGoogle** | ID | ID de Producto | Identificador único para cada producto en el feed. |
| | GTIN | EAN/UPC del Producto | Número Global de Artículo Comercial para la identificación del producto. |
| | Identifier\_exists | Sí | Indica si existen identificadores únicos. |
| | Title | Nombre del Producto | Título del producto para Google Shopping. |
| | Availability | Detección automática | Estado de stock del producto (en stock, agotado). |
| | Availability\_date | Detección automática | Fecha de disponibilidad para pre-pedidos. |
| | Inventory | Detección automática | Cantidad de stock actual. |
| | Brand | Fabricante del Producto | Nombre de la marca del producto. |
| | Link | URL del Producto | Enlace directo a la página del producto. |
| | Image link | URL de la Imagen Principal del Producto | URL de la imagen principal del producto. |
| | Additional\_image\_link | URLs de Imágenes Secundarias del Producto | URLs de imágenes adicionales del producto. |
| | Item subtitle | Opcional | Detalle corto y adicional del producto. |
| | Description | Descripción del Producto | Descripción detallada del producto. |
| | Product\_type | Su Ruta de Categoría | Su categorización interna del producto. |
| | Condition | Nuevo | Condición del producto (nuevo, usado, reacondicionado). |
| | Price | Precio del Producto | Precio de venta actual. |
| | Sale Price | Precio Específico del Producto | Precio con descuento si está en oferta. |
| | Tax rate | Tasa de Impuestos de la Tienda | Tasa de impuestos aplicable. |
| | Contextual keywords | Opcional | Palabras clave adicionales para la relevancia del producto. |
| | Google product category | Seleccionar de la Taxonomía de Google | Categoría de producto estandarizada de Google. |
| | Export Size Attribute | SÍ (para ropa) | Incluye atributos de tamaño del producto en el feed. |
| | Export Exclude Categories | Seleccionar según sea necesario | Excluye productos de categorías seleccionadas. |
| | Export Availability Date | SÍ (para pre-pedidos) | Incluye el atributo `availability_date`. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis productos no aparecen en Google Shopping, o estoy recibiendo desaprobaciones. ¿Qué debo verificar primero?**
R1:

-   **Cuenta de Google Merchant Center (GMC):** Inicie sesión en su cuenta de GMC y verifique la sección "Diagnóstico". Aquí es donde Google informa errores o advertencias específicos para sus productos y feed.
-   **Procesamiento del feed:** Asegúrese de que su feed haya sido procesado con éxito por Google. Verifique la sección "Feeds" en GMC.
-   **Atributos requeridos:** Verifique que todos los atributos obligatorios de Google (ID, Título, Enlace, Enlace de imagen, Precio, Descripción, GTIN/Marca/MPN, Disponibilidad, Categoría de producto de Google) estén correctamente asignados y completados en la configuración de exportación del módulo.
-   **Discrepancias de datos:** Google es muy estricto con la coincidencia de precios y disponibilidad entre su feed y su sitio web. Asegúrese de que los datos de sus productos de PrestaShop sean precisos y de que Google esté obteniendo el feed más reciente.
-   **Categoría de producto de Google:** Asegúrese de haber seleccionado la Categoría de producto de Google más precisa para sus productos.

**P2: He realizado cambios en mis productos en PrestaShop, pero no se están actualizando en Google Shopping.**
R2:

-   **Generar nuevo feed:** Después de realizar cambios en PrestaShop, debe generar un nuevo feed utilizando el botón "Generar feed" del módulo.
-   **Recuperación programada de Google:** Google Merchant Center necesita obtener este feed actualizado. Si tiene una recuperación programada configurada, se actualizará automáticamente en el siguiente horario programado. También puede activar manualmente una recuperación en su cuenta de Google Merchant Center en "Feeds" > "Obtener ahora".
-   **Caché:** Borre la caché de Smarty de su PrestaShop (Parámetros avanzados > Rendimiento) y la caché del navegador para asegurarse de que está viendo la última versión de la configuración del módulo y del feed generado.

**P3: ¿Cómo excluyo ciertos productos o categorías del feed de Google?**
R3:

-   En la pantalla de configuración principal del módulo, asegúrese de que "Mostrar árbol de categorías" esté habilitado.
-   Luego, en la pantalla `AdminExportProductsFeedGoogle`, use la opción "Exportar Excluir Categorías". Verá un árbol de sus categorías. Seleccione las categorías cuyos productos desea excluir del feed.
-   Genere un nuevo feed después de realizar estas selecciones.

**P4: El proceso de generación del feed tarda mucho tiempo o se agota el tiempo de espera para mi tienda grande.**
R4:

-   **Recursos del servidor:** La generación de feeds grandes puede consumir muchos recursos. Póngase en contacto con su proveedor de alojamiento para asegurarse de que su servidor tenga suficiente límite de memoria PHP, tiempo de ejecución y recursos de CPU.
-   **Configuración de PHP:** Aumente `max_execution_time` y `memory_limit` en su archivo `php.ini` (o a través de su panel de control de alojamiento).
-   **Filtrar productos:** Si es posible, intente segmentar su feed excluyendo categorías o productos menos importantes para reducir el tamaño del feed.
-   **Actualizaciones del módulo:** Asegúrese de estar ejecutando la última versión del módulo, ya que las mejoras de rendimiento a menudo se incluyen en las actualizaciones.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo `Google merchant center feed` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los controladores del Back-Office para la configuración y la generación del feed. Utiliza un controlador frontal para exponer la URL del feed generado para las recuperaciones programadas de Google. El módulo no extiende `ObjectModel` para tablas de base de datos personalizadas, sino que se basa en la clase `Configuration` de PrestaShop para la configuración. Integra una biblioteca de herramientas de búsqueda de terceros para la funcionalidad de autocompletado.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `controllers/front/feed.php`
    -   **Nombre de la clase:** `GmfeedFeedModuleFrontController`
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador es responsable de servir el feed de productos XML/CSV generado a Google Merchant Center. Cuando Google realiza una recuperación programada, accede a una URL manejada por este controlador. El controlador recupera los datos del feed generado más recientemente y los envía, típicamente con los encabezados apropiados para la descarga de archivos o la visualización directa.
-   `controllers/front/index.php`
    -   **Nombre de la clase:** `GmfeedIndexModuleFrontController`
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Es probable que sea un marcador de posición o un controlador frontal predeterminado que podría redirigir o simplemente mostrar una página en blanco. No parece tener un papel funcional directo en la generación o visualización del feed según la información proporcionada.

#### Controladores de administración del Back-Office

-   `controllers/admin/AdminExportProductsFeedGoogle.php`
    -   **Nombre de la clase:** `AdminExportProductsFeedGoogleController`
    -   **Clase padre:** `ModuleAdminController`
    -   **Nombre de la pestaña:** "Exportar Feed de Productos" (o similar, vinculado desde la configuración principal del módulo)
    -   **Entidad gestionada:** Generación de feed de productos.
    -   **Responsabilidad:** Este es el controlador de administración principal para gestionar y generar el feed de Google Merchant Center. Maneja la visualización del formulario de configuración para los atributos del feed (GTIN, Título, Precio, etc.), procesa los envíos del formulario y activa la lógica de generación del feed. Interactúa con los datos de productos, categorías y atributos de PrestaShop para compilar el feed. También gestiona la exclusión de categorías (`gm_export_exclude_categories`) y otras configuraciones específicas del feed.
-   `controllers/admin/index.php`
    -   **Nombre de la clase:** `GmfeedIndexModuleAdminController`
    -   **Clase padre:** `ModuleAdminController`
    -   **Nombre de la pestaña:** (Probablemente no sea una pestaña directa, sino parte del enrutamiento interno del módulo)
    -   **Responsabilidad:** Similar a su contraparte del front-office, es probable que sea un marcador de posición o un controlador de administración predeterminado. No parece gestionar una entidad específica ni proporcionar una interfaz de usuario distinta.

### 4.3 Clases y modelos principales (`classes/`)

La información proporcionada indica que no hay clases o modelos personalizados dentro del directorio `classes/`. Es probable que el módulo realice sus operaciones directamente dentro del archivo principal del módulo (`gmfeed.php`) y sus controladores, aprovechando las clases `ObjectModel` existentes de PrestaShop (como `Product`, `Category`, `Manufacturer`, `AttributeGroup`, `Attribute`) y la clase `Configuration` para la configuración.

### 4.4 Activos de JavaScript (`views/js/`)

-   `gmfeed/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Este script es parte de una biblioteca de herramientas de búsqueda, probablemente utilizada para la funcionalidad de autocompletado dentro de los formularios de configuración de administración, como la selección de categorías de productos de Google o la exclusión de productos/categorías específicos. Se vincularía a los campos de entrada, realizaría solicitudes AJAX a un punto final de backend (posiblemente manejado por uno de los controladores de administración) para obtener sugerencias y mostrarlas al usuario.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `gmfeed/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Proporciona estilo para las sugerencias de autocompletado y los campos de entrada, asegurando una apariencia consistente y fácil de usar para la herramienta de búsqueda dentro de la interfaz de administración del módulo.
    -   **Selectores CSS clave:** Probablemente incluye clases para el contenedor de autocompletado, la lista de sugerencias, la sugerencia activa y el campo de entrada.
-   `gmfeed/views/admin-theme.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Detalles:** Contiene reglas de estilo generales específicas para las páginas de configuración del módulo en el Back Office de PrestaShop. Esto podría incluir ajustes de diseño, estilo de botones, estilo de elementos de formulario o señales visuales específicas para la interfaz del módulo.
    -   **Selectores CSS clave:** IDs o clases de contenedor específicos del módulo, clases de elementos de formulario.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

El dossier del módulo indica `actionAdminControllerSetMedia` como un gancho de front-office, lo cual es inusual ya que es un gancho de administración. Es más probable que el módulo use `actionAdminControllerSetMedia` para cargar sus activos JS/CSS en el back office, y las plantillas que se enumeran a continuación se renderizan dentro del contexto de administración.

#### Plantillas de administración (`views/templates/admin/`)

-   `gmfeed/lib/searchTool/views/scripts.tpl`
    -   **Propósito:** Probablemente incluye código JavaScript o inicializa la funcionalidad de autocompletado. Esta plantilla se renderizaría en el Back Office para configurar la herramienta de búsqueda.
-   `gmfeed/views/categories-fancybox.tpl`
    -   **Propósito:** Esta plantilla se utiliza para mostrar el árbol de categorías para la selección/exclusión, probablemente dentro de una ventana emergente Fancybox (o similar). Renderizaría la lista jerárquica de categorías.
-   `gmfeed/views/exclude-products.tpl`
    -   **Propósito:** Esta plantilla mostraría la interfaz para seleccionar productos a excluir del feed, potencialmente utilizando la herramienta de búsqueda y el árbol de categorías.
-   `gmfeed/views/google_lang_links.tpl`
    -   **Propósito:** Esta plantilla podría usarse para mostrar enlaces o información relacionada con Google Merchant Center para diferentes idiomas, posiblemente guiando al comerciante a configurar feeds para varios idiomas de la tienda.
-   `gmfeed/views/returnAlert.tpl`
    -   **Propósito:** Una plantilla genérica para mostrar alertas o mensajes al usuario en el Back Office, como mensajes de éxito después de la generación del feed o notificaciones de error.
-   `gmfeed/views/script-fancybox.tpl`
    -   **Propósito:** Esta plantilla probablemente contiene código JavaScript para inicializar y configurar la biblioteca Fancybox (o similar), utilizada para mostrar ventanas emergentes como el árbol de categorías.
-   `gmfeed/views/script.tpl`
    -   **Propósito:** Una plantilla de script general para el Back Office del módulo, que potencialmente contiene varias funcionalidades JavaScript, oyentes de eventos o llamadas AJAX relacionadas con el proceso de configuración y generación del feed.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:

    -   El módulo no parece crear tablas SQL personalizadas según la información proporcionada (no hay `classes/` con `ObjectModel` o archivos SQL de `install/uninstall`).
    -   La configuración (por ejemplo, `pf_tree`, `gm_export_size_attribute`, `gm_export_exclude_categories`, `gm_export_availability_date`) se almacena en la tabla `ps_configuration`. El valor de `gm_export_exclude_categories` probablemente sería un array serializado de IDs de categoría.
-   **Tabla de ganchos registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se inicializa un controlador de administración y se están configurando sus medios (JS/CSS). | Utilizado por el módulo para cargar sus archivos JavaScript y CSS específicos (por ejemplo, `autocomplete.js`, `admin-theme.css`) en el Back Office para sus pantallas de configuración. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Google merchant center feed", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo y su integración con su tienda PrestaShop.
