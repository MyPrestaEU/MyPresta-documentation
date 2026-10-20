---
title: "Pretty / Clean URLs PRO - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Pretty / Clean URLs PRO de PrestaShop por MyPresta.eu."
sidebar:
  label: "Pretty / Clean URLs PRO - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Pretty / Clean URLs PRO en MyPresta.eu](https://mypresta.eu/modules/seo/pretty-clean-urls-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/seo/pretty-clean-urls-pro/)
>
> ---


# Pretty / Clean URLs PRO

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.0.0 - 1.7.4.x, 1.7.5.0 - 1.7.7.x, 1.7.8.x, 8.x, 9.x
-   **Compatibilidad PHP**: PHP 5.6 - 8.5
-   **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Tu servidor también debe tener `mod_rewrite` habilitado para Apache o una funcionalidad equivalente de reescritura de URL para Nginx, lo cual es estándar para la mayoría de las instalaciones de PrestaShop.
-   **URLs Amigables de PrestaShop**: La opción nativa de PrestaShop "URL amigable" (que se encuentra en **Parámetros de la tienda > SEO y URLs**) *debe estar habilitada* para que este módulo funcione correctamente. Este módulo mejora la funcionalidad nativa de PrestaShop, no la reemplaza.

## 2. Guía Completa de Configuración

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" te llevará a la página de configuración principal de "Pretty / Clean URLs PRO". Aquí es donde controlas el comportamiento principal del módulo.

**Configuración General**

-   **Habilitar URLs Bonitas:**
    -   **Qué hace esta configuración:** Este es el interruptor principal del módulo. Controla si el módulo genera y utiliza activamente URLs limpias en toda tu tienda.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* El módulo comenzará a generar y redirigir a URLs limpias para todos los tipos de página compatibles (productos, categorías, CMS, etc.).
        -   *Cuando está deshabilitado:* El módulo estará inactivo, y PrestaShop volverá a su estructura de URL predeterminada (que puede incluir IDs).
    -   **Valor recomendado:** **SÍ** (Esta es la función principal del módulo).
    -   **Escenario / ejemplo del comerciante:** Acabas de instalar el módulo y quieres activar sus beneficios SEO. Habilitarías esta configuración. Si necesitas solucionar problemas temporalmente o volver al comportamiento predeterminado de PrestaShop, podrías deshabilitarlo.
-   **Eliminar IDs de las URLs:**
    -   **Qué hace esta configuración:** Esta opción controla específicamente si el ID numérico (por ejemplo, `123` en `tutienda.com/123-mi-producto`) se elimina de las URLs.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Las URLs serán más cortas y limpias, como `tutienda.com/mi-producto`. Esto es generalmente mejor para el SEO y la estética.
        -   *Cuando está deshabilitado:* Las URLs seguirán siendo "bonitas" pero conservarán el ID, por ejemplo, `tutienda.com/123-mi-producto`. Esto podría ser útil si tienes sistemas externos que dependen de que el ID esté presente en la URL, aunque es menos común.
    -   **Valor recomendado:** **SÍ** (Para el máximo beneficio SEO y una estética limpia).
    -   **Escenario / ejemplo del comerciante:** Quieres las URLs más limpias posibles para una mejor indexación en los motores de búsqueda y legibilidad para el usuario. Habilitarías esto.
-   **Redirección Automática 301:**
    -   **Qué hace esta configuración:** Esta configuración crítica le dice al módulo que cree automáticamente redirecciones permanentes 301 de las URLs antiguas basadas en ID a las nuevas URLs limpias.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Cualquier visitante o bot de motor de búsqueda que intente acceder a una URL antigua (por ejemplo, una que fue indexada antes de que el módulo estuviera activo) será redirigido sin problemas a la nueva URL limpia. Esto evita errores 404 y preserva tu valor SEO de enlaces.
        -   *Cuando está deshabilitado:* Las URLs antiguas llevarán a errores 404 "Página no encontrada", lo cual es malo para la experiencia del usuario y puede dañar gravemente tu SEO.
    -   **Valor recomendado:** **SÍ** (Absolutamente esencial para mantener el SEO y la experiencia del usuario durante y después de la transición a URLs limpias).
    -   **Escenario / ejemplo del comerciante:** Acabas de activar el módulo en una tienda existente con muchas páginas indexadas. Habilitar esto asegura que todos tus enlaces antiguos sigan funcionando y pasen su valor SEO a los nuevos enlaces.
