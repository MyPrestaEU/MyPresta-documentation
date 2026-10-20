---
title: "Feed de productos de Pinterest - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Feed de productos de Pinterest' de MyPresta.eu."
sidebar:
  label: "Feed de productos de Pinterest - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Pinterest products feed en MyPresta.eu](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/pinterest-products-feed/)
>
> ---


# Feed de productos de Pinterest

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y garantizan el buen funcionamiento de los módulos. Su entorno de alojamiento también debe permitir suficiente memoria y tiempo de ejecución para generar feeds de productos grandes, especialmente si tiene muchos productos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Feed de productos de Pinterest" tiene una pantalla de configuración principal y una pantalla de administración dedicada para gestionar sus feeds de productos.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Configurar Feed de productos de Pinterest)

Esta es la pantalla de configuración principal donde define los parámetros centrales para su feed de productos de Pinterest.

#### Pestaña de Configuración General

Esta pestaña contiene los ajustes fundamentales para generar su feed de productos.

-   **Activar Feed de Pinterest:**

    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo generará el feed de productos y lo hará accesible a través de una URL.
        -   *Cuando está desactivado (NO):* El módulo no generará ni actualizará el feed, y la URL del feed se volverá inactiva.
    -   **Valor recomendado:** SÍ (una vez que haya configurado otros ajustes).
    -   **Escenario / ejemplo del comerciante:** Está listo para comenzar a vender en Pinterest, por lo que lo activa después de configurar sus filtros de productos.
-   **Tipo de archivo de feed:**

    -   **Qué hace este ajuste:** Determina el formato del archivo del feed de productos. Pinterest admite tanto CSV (valores separados por comas) como XML (lenguaje de marcado extensible).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en CSV:* El feed será un archivo de texto plano con datos de productos separados por comas.
        -   *Cuando se establece en XML:* El feed será un archivo estructurado que utiliza etiquetas XML.
    -   **Valor recomendado:** XML (generalmente más robusto para datos complejos, pero ambos funcionan con Pinterest).
    -   **Escenario / ejemplo del comerciante:** Pinterest a menudo recomienda XML para datos más ricos, por lo que podría elegir XML para una mejor compatibilidad y preparación para el futuro.
-   **Idioma predeterminado para el feed:**

    -   **Qué hace este ajuste:** Selecciona el idioma en el que se exportarán los nombres de productos, descripciones y otros datos textuales en el feed.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en inglés:* Todo el texto del producto estará en inglés.
        -   *Cuando se establece en francés:* Todo el texto del producto estará en francés.
    -   **Valor recomendado:** El idioma principal de su público objetivo en Pinterest.
    -   **Escenario / ejemplo del comerciante:** Si se dirige a clientes en Francia, seleccionaría francés. Si se dirige a una audiencia global de habla inglesa, seleccionaría inglés.
-   **Moneda predeterminada para el feed:**

    -   **Qué hace este ajuste:** Selecciona la moneda en la que se exportarán los precios de los productos en el feed.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en USD:* Todos los precios estarán en dólares estadounidenses.
        -   *Cuando se establece en EUR:* Todos los precios estarán en euros.
    -   **Valor recomendado:** La moneda principal de su mercado objetivo en Pinterest.
    -   **Escenario / ejemplo del comerciante:** Si su mercado principal utiliza euros, configúrelo en EUR para garantizar una visualización correcta de los precios en Pinterest.
-   **País predeterminado para el feed:**

    -   **Qué hace este ajuste:** Selecciona el país asociado con sus productos en el feed. Esto puede influir en los cálculos de envío e impuestos por parte de Pinterest.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en Estados Unidos:* Los productos se asocian con el mercado estadounidense.
        -   *Cuando se establece en Francia:* Los productos se asocian con el mercado francés.
    -   **Valor recomendado:** Su país principal de operación o mercado objetivo.
    -   **Escenario / ejemplo del comerciante:** Si su negocio tiene su sede en Alemania y vende principalmente a clientes alemanes, seleccionaría Alemania.
-   **Transportista predeterminado para el feed:**

    -   **Qué hace este ajuste:** Especifica el transportista de envío predeterminado que se asociará con los productos en el feed. Pinterest puede usar esto para estimar los costos de envío.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Mi transportista":* Pinterest podría usar las reglas generales de envío de este transportista (si están disponibles) para la visualización.
    -   **Valor recomendado:** Su transportista de envío más utilizado o predeterminado.
    -   **Escenario / ejemplo del comerciante:** Si la mayoría de sus envíos son con FedEx, seleccionaría FedEx aquí.
-   **Incluir combinaciones de productos (variaciones):**

    -   **Qué hace este ajuste:** Determina si las variaciones individuales de productos (como diferentes tallas o colores de una camiseta) se incluyen como elementos separados en el feed.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Cada combinación (por ejemplo, "Camiseta Roja - Pequeña", "Camiseta Roja - Mediana") será una entrada distinta en el feed.
        -   *Cuando está desactivado (NO):* Solo se incluirá el producto principal, sin variaciones individuales.
    -   **Valor recomendado:** SÍ (si desea que los clientes vean y hagan clic en variaciones específicas en Pinterest).
    -   **Escenario / ejemplo del comerciante:** Vende camisetas en varias tallas y colores. Habilitar esto asegura que cada combinación única de talla/color obtenga su propio pin en Pinterest, permitiendo a los clientes encontrar exactamente lo que buscan.
-   **Exportar productos con atributo específico (por ejemplo, Talla):**

    -   **Qué hace este ajuste:** Le permite especificar un atributo particular (como "Talla" o "Color") que debe incluirse en el feed de productos, a menudo utilizado para datos de productos enriquecidos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona (por ejemplo, "Talla"):* El atributo de talla de sus productos se incluirá explícitamente en los datos del feed.
        -   *Cuando no se selecciona:* Este atributo específico no se exportará explícitamente.
    -   **Valor recomendado:** Seleccione un atributo que sea crucial para la diferenciación del producto, como "Talla" o "Color".
    -   **Escenario / ejemplo del comerciante:** Si vende ropa, seleccionar "Talla" asegura que Pinterest pueda mostrar la información de talla directamente en el pin, mejorando la experiencia de compra.
-   **Exportar productos con característica específica (por ejemplo, Material):**

    -   **Qué hace este ajuste:** Similar a los atributos, esto le permite incluir una característica específica del producto (como "Material" o "Marca") en el feed.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona (por ejemplo, "Material"):* La característica de material de sus productos se incluirá explícitamente en los datos del feed.
        -   *Cuando no se selecciona:* Esta característica específica no se exportará explícitamente.
    -   **Valor recomendado:** Seleccione una característica que agregue información valiosa para los compradores, como "Material", "Marca" o "Estilo".
    -   **Escenario / ejemplo del comerciante:** Si vende muebles, seleccionar "Material" (por ejemplo, "Roble", "Pino") ayuda a los clientes a filtrar y encontrar productos según sus preferencias.
-   **Exportar productos con etiqueta personalizada específica (por ejemplo, Más vendido):**

    -   **Qué hace este ajuste:** Le permite incluir una etiqueta personalizada (si las ha definido en PrestaShop) en el feed. Estas se pueden usar para campañas de marketing específicas en Pinterest.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se selecciona (por ejemplo, "Más vendido"):* Los productos con esta etiqueta personalizada la tendrán incluida en sus datos de feed.
        -   *Cuando no se selecciona:* Las etiquetas personalizadas no se exportarán.
    -   **Valor recomendado:** Úselo si tiene etiquetas específicas para marketing o categorización en Pinterest.
    -   **Escenario / ejemplo del comerciante:** Ha marcado ciertos productos como "Más vendidos" en PrestaShop. Exportar esta etiqueta le permite crear campañas publicitarias de Pinterest dirigidas específicamente a estos productos de alto rendimiento.