-   **Forzar Barra Final:**
    -   **Qué hace esta configuración:** Determina si siempre se añade una barra final (`/`) al final de tus URLs (por ejemplo, `tutienda.com/categoria/` vs. `tutienda.com/categoria`).
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Todas las URLs generadas terminarán con una barra. Esto puede ayudar con la consistencia de las URLs y algunas herramientas SEO lo prefieren.
        -   *Cuando está deshabilitado:* Las URLs no necesariamente terminarán con una barra, dependiendo del comportamiento predeterminado de PrestaShop para ese tipo de página.
    -   **Valor recomendado:** **SÍ** (Para consistencia y para evitar posibles problemas de contenido duplicado si los motores de búsqueda tratan `url` y `url/` como páginas diferentes).
    -   **Escenario / ejemplo del comerciante:** Quieres asegurarte de que todas las URLs de tus categorías y páginas CMS terminen consistentemente con una barra para una mejor gestión SEO y para prevenir posibles problemas de contenido duplicado.
-   **Eliminar Extensión .html:**
    -   **Qué hace esta configuración:** Esta opción controla si la extensión `.html` se elimina de las URLs de productos y páginas CMS.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* Las URLs serán aún más cortas, por ejemplo, `tutienda.com/mi-producto` en lugar de `tutienda.com/mi-producto.html`. Esto es generalmente preferido para el diseño web moderno y el SEO.
        -   *Cuando está deshabilitado:* Las URLs de productos y páginas CMS conservarán la extensión `.html`.
    -   **Valor recomendado:** **SÍ** (Para la estructura de URL más limpia y moderna).
    -   **Escenario / ejemplo del comerciante:** Quieres que las páginas de tus productos se vean como `tutienda.com/mi-producto` en lugar de `tutienda.com/mi-producto.html` para una apariencia más elegante y un mejor SEO.

**Botón Guardar:**

-   Haz clic siempre en el botón "Guardar" después de realizar cualquier cambio para aplicarlos a tu tienda.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

Este módulo funciona principalmente anulando las clases y controladores principales de PrestaShop para modificar la generación y el enrutamiento de URLs. Aunque no introduce un nuevo elemento de menú dedicado en el Back Office para gestionar una lista de "URLs Bonitas", se integra directamente con las funcionalidades existentes de PrestaShop.

**Integración con AdminProductsController (Back Office > Catálogo > Productos)**

-   **Nombre de la Pantalla y Ubicación del Menú:** **Catálogo > Productos**
-   **Acciones y Configuraciones Disponibles:**
    -   Cuando editas o creas un producto, el módulo influye en cómo se comporta el campo "URL amigable". En lugar de requerir que elimines manualmente los IDs o asegures una estructura limpia, la lógica del módulo generará y sugerirá automáticamente una URL limpia y sin ID basada en el nombre de tu producto y la configuración del módulo.
    -   El módulo asegura que cuando guardas un producto, su URL se genera de acuerdo con la configuración de "Pretty / Clean URLs PRO" (por ejemplo, sin ID, sin extensión `.html` si está configurado).
-   **Efecto de los cambios:**
    -   Cuando guardas un producto, la URL generada y utilizada por PrestaShop reflejará la estructura de URL limpia definida en la configuración del módulo.
    -   Si cambias el nombre de un producto, el módulo ayudará a asegurar que la URL amigable se actualice limpiamente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   Continúa gestionando tus productos como de costumbre en **Catálogo > Productos**. El módulo funciona en segundo plano para asegurar que las URLs estén optimizadas.
    -   Al crear o editar productos, asegúrate de que los nombres de tus productos sean descriptivos, ya que se utilizan para generar las URLs amigables.
    -   Aún puedes ajustar manualmente el campo "URL amigable" para un producto si necesitas una URL específica, pero la lógica del módulo guiará la generación inicial.

**Otros Controladores de Administración (Integración Implícita)**

El módulo también afecta implícitamente otras áreas donde se generan URLs, como:

-   **Catálogo > Categorías**: Al crear o editar categorías.
-   **Catálogo > Marcas**: Al crear o editar marcas.
-   **Catálogo > Proveedores**: Al crear o editar proveedores.
-   **Diseño > Páginas (CMS)**: Al crear o editar páginas CMS.

En todos estos casos, el módulo asegura que las URLs amigables generadas por PrestaShop se adhieran a la configuración de "Pretty / Clean URLs PRO", eliminando IDs y extensiones según lo configurado.