-   **Excluir productos por categoría:**

    -   **Qué hace este ajuste:** Proporciona un selector en forma de árbol para elegir categorías completas de productos que NO desea incluir en su feed de Pinterest.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan categorías:* Todos los productos dentro de esas categorías (y sus subcategorías) se excluirán del feed generado.
        -   *Cuando no se seleccionan categorías:* Todos los productos de todas las categorías se considerarán para la exportación (a menos que se excluyan por otros ajustes).
    -   **Valor recomendado:** Excluya categorías que no sean adecuadas para Pinterest (por ejemplo, servicios, descargas digitales o productos que no desea anunciar).
    -   **Escenario / ejemplo del comerciante:** Vende tanto productos físicos como tarjetas de regalo digitales. Excluiría la categoría "Tarjetas de regalo digitales" del feed, ya que Pinterest es principalmente para productos físicos.
-   **Excluir productos específicos:**

    -   **Qué hace este ajuste:** Le permite buscar y seleccionar productos individuales que desea excluir explícitamente del feed de Pinterest.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan productos:* Esos productos específicos no aparecerán en el feed generado.
        -   *Cuando no se seleccionan productos:* Todos los productos (no excluidos por categoría) se considerarán para la exportación.
    -   **Valor recomendado:** Excluya productos específicos que estén agotados indefinidamente, descontinuados o por cualquier otra razón por la que no los quiera en Pinterest.
    -   **Escenario / ejemplo del comerciante:** Un producto en particular no está disponible temporalmente debido a un problema con el proveedor, por lo que lo excluye hasta que vuelva a estar en stock.
-   **Generar URL del feed:**

    -   **Qué hace este ajuste:** Muestra la URL única donde se puede acceder a su feed de productos de Pinterest. Esta es la URL que proporcionará a Pinterest.
    -   **Efecto de cambiar este ajuste:** Este es un campo de solo visualización. La URL cambia si cambia el dominio de su tienda o la configuración SSL.
    -   **Valor recomendado:** Copie esta URL y péguela en la configuración de su cuenta de empresa de Pinterest al configurar su catálogo de productos.
    -   **Escenario / ejemplo del comerciante:** Después de configurar todos los ajustes, copia esta URL y va a su cuenta de empresa de Pinterest para configurar su catálogo de productos, pegando esta URL en el campo "Fuente de datos".
-   **Generar feed (Botón):**

    -   **Qué hace este ajuste:** Activa manualmente la generación del archivo del feed de productos.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se creará o actualizará inmediatamente el archivo del feed según su configuración actual. Esto puede llevar algún tiempo para catálogos grandes.
    -   **Valor recomendado:** Haga clic en esto después de realizar cualquier cambio en la configuración de su feed o cuando desee forzar una actualización inmediata.
    -   **Escenario / ejemplo del comerciante:** Acaba de agregar 50 productos nuevos y desea que aparezcan en Pinterest lo antes posible, por lo que hace clic en "Generar feed".

#### Pestaña de Configuración de Tareas Programadas (Cron Job)

Esta pestaña proporciona información para automatizar el proceso de generación del feed.

-   **URL de la tarea programada (Cron Job):**

    -   **Qué hace este ajuste:** Muestra una URL especial que, al visitarse, activa automáticamente el proceso de generación del feed sin que tenga que hacer clic en el botón "Generar feed" en el back office.
    -   **Efecto de cambiar este ajuste:** Este es un campo de solo visualización.
    -   **Valor recomendado:** Copie esta URL y configúrela como una "tarea programada" (cron job) en el servidor de su alojamiento web.
    -   **Escenario / ejemplo del comerciante:** Desea que su feed de Pinterest se actualice todas las noches a las 3 AM. Copia esta URL y configura una tarea programada en su servidor para visitar esta URL diariamente a las 3 AM.
-   **Cómo configurar una tarea programada (Cron Job):**

    -   **Qué hace este ajuste:** Proporciona instrucciones sobre cómo configurar una tarea automatizada (tarea programada) en su servidor web para actualizar regularmente su feed de productos.
    -   **Efecto de cambiar este ajuste:** Esta es una sección informativa.
    -   **Valor recomendado:** Siga estas instrucciones o proporciónelas a su webmaster/soporte de alojamiento para asegurarse de que su feed esté siempre actualizado.
    -   **Escenario / ejemplo del comerciante:** No está seguro de cómo configurar una tarea programada. Esta sección le brinda los pasos exactos o la información para pasar a su proveedor de alojamiento.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### Panel de control de feeds de Pinterest (Back Office > Vender > Feeds de Pinterest)

Esta sección dedicada de su back office de PrestaShop proporciona una interfaz de descripción general y gestión para sus feeds de productos de Pinterest. Puede encontrarla en el menú "Vender" en PrestaShop 1.7/8/9.

-   **Nombre de la pantalla y ubicación del menú:** Feeds de Pinterest (en "Vender" en el menú principal).
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado de feeds:** Esta tabla muestra todos los feeds generados (si el módulo admite múltiples feeds, de lo contrario mostrará el principal). Normalmente incluye:
        -   **Nombre/ID del feed:** Un identificador único para el feed.
        -   **Idioma:** El idioma de los productos en el feed.
        -   **Moneda:** La moneda de los precios en el feed.
        -   **Última generación:** La fecha y hora de la última actualización del feed.
        -   **URL del feed:** El enlace directo al archivo del feed generado.
        -   **Acciones:** Botones para ver, descargar o regenerar el feed.
    -   **Agregar nuevo feed / Editar feed:** Si bien el módulo se centra principalmente en un único feed principal, esta interfaz podría permitir una futura expansión o configuraciones de feed específicas. Por ahora, refleja en gran medida la configuración de la página de configuración principal.
    -   **Vista de cuadrícula / gestión:** Esta pantalla proporciona una visión clara del estado de su feed y acceso rápido a su URL y opciones de regeneración.
-   **Efecto de los cambios:**
    -   *Regenerar un feed:* Actualiza el archivo del feed con los últimos datos de productos de su tienda, reflejando cualquier cambio en la información del producto, precios o niveles de stock.
    -   *Ver la URL del feed:* Le permite copiar rápidamente la URL necesaria para Pinterest.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revise periódicamente este panel para asegurarse de que su feed se esté generando regularmente (si ha configurado una tarea programada) y que la marca de tiempo de "Última generación" sea reciente.
    2.  Si realiza cambios significativos en los productos (por ejemplo, actualizaciones masivas de precios, lanzamientos de nuevos productos), podría regenerar manualmente el feed desde esta pantalla o la configuración del módulo para asegurarse de que Pinterest obtenga los datos más recientes rápidamente.
    3.  Copie la URL del feed desde aquí al configurar inicialmente su cuenta de empresa de Pinterest.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Activar Feed de Pinterest | SÍ | Activa/desactiva la generación del feed. |