### 2.3 Integración de la Configuración de SEO y URLs de PrestaShop

El módulo "Pretty / Clean URLs PRO" a partir de la versión 2.8.3 y superiores tiene su propia sección dedicada para definir esquemas de URL, lo que hace innecesario configurar manualmente estas opciones en la sección nativa de PrestaShop **Parámetros de la tienda > SEO y URLs**. Sin embargo, es crucial entender la interacción.

:::caution Nota Importante
Aunque el módulo gestiona el esquema de URL, la opción nativa de PrestaShop **URL amigable** en **Parámetros de la tienda > SEO y URLs** *debe estar habilitada* para que el módulo funcione. El módulo mejora esta funcionalidad central de PrestaShop.
:::

**Esquema de URLs (Gestionado por el Módulo)**

Históricamente, los usuarios de PrestaShop definían los patrones de URL (rutas) para productos, categorías, páginas CMS, etc., en la sección **Parámetros de la tienda > SEO y URLs**. El módulo "Pretty / Clean URLs PRO" ahora asume esta responsabilidad, permitiéndote configurarlas directamente desde su propia página de configuración.

El módulo asegura que las rutas se configuren para eliminar `{id}` de las URLs, lo cual es esencial para URLs verdaderamente limpias. Si, por alguna razón, encuentras que las rutas en **Parámetros de la tienda > SEO y URLs** todavía contienen `{id}` después de instalar y configurar el módulo, podría indicar un problema con las anulaciones del módulo (consulta la Sección 6 para solucionar problemas).

Como referencia, aquí están las estructuras de ruta recomendadas que el módulo busca implementar:

| Tipo de Ruta          | Valor Predeterminado de PrestaShop (Ejemplo) | Valor Deseado del Módulo (Limpio) |
| :------------------ | :--------------------------------- | :----------------------------- |
| Ruta a producto    | `{category:/}{id}-{rewrite}{-:ean13}.html` | `{category:/}{rewrite}.html` (o `{rewrite}.html`) |
| Ruta a categoría   | `{id}-{rewrite}`                   | `{parent_categories:/}{rewrite}/` (o `{rewrite}/`) |
| Ruta a proveedor   | `{id}__{rewrite}`                  | `supplier/{rewrite}/`          |
| Ruta a fabricante | `{id}_{rewrite}`                   | `manufacturer/{rewrite}/`      |
| Ruta a página CMS   | `content/{id}-{rewrite}`           | `info/{rewrite}.html`          |
| Ruta a página de categoría CMS | `content/category/{id}-{rewrite}` | `info/{rewrite}`               |

:::tip Entorno Multitienda
Si estás ejecutando una Multitienda PrestaShop, recuerda verificar y, si es necesario, ajustar la configuración del esquema de URL para cada tienda individual. Puedes seleccionar la tienda que deseas configurar desde el menú de contexto de la tienda en tu Back Office.
:::

### 2.4 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Config. del Módulo | Habilitar URLs Bonitas | SÍ | Activa/desactiva la funcionalidad principal del módulo. |
| Config. del Módulo | Eliminar IDs de las URLs | SÍ | Elimina los IDs numéricos de las URLs (por ejemplo, `123-producto` se convierte en `producto`). |
| Config. del Módulo | Redirección Automática 301 | SÍ | Redirige las URLs antiguas basadas en ID a nuevas URLs limpias, preservando el SEO. |
| Config. del Módulo | Forzar Barra Final | SÍ | Asegura que todas las URLs terminen con `/` para consistencia y SEO. |
| Config. del Módulo | Eliminar Extensión .html | SÍ | Elimina `.html` de las URLs de productos/páginas CMS para enlaces más limpios. |
| Catálogo > Productos (Editar) | Campo URL amigable | Auto-generado | El módulo influye en la generación automática de URLs limpias para productos. |
| Catálogo > Categorías (Editar) | Campo URL amigable | Auto-generado | El módulo influye en la generación automática de URLs limpias para categorías. |
| Diseño > Páginas (Editar) | Campo URL amigable | Auto-generado | El módulo influye en la generación automática de URLs limpias para páginas CMS. |
| Parámetros de la tienda > SEO y URLs | URL amigable | SÍ | **CRÍTICO:** Debe estar habilitado para que el módulo funcione. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Después de instalar, mis URLs siguen igual o estoy recibiendo errores 404.**