| | Tipo de archivo de feed | XML | Establece el formato de salida para el feed (CSV o XML). |
| | Idioma predeterminado para el feed | Su idioma principal | Idioma para nombres/descripciones de productos. |
| | Moneda predeterminada para el feed | Su moneda principal | Moneda para precios de productos. |
| | País predeterminado para el feed | Su país principal | Asociación de país para productos. |
| | Transportista predeterminado para el feed | Su transportista predeterminado | Transportista de envío para estimaciones de Pinterest. |
| | Incluir combinaciones de productos | SÍ | Exporta variaciones individuales de productos. |
| | Exportar productos con atributo específico | Seleccione el atributo relevante (por ejemplo, Talla) | Incluye atributos específicos del producto en el feed. |
| | Exportar productos con característica específica | Seleccione la característica relevante (por ejemplo, Material) | Incluye características específicas del producto en el feed. |
| | Exportar productos con etiqueta personalizada específica | Seleccione la etiqueta relevante (por ejemplo, Más vendido) | Incluye etiquetas personalizadas para marketing. |
| | Excluir productos por categoría | Seleccione las categorías a excluir | Evita que los productos de las categorías elegidas aparezcan en el feed. |
| | Excluir productos específicos | Seleccione productos individuales a excluir | Evita que productos específicos aparezcan en el feed. |
| | Generar URL del feed | (Solo visualización) | La URL que se debe proporcionar a Pinterest para obtener su feed. |
| | Generar feed (Botón) | Haga clic después de los cambios | Activa manualmente la generación inmediata del feed. |
| **Pestaña de Configuración de Tareas Programadas** | URL de la tarea programada (Cron Job) | (Solo visualización) | URL para la generación automatizada del feed a través de la tarea programada del servidor. |
| | Cómo configurar una tarea programada (Cron Job) | Siga las instrucciones | Guía para configurar actualizaciones automatizadas del feed. |
| **Panel de control de feeds de Pinterest** | Tabla de listado de feeds | (Ver) | Descripción general de los feeds generados, estado y URLs. |
| | Regenerar feed (Acción) | Haga clic según sea necesario | Actualiza el feed con los últimos datos de la tienda. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis productos no aparecen en Pinterest después de configurar el feed. ¿Qué debo hacer?**
R1: Primero, asegúrese de que la configuración "Activar Feed de Pinterest" en la configuración del módulo esté establecida en SÍ. Luego, haga clic manualmente en el botón "Generar feed" para crear el archivo de feed inicial. A continuación, verifique que haya copiado y pegado correctamente la "URL de generación de feed" en la configuración del catálogo de productos de su cuenta de empresa de Pinterest. Pinterest puede tardar algún tiempo (hasta 24-48 horas) en procesar un nuevo feed. Además, revise su cuenta de empresa de Pinterest en busca de mensajes de error relacionados con el feed.

**P2: Los precios o los niveles de stock en Pinterest están desactualizados. ¿Cómo puedo solucionar esto?**
R2: Esto generalmente significa que su feed no se está actualizando regularmente. Asegúrese de haber configurado la tarea programada (cron job) en su servidor de alojamiento utilizando la "URL de la tarea programada" proporcionada en el módulo. Si la tarea programada está configurada, verifique que se esté ejecutando correctamente (su proveedor de alojamiento puede ayudarlo con esto). También puede regenerar manualmente el feed haciendo clic en el botón "Generar feed" en la configuración del módulo para forzar una actualización inmediata.

**P3: Faltan algunos de mis productos en el feed de Pinterest.**
R3: Vaya a la página de configuración del módulo y verifique las configuraciones "Excluir productos por categoría" y "Excluir productos específicos". Es posible que haya excluido inadvertidamente categorías o productos individuales. Además, asegúrese de que los productos tengan imágenes válidas, precios y estén configurados como "activos" y "disponibles para pedido" en su tienda PrestaShop, ya que el módulo normalmente solo exporta productos activos y comprables.

**P4: El proceso de generación del feed tarda mucho tiempo o se agota el tiempo de espera.**
R4: Si tiene un catálogo muy grande (miles de productos), generar el feed puede consumir muchos recursos.
\* **Solución 1:** Aumente los ajustes de `memory_limit` y `max_execution_time` de PHP en el archivo `php.ini` de su servidor. Su proveedor de alojamiento puede ayudarlo con esto.
\* **Solución 2:** Asegúrese de que su tarea programada esté configurada para ejecutarse durante las horas de menor actividad para minimizar el impacto en el rendimiento de la tienda.
\* **Solución 3:** Considere excluir categorías o productos menos importantes si el tamaño del feed es un problema constante.

**P5: Los estilos de mi tema personalizado no se aplican a la interfaz de administración del módulo.**
R5: La interfaz de administración del módulo utiliza su propio CSS (`admin-app.css`, `admin-theme.css`). Estos son independientes de su tema de front-office. Si desea personalizar la apariencia de las páginas de back-office del módulo, necesitaría sobrescribir estos archivos CSS específicos o agregar CSS personalizado a su back office de PrestaShop. Esta es típicamente una tarea para un desarrollador web.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Feed de productos de Pinterest" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo `pinterestfeed` sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, con controladores frontales dedicados para la generación de feeds y la ejecución de tareas programadas (cron), y controladores de administración para la configuración y gestión. Aprovecha `ObjectModel` para la posible persistencia de datos (aunque se centra principalmente en la generación dinámica de feeds) y utiliza plantillas Smarty para renderizar tanto la configuración del back-office como las vistas informativas. La lógica central para generar el feed de acuerdo con las especificaciones de Pinterest está encapsulada en clases auxiliares dedicadas.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan las solicitudes orientadas al público, principalmente para el feed en sí y la ejecución de tareas programadas.

-   `controllers/front/cron.php`
    -   **Nombre de la clase y clase padre:** `PinterestFeedCronModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador está diseñado para ser llamado por una tarea programada (cron job) del lado del servidor. Cuando se accede, activa la clase `PinterestFeedGenerator` para regenerar el feed de productos basándose en la configuración actual del módulo. Normalmente devuelve un mensaje simple de éxito/fallo o registra el proceso. No renderiza una página visual.
-   `controllers/front/feed.php`
    -   **Nombre de la clase y clase padre:** `PinterestFeedFeedModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador sirve el archivo de feed de productos real. Cuando se accede a través de la "URL de generación de feed", lee el archivo de feed pregenerado (o lo genera si no existe/está desactualizado, dependiendo de la implementación) y genera su contenido (CSV o XML) con los encabezados HTTP apropiados (`Content-Type`).

#### Controladores de administración del Back-Office

Estos controladores gestionan la configuración del módulo y proporcionan interfaces administrativas.

-   `controllers/admin/AdminExportProductsFeedPinterest.php`
    -   **Nombre de la clase y clase padre:** `AdminExportProductsFeedPinterestController` que extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Este controlador es responsable del panel de control "Feeds de Pinterest" que se encuentra en el menú "Vender". Gestiona la visualización y las acciones relacionadas con los feeds de productos generados. No gestiona directamente una entidad `ObjectModel` específica, sino que orquesta la generación y visualización de datos relacionados con el feed.
    -   **Claves de configuración clave utilizadas:** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (para valores predeterminados en formularios), `pm_pinterestfeed_products`, `pm_export_size_attribute` (para configuraciones específicas del módulo). También utiliza `pf_tree` para la selección de categorías y `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` para la selección de idioma en formularios.
-   `controllers/admin/index.php`
    -   **Nombre de la clase y clase padre:** Este archivo probablemente sirve como un marcador de posición o una simple redirección/punto de entrada para la sección de administración, en lugar de un controlador completo. En PrestaShop, los archivos `index.php` en subdirectorios a menudo evitan la lista directa de directorios. Su función principal es garantizar la seguridad al evitar el acceso directo al contenido del directorio.

### 4.3 Clases y modelos principales (`classes/`)

-   `classes/index.php`
    -   **Propósito:** Archivo de seguridad estándar de PrestaShop para evitar la lista directa de directorios.
-   `classes/PinterestFeedGenerator.php`
    -   **Responsabilidad:** Esta es la clase de lógica central para construir el feed de productos.
    -   **Interacción con la base de datos:** Interactúa con varias tablas principales de PrestaShop (por ejemplo, `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`) para obtener datos de productos.
    -   **Extensión de ObjectModel:** No extiende `ObjectModel` directamente, ya que su propósito es la agregación y el formato de datos en lugar de la persistencia de una sola entidad.
    -   **Métodos públicos clave:** Contiene métodos para obtener productos, manejar combinaciones, aplicar filtros (categorías, productos específicos), formatear datos según las especificaciones de Pinterest y escribir la salida al tipo de archivo elegido (CSV/XML).