-   **R:** Primero, asegúrate de que "Habilitar URLs Bonitas" esté configurado en SÍ en la configuración del módulo.
-   Segundo, ve a **Parámetros Avanzados > Rendimiento** en tu Back Office de PrestaShop y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
-   Tercero, asegúrate de que la opción nativa de PrestaShop "URL amigable" esté habilitada en **Parámetros de la tienda > SEO y URLs**. Este módulo mejora la funcionalidad nativa de URL amigable de PrestaShop, no la reemplaza por completo.
-   Finalmente, verifica el archivo `.htaccess` de tu servidor (si usas Apache) o la configuración de Nginx. El módulo depende de la reescritura de URL del lado del servidor (mod_rewrite para Apache) para funcionar correctamente. Si no estás seguro, contacta a tu proveedor de hosting.

**P2: Mi tema personalizado tiene algunos problemas extraños de visualización después de habilitar el módulo.**

-   **R:** Este módulo afecta principalmente la generación y redirección de URLs, no la visualización visual. Es poco probable que cause directamente problemas de visualización del tema. Sin embargo, si has borrado la caché, es posible que el CSS o JS de tu tema necesiten recargarse. Intenta borrar la caché de tu navegador. Si el problema persiste, podría ser un conflicto con otro módulo o una modificación de tema personalizada. Deshabilita temporalmente "Pretty / Clean URLs PRO" para ver si el problema se resuelve. Si lo hace, contacta al soporte de MyPresta.eu.

**P3: ¿Funcionará este módulo con mis URLs personalizadas o redirecciones existentes?**

-   **R:** El módulo se centra en generar URLs limpias para las entidades principales de PrestaShop (productos, categorías, CMS, etc.). Si has creado manualmente redirecciones personalizadas o URLs amigables específicas fuera del sistema estándar de PrestaShop, la redirección automática 301 del módulo priorizará sus propias URLs limpias generadas. Generalmente, es mejor dejar que el módulo gestione todas las URLs de las entidades principales para mantener la consistencia. Si tienes redirecciones personalizadas muy específicas, es posible que debas probar cómo interactúan.

**P4: Cambié el nombre de un producto, pero la URL no se actualizó automáticamente.**

-   **R:** Cuando cambias el nombre de un producto, PrestaShop suele sugerir una nueva URL amigable. Debes guardar explícitamente el producto para que los cambios surtan efecto y para que el módulo procese la nueva URL. Si el campo de URL amigable no se actualiza automáticamente, es posible que debas hacer clic manualmente en "Generar URL" junto al campo de URL amigable en la página de edición del producto, y luego guardar el producto. El módulo se asegurará entonces de que esta nueva URL sea limpia y gestionará la redirección desde la antigua.

**P5: ¿Afecta este módulo a mis URLs multilingües?**

-   **R:** ¡No, las mejora! El módulo funciona con las capacidades multilingües de PrestaShop. Generará URLs limpias para cada idioma, respetando el código de idioma en la URL (por ejemplo, `/es/mi-producto` y `/fr/mon-produit`). Asegúrate de que los nombres de tus productos, categorías y páginas CMS estén traducidos para cada idioma para obtener las mejores URLs amigables.

**P6: Veo un mensaje de error "la palabra clave {id} es obligatoria para la ruta (...)" al intentar guardar esquemas de URL.**

-   **R:** Este error suele ocurrir si las anulaciones del módulo (una parte central de su funcionalidad) no están correctamente instaladas o están deshabilitadas en tu tienda PrestaShop. El módulo se basa en estas anulaciones para modificar el comportamiento de enrutamiento de URL predeterminado de PrestaShop, lo que le permite eliminar el `{id}` de las rutas.
    -   **Solución:**
        1.  **Verificar Anulaciones:** Asegúrate de que el sistema de anulación de PrestaShop esté habilitado. Normalmente puedes encontrar esta configuración en **Parámetros Avanzados > Rendimiento**. Busca una opción relacionada con "Desactivar módulos no PrestaShop" o "Desactivar anulaciones" y asegúrate de que esté configurada en "No".
        2.  **Reinstalar Módulo:** A veces, reinstalar el módulo puede resolver problemas de anulación. Desinstala el módulo, borra la caché de PrestaShop y luego vuelve a instalarlo.
        3.  **Verificación Manual de Anulaciones:** Verifica que los archivos de anulación del módulo estén presentes en tus directorios `override/classes/` y `override/controllers/` (por ejemplo, `override/classes/Dispatcher.php`, `override/controllers/front/ProductController.php`). Si faltan, indica un problema de instalación.
    -   Si el problema persiste, contacta al soporte de MyPresta.eu.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Pretty / Clean URLs PRO" opera anulando las clases principales de PrestaShop, específicamente `Dispatcher` y `Link`, para modificar cómo se generan y analizan las URLs. Intercepta la lógica predeterminada de enrutamiento y generación de URLs para eliminar IDs y extensiones basándose en su configuración. El módulo aprovecha el sistema de anulación de PrestaShop (`/override/`) para inyectar su lógica personalizada sin modificar directamente los archivos principales, asegurando la compatibilidad con las actualizaciones. También incluye una anulación del controlador de administración para `AdminProductsController` para asegurar que la generación de URL amigable en el back office se alinee con la configuración del módulo.