-   `classes/PinterestFeedSpec.php`
    -   **Responsabilidad:** Esta clase probablemente define los campos requeridos y opcionales para la especificación del feed de productos de Pinterest. Actúa como una capa de mapeo o validación para garantizar que el feed generado cumpla con las directrices de Pinterest.
    -   **Interacción con la base de datos:** Ninguna directamente.
    -   **Extensión de ObjectModel:** No extiende `ObjectModel`.
    -   **Métodos públicos clave:** Puede contener métodos para recuperar la lista de campos requeridos/opcionales, sus tipos de datos y cualquier regla de formato específica.

### 4.4 Activos JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office.
    -   **Propósito:** Proporciona funcionalidad de autocompletado, probablemente para buscar y seleccionar productos o categorías en los formularios de configuración de administración (por ejemplo, para "Excluir productos específicos").
    -   **Detectores de eventos:** Se enlaza a los eventos `keyup` o `input` del campo de entrada para activar búsquedas AJAX.
    -   **Manipulación del DOM:** Muestra los resultados de la búsqueda en una lista desplegable, permite la selección y actualiza los campos de entrada ocultos.
-   `views/js/admin-app.js`
    -   **Alcance:** Back-office.
    -   **Propósito:** JavaScript principal para la configuración y el panel de control del back-office del módulo. Maneja el envío de formularios, las actualizaciones dinámicas y, potencialmente, las llamadas AJAX para el estado de generación del feed.
    -   **Detectores de eventos:** Se enlaza a los eventos `submit` del formulario, a los eventos `click` de los botones (por ejemplo, "Generar feed") y, potencialmente, a los eventos `change` de los cuadros de selección.
    -   **Manipulación del DOM:** Gestiona la visualización de las pestañas de configuración, actualiza los mensajes de estado e interactúa con el componente de autocompletado.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Propósito:** Estiliza la entrada de búsqueda de autocompletado y sus resultados desplegables, asegurando una apariencia consistente dentro del back office de PrestaShop.
    -   **Selectores de clase CSS clave:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `views/admin-theme.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Propósito:** Proporciona un estilo general para las páginas de configuración del back-office del módulo, asegurando que se integre bien con el tema de administración de PrestaShop.
    -   **Selectores de clase CSS clave:** `.panel`, `.form-group`, `.control-label`, `.help-block`.
-   `views/css/admin-app.css`
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Propósito:** Estilo específico para los elementos y el diseño personalizados del módulo dentro de la interfaz de administración, como la navegación por pestañas, los botones personalizados o los bloques de información únicos.
    -   **Selectores de clase CSS clave:** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de gancho (`views/templates/hook/`)**: La descripción del módulo no enumera explícitamente las plantillas de gancho, lo que sugiere que su presencia en el front-office es principalmente a través de la URL del feed, no de la visualización directa. Si las hubiera, serían para bloques informativos.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `views/templates/admin/dashboard.tpl`: Probablemente la plantilla principal para el panel de control "Feeds de Pinterest", que muestra la lista de feeds, su estado y acciones.
    -   `views/templates/admin/feeds.tpl`: Podría ser una plantilla parcial utilizada dentro de `dashboard.tpl` para renderizar la tabla de feeds.
    -   `views/templates/admin/form-chrome.tpl`: Una plantilla genérica de envoltura para formularios de administración, que proporciona el panel estándar de PrestaShop y la estructura del formulario.
    -   `views/templates/admin/layout.tpl`: La plantilla de diseño principal para la sección de administración del módulo, que define la estructura general, incluyendo el encabezado, las pestañas y el área de contenido.
-   **Plantillas de configuración y utilidad (`views/`)**:
    -   `views/categories-fancybox.tpl`: Plantilla para un modal Fancybox utilizado para la selección de categorías (por ejemplo, para exclusión).
    -   `views/custom-labels.tpl`: Plantilla para mostrar o gestionar etiquetas personalizadas.
    -   `views/exclude-products.tpl`: Plantilla para la interfaz de búsqueda y selección de exclusión de productos.
    -   `views/google_lang_links.tpl`: Potencialmente para mostrar enlaces o información específicos del idioma, aunque su uso directo en un módulo de feed de Pinterest podría ser para fines informativos.
    -   `views/returnAlert.tpl`: Una plantilla genérica para mostrar alertas de éxito o error en el back office.
    -   `views/script-fancybox.tpl`: Contiene JavaScript para inicializar y gestionar modales Fancybox.
    -   `views/script.tpl`: Fragmentos de JavaScript generales o scripts de inicialización para las páginas de administración del módulo.
    -   `lib/searchTool/views/scripts.tpl`: Contiene JavaScript para la herramienta de búsqueda de autocompletado.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:
    -   El módulo no parece crear sus propias tablas SQL personalizadas basándose en el inventario proporcionado.
    -   Se basa en gran medida en las tablas principales existentes de PrestaShop: `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (para la configuración del módulo como `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE`, etc.).
-   **Tabla de ganchos registrados**:
    La función principal del módulo es la generación de feeds, que normalmente se activa mediante el acceso directo al controlador (URL del feed, URL de la tarea programada) o acciones de administración. Si bien la descripción del módulo menciona "Ganchos de Front-Office: Encabezado, Columnas, Producto o Pie de página", el inventario de archivos y la descripción de las características proporcionadas sugieren que *este módulo específico* no los utiliza activamente para la visualización. En cambio, el módulo probablemente registra ganchos para procesos internos o posibles extensiones futuras.

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En cada carga de página en el front office. | Potencialmente para agregar JS/CSS personalizado si el módulo tuviera un componente de front-office, o para seguimiento interno. (Poco probable que sea utilizado para salida visual por este módulo). |
| `displayRightColumn` | En la columna derecha del front office. | (Poco probable que sea utilizado para salida visual por este módulo). |
| `displayLeftColumn` | En la columna izquierda del front office. | (Poco probable que sea utilizado para salida visual por este módulo). |
| `displayFooter` | En el pie de página de cada página en el front office. | (Poco probable que sea utilizado para salida visual por este módulo). |
| `displayProductExtraContent` | En la página del producto, debajo del contenido principal. | (Poco probable que sea utilizado para salida visual por este módulo). |
| `actionProductUpdate` | Después de que un producto se actualiza en el back office. | Potencialmente para marcar el feed como que necesita regeneración o para activar una actualización parcial. |
| `actionProductAdd` | Después de que se agrega un nuevo producto. | Similar a `actionProductUpdate`. |
| `actionProductDelete` | Después de que se elimina un producto. | Similar a `actionProductUpdate`. |
| `actionUpdateQuantity` | Después de que cambia la cantidad de stock del producto. | Potencialmente para activar la regeneración del feed si los cambios de stock son críticos para el feed. |
| `actionModuleInstall` | Durante la instalación del módulo. | Para crear entradas de configuración y, potencialmente, el archivo de feed inicial. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para limpiar las entradas de configuración y los archivos generados. |
| `displayAdminProductsExtra` | En la página de edición del producto en el back office. | Podría usarse para agregar una pestaña o campo específico relacionado con la configuración del feed de Pinterest para productos individuales. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para su módulo "Feed de productos de Pinterest", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y le ayude a alcanzar sus objetivos de comercio electrónico.

-   **Historial de pedidos y descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Contacto de soporte de MyPresta.eu:** <https://mypresta.eu/contact>