### 4.2 Controladores (`controllers/`)

El módulo utiliza principalmente anulaciones de controladores de front-office para modificar la generación y el enrutamiento de URLs.

-   **Controladores de Front-Office**:

    -   `purls/override/controllers/front/CartController.php`
        -   **Nombre de la clase y clase padre**: `CartController` (anula `CartControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para enlaces relacionados con el carrito para asegurar que sean limpios y sin ID cuando corresponda.
    -   `purls/override/controllers/front/CmsController.php`
        -   **Nombre de la clase y clase padre**: `CmsController` (anula `CmsControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para páginas CMS, eliminando IDs y extensiones `.html` según lo configurado.
    -   `purls/override/controllers/front/listing/CategoryController.php`
        -   **Nombre de la clase y clase padre**: `CategoryController` (anula `CategoryControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para páginas de categoría, eliminando IDs y asegurando URLs limpias.
    -   `purls/override/controllers/front/listing/index.php`
        -   **Nombre de la clase y clase padre**: No es un controlador directo, probablemente un archivo vacío o un marcador de posición. El autocargador de PrestaShop podría recoger otros archivos en este directorio.
        -   **Responsabilidad**: Sin responsabilidad directa; sirve como marcador de directorio.
    -   `purls/override/controllers/front/listing/ManufacturerController.php`
        -   **Nombre de la clase y clase padre**: `ManufacturerController` (anula `ManufacturerControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para páginas de fabricante, eliminando IDs y asegurando URLs limpias.
    -   `purls/override/controllers/front/listing/SupplierController.php`
        -   **Nombre de la clase y clase padre**: `SupplierController` (anula `SupplierControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para páginas de proveedor, eliminando IDs y asegurando URLs limpias.
    -   `purls/override/controllers/front/ProductController.php`
        -   **Nombre de la clase y clase padre**: `ProductController` (anula `ProductControllerCore`)
        -   **Responsabilidad**: Modifica la generación de URL para páginas de producto, eliminando IDs y extensiones `.html` según lo configurado.
-   **Controladores de Administración (Back-Office)**:

    -   `purls/override/controllers/admin/AdminProductsController.php`
        -   **Nombre de la clase y clase padre**: `AdminProductsController` (anula `AdminProductsControllerCore`)
        -   **Responsabilidad**: Se integra con la interfaz de gestión de productos para asegurar que cuando se generan o actualizan URLs amigables en el back office, estas se adhieran a la configuración del módulo (por ejemplo, eliminando IDs). Probablemente modifica el método `generateFriendlyUrl` o una lógica similar.

### 4.3 Clases y Modelos Principales (`classes/`)

La lógica central del módulo reside en sus anulaciones de clase, que son fundamentales para cómo PrestaShop maneja las URLs.

-   `purls/override/classes/Dispatcher.php`
    -   **Nombre de la clase y clase padre**: `Dispatcher` (anula `DispatcherCore`)
    -   **Interacción con la base de datos**: Ninguna directamente, pero interactúa con `ps_configuration` para la configuración del módulo.
    -   **Métodos públicos clave y lógica de negocio**: Esta clase es responsable de enrutar las solicitudes entrantes al controlador correcto y de generar URLs. La anulación probablemente modifica métodos como `getFriendlyUrl` o `createUrl` para eliminar IDs y extensiones, y para manejar la lógica de redirección 301 para URLs antiguas. Es el punto central para el análisis y la generación de URLs.
-   `purls/override/classes/Link.php`
    -   **Nombre de la clase y clase padre**: `Link` (anula `LinkCore`)
    -   **Interacción con la base de datos**: Ninguna directamente, pero interactúa con `ps_configuration` para la configuración del módulo.
    -   **Métodos públicos clave y lógica de negocio**: La clase `Link` se utiliza en todo PrestaShop para construir URLs para varias entidades (productos, categorías, CMS, etc.). La anulación en este módulo modifica métodos como `getProductLink`, `getCategoryLink`, `getCMSLink`, etc., para generar URLs que sean limpias, sin ID y sin extensiones `.html` según la configuración del módulo. Funciona en conjunto con la anulación de `Dispatcher` para asegurar una generación de URL consistente.

### 4.4 Activos JavaScript (`views/js/`)

-   `purls/views/js/purls.js`
    -   **Alcance**: Back-office (probablemente en páginas de edición de productos/categorías/CMS).
    -   **Detalles**: Este script probablemente contiene lógica del lado del cliente para mejorar el proceso de generación de URL amigable dentro del Back Office de PrestaShop. Podría:
        -   Escuchar los cambios en los nombres de productos/categorías/CMS y actualizar automáticamente el campo "URL amigable" basándose en la configuración del módulo.
        -   Proporcionar retroalimentación o validación en tiempo real para las URLs generadas.
        -   Potencialmente interactuar con llamadas AJAX al servidor para obtener URLs amigables sugeridas.
        -   Asegurar que el botón "Generar URL" (si está presente) active la lógica del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No se encontraron archivos CSS personalizados en el archivo del módulo, lo que indica que el módulo no introduce nuevos elementos visuales que requieran un estilo específico. Se basa en el estilo predeterminado del Back Office de PrestaShop para su página de configuración.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `purls/views/purls.tpl`
        -   **Alcance**: Back-office, página de configuración del módulo.
        -   **Detalles**: Esta plantilla renderiza el formulario de configuración principal para el módulo "Pretty / Clean URLs PRO". Contiene la estructura HTML para todas las configuraciones descritas en la Sección 4.1, incluyendo interruptores para habilitar/deshabilitar funciones y el botón "Guardar". Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Almacena su configuración en la tabla estándar `ps_configuration` de PrestaShop. Las claves de configuración suelen seguir un patrón como `PURLS_ENABLE`, `PURLS_REMOVE_IDS`, `PURLS_301_REDIRECT`, etc.
-   **Tabla de Hooks Registrados**:
    El módulo opera principalmente a través de anulaciones de clase en lugar de un registro directo de hooks para su funcionalidad principal. Sin embargo, podría interactuar implícitamente con hooks que activan la generación o redirección de URL.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | En cada carga de página en el front office, dentro de la sección `<head>`. | Aunque no registra directamente un elemento visual, las anulaciones de `Dispatcher` y `Link` del módulo están activas durante la renderización de la página, influyendo en cualquier URL generada dentro del encabezado (por ejemplo, URLs canónicas, selectores de idioma). |
| `actionDispatcherBefore` | Antes de que el despachador procese la solicitud. | La anulación de `Dispatcher` está activa en esta etapa, lo que permite al módulo interceptar y modificar la lógica de análisis y enrutamiento de URL antes de que PrestaShop determine qué controlador cargar. Esto es crucial para manejar las redirecciones 301 desde URLs antiguas. |
| `actionDispatcherAfter` | Después de que el despachador ha procesado la solicitud. | La anulación de `Dispatcher` también puede estar activa aquí, potencialmente para post-procesamiento o registro relacionado con el manejo de URL. |
| `actionProductUpdate` / `actionProductAdd` | Después de que un producto se actualiza o se añade en el Back Office. | La anulación de `AdminProductsController` asegura que cuando se guarda un producto, su URL amigable se genera de acuerdo con la configuración del módulo. Esta es una interacción implícita en lugar de un registro directo de hook por parte del módulo. |
| `actionCategoryUpdate` / `actionCategoryAdd` | Después de que una categoría se actualiza o se añade en el Back Office. | Similar a los productos, el módulo asegura URLs limpias para las categorías. |
| `actionCmsUpdate` / `actionCmsAdd` | Después de que una página CMS se actualiza o se añade en el Back Office. | Similar a los productos, el módulo asegura URLs limpias para las páginas CMS. |

## 5. Soporte Oficial y Recursos

Para actualizaciones oficiales, soporte técnico y cualquier consulta relacionada con el módulo "Pretty / Clean URLs PRO", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener.
