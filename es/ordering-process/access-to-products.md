---
title: "Acceso a Productos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Acceso a Productos' de MyPresta.eu."
sidebar:
  label: "Acceso a Productos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Access to Products en MyPresta.eu](https://mypresta.eu/modules/ordering-process/access-to-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/access-to-products/)
>
> ---


# Acceso a Productos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Acceso a Productos)

Esta es la pantalla de configuración principal donde defines las reglas para el acceso a los productos.

#### Ajustes Generales

| Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- |
| **Habilitar módulo** | SÍ | **Propósito:** Activa o desactiva la funcionalidad del módulo.   **Efecto:**   *Cuando está habilitado:* Todas tus restricciones configuradas estarán activas en el front office.   *Cuando está deshabilitado:* El módulo no tendrá ningún efecto, y todos los productos serán visibles y comprables por todos los clientes, independientemente del grupo.   **Recomendado:** SÍ, una vez que hayas configurado tus reglas. |
| **Bloquear posibilidad de ver página de producto** | NO | **Propósito:** Controla si los clientes que no pertenecen a los grupos permitidos pueden siquiera ver la página dedicada del producto.   **Efecto:**   *Cuando está habilitado:* Si un cliente que no pertenece a un grupo permitido intenta acceder a la página del producto directamente (por ejemplo, a través de un enlace o motor de búsqueda), será redirigido o se le mostrará un mensaje de acceso denegado.   *Cuando está deshabilitado:* Los clientes no autorizados aún pueden ver la página del producto, pero se les impedirá añadirlo a su carrito.   **Recomendado:** SÍ para productos verdaderamente exclusivos, NO si quieres que vean el producto pero no lo compren (por ejemplo, "contáctanos para venta al por mayor"). |
| **Ocultar producto en listas de productos** | NO | **Propósito:** Determina si los productos restringidos se ocultan de las páginas de categoría, resultados de búsqueda y otras listas de productos para clientes no autorizados.   **Efecto:**   *Cuando está habilitado:* Los productos simplemente no aparecerán en ninguna lista de productos para clientes que no pertenezcan a los grupos permitidos.   *Cuando está deshabilitado:* Los productos aparecerán en las listas, pero cuando el cliente haga clic en ellos, se les bloqueará la visualización de la página (si "Bloquear posibilidad de ver página de producto" es SÍ) o se les bloqueará la adición al carrito.   **Recomendado:** SÍ para una experiencia de navegación más limpia y dirigida para cada grupo de clientes. |
| **Mensaje para clientes no permitidos** | "No tienes permiso para pedir este producto." | **Propósito:** El texto que se muestra a los clientes que intentan añadir un producto restringido a su carrito o ver una página de producto restringida (si "Bloquear posibilidad de ver página de producto" es NO).   **Efecto:** Este mensaje aparece en el carrito de compras junto al producto restringido o en la página del producto.   **Recomendado:** Un mensaje claro y educado. Puedes personalizarlo para explicar el motivo (por ejemplo, "Este producto es solo para clientes mayoristas. Por favor, inicia sesión en tu cuenta mayorista."). |

#### Tabla de Restricciones de Productos

Esta sección muestra una lista de todos los productos para los que has definido restricciones de acceso. Puedes añadir nuevas restricciones o editar las existentes aquí.

-   **Nombre del Producto:** El nombre del producto que se está restringiendo.
-   **Grupos de Clientes Permitidos:** Una lista de grupos de clientes a los que *se les permite* ver y/o comprar este producto.
-   **Acciones:** Editar (icono de lápiz) o Eliminar (icono de papelera) la restricción.

#### Añadir/Editar Restricciones de Productos

Cuando haces clic en "Añadir nueva restricción" o en el icono "Editar" para una restricción existente, verás un formulario:

-   **Seleccionar Producto:**

    -   **Qué hace este ajuste:** Te permite buscar y seleccionar el producto específico que deseas restringir.
    -   **Efecto de cambiar este ajuste:** Esto vincula la regla de restricción a un producto particular en tu catálogo.
    -   **Valor recomendado:** Selecciona el producto exacto.
    -   **Escenario de comerciante:** Quieres restringir "Mezcla de Café Mayorista" a tus clientes mayoristas. Buscarías y seleccionarías "Mezcla de Café Mayorista".
-   **Seleccionar Grupos de Clientes:**

    -   **Qué hace este ajuste:** Una lista de todos los grupos de clientes definidos en tu tienda PrestaShop (por ejemplo, Visitante, Invitado, Cliente, Mayorista, VIP). Seleccionas cuáles de estos grupos *tienen permiso* para acceder al producto.
    -   **Efecto de cambiar este ajuste:** Solo los clientes que pertenecen a los grupos seleccionados podrán interactuar con el producto según tus ajustes generales (ver, añadir al carrito). Todos los demás grupos estarán restringidos.
    -   **Valor recomendado:** Selecciona solo los grupos que deben tener acceso.
    -   **Escenario de comerciante:** Para "Mezcla de Café Mayorista", seleccionarías "Mayorista". Si también quisieras que los VIP tuvieran acceso, seleccionarías "Mayorista" y "VIP".

Después de hacer tus selecciones, haz clic en **"Guardar"** para aplicar la restricción.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del Módulo | Habilitar módulo | SÍ | Activa/desactiva toda la funcionalidad del módulo. |
| Configuración del Módulo | Bloquear posibilidad de ver página de producto | NO (considerar SÍ para exclusividad) | Impide que clientes no autorizados vean la página del producto. |
| Configuración del Módulo | Ocultar producto en listas de productos | NO (considerar SÍ para visualización dirigida) | Oculta productos restringidos de los resultados de categoría/búsqueda para clientes no autorizados. |
| Configuración del Módulo | Mensaje para clientes no permitidos | "No tienes permiso para pedir este producto." | Mensaje personalizable que se muestra a clientes no autorizados. |
| Tabla de Restricciones de Productos | Seleccionar Producto | N/A | Elige el producto al que aplicar restricciones. |
| Tabla de Restricciones de Productos | Seleccionar Grupos de Clientes | N/A | Define qué grupos de clientes *tienen permiso* para acceder al producto seleccionado. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: He configurado restricciones, pero no parecen funcionar. ¿Qué debo hacer?**
R:

1.  **Verificar el Estado del Módulo:** Asegúrate de que "Habilitar módulo" esté configurado en SÍ en la configuración del módulo.
2.  **Borrar Caché:** Ve a **Parámetros Avanzados > Rendimiento** en tu Back Office de PrestaShop. Haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto es crucial para que los cambios surtan efecto.
3.  **Asignación de Grupo de Clientes:** Vuelve a verificar que el cliente con el que estás probando esté correctamente asignado al grupo de clientes deseado (Clientes > Clientes, luego edita el cliente).
4.  **Selección de Producto:** Verifica que hayas seleccionado el producto correcto en la configuración de restricciones del módulo.
5.  **Caché del Navegador:** Intenta borrar la caché de tu navegador o probar en una ventana de incógnito/privada para descartar problemas de caché del lado del cliente.

**P: ¿Cómo traduzco el "Mensaje para clientes no permitidos" a otros idiomas?**
R:

1.  Ve a **Internacional > Traducciones** en tu Back Office de PrestaShop.
2.  Selecciona "Traducciones de módulos instalados" como Tipo de traducción.
3.  Elige tu tema.
4.  Selecciona el idioma al que deseas traducir.
5.  Busca el módulo "Acceso a Productos". Deberías ver el campo para el mensaje allí, listo para traducir.

**P: ¿Este módulo ralentizará mi tienda?**
R: El módulo está diseñado para ser ligero y eficiente. Se integra directamente con la lógica central de productos y carritos de PrestaShop. Cualquier impacto en el rendimiento debería ser insignificante, especialmente después del almacenamiento en caché. Si notas ralentizaciones significativas, asegúrate de que tu servidor cumpla con los requisitos mínimos de PrestaShop y de que estés utilizando una versión reciente de PHP.

**P: ¿Qué sucede si un cliente está en varios grupos, y un grupo está permitido mientras que otro no?**
R: Si un cliente pertenece a *cualquier* grupo al que se le permite explícitamente el acceso a un producto, tendrá acceso. El módulo concede acceso si *cualquiera* de los grupos del cliente coincide con un grupo permitido para ese producto. Es una lógica "O": si el Grupo A está permitido O el Grupo B está permitido, y el cliente está en el Grupo A, obtiene acceso.

**P: ¿Puedo restringir el acceso a categorías enteras en lugar de productos individuales?**
R: Este módulo se centra en restricciones de productos individuales. Para restringir categorías enteras, necesitarías aplicar la restricción a cada producto dentro de esa categoría. Para restricciones a nivel de categoría, podrías necesitar un módulo diferente o un desarrollo personalizado.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Resumen de la Arquitectura

El módulo "Acceso a Productos" (`pga`) opera principalmente sobrescribiendo clases centrales de PrestaShop para inyectar su lógica de control de acceso. Aprovecha el `ObjectModel` de PrestaShop para el almacenamiento de la configuración y modifica la visibilidad del producto y el comportamiento del carrito en puntos clave del ciclo de vida de la solicitud del front-office. La lógica principal del módulo reside en `index.php` (el archivo principal del módulo) y sus sobrescrituras.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda la configuración se gestiona a través del método `getContent()` en el archivo principal del módulo (`pga/index.php`).

### 4.3 Clases y Modelos Centrales (`classes/`)

El módulo utiliza el mecanismo de sobrescritura de PrestaShop para modificar el comportamiento central.

-   `pga/override/classes/Pack.php`

    -   **Nombre de la Clase:** `Pack` (sobrescribe la clase `Pack` de PrestaShop)
    -   **Responsabilidad:** Esta sobrescritura probablemente modifica cómo se manejan los paquetes de productos, específicamente en relación con la visibilidad y el acceso del producto. Asegura que si un producto dentro de un paquete está restringido, el paquete mismo respete esas restricciones. Esto es crucial para mantener un control de acceso consistente para productos agrupados.
    -   **Métodos Clave (probablemente modificados/añadidos):** Métodos relacionados con `getPackProducts()` o `isPack()` podrían extenderse para filtrar productos basándose en las restricciones de `pga`.
-   `pga/override/classes/shop/Shop.php`

    -   **Nombre de la Clase:** `Shop` (sobrescribe la clase `Shop` de PrestaShop)
    -   **Responsabilidad:** Esta sobrescritura es menos común para módulos de acceso a productos y sugiere una integración más profunda. Podría usarse para asegurar que las restricciones de productos se apliquen correctamente en diferentes tiendas en un entorno multi-tienda, o para modificar cómo se recuperan los datos de los productos a un nivel muy fundamental, afectando potencialmente las consultas de productos.
    -   **Métodos Clave (probablemente modificados/añadidos):** Métodos como `getProducts()` o `getProductById()` podrían extenderse para filtrar resultados basándose en las reglas de `pga` antes de que sean devueltos por el contexto de `Shop`.

### 4.4 Activos JavaScript (`views/js/`)

-   `pga/views/js/pga.js`
    -   **Alcance:** Back-office.
    -   **Propósito:** Este script es probablemente responsable de mejorar la experiencia del usuario en la página de configuración del módulo. Podría manejar llamadas AJAX para la búsqueda de productos, actualizaciones dinámicas de la tabla de restricciones de productos o validación del lado del cliente para el formulario de configuración.
    -   **Funcionalidad Clave:**
        -   Escuchadores de eventos para campos de entrada de búsqueda de productos (por ejemplo, eventos `keyup` para activar sugerencias AJAX).
        -   Solicitudes AJAX a un endpoint del módulo (a través de `AdminController` o `index.php?fc=module&module=pga&controller=ajax`) para obtener datos de productos o guardar restricciones.
        -   Manipulación del DOM para mostrar resultados de búsqueda, añadir productos seleccionados a la lista de restricciones o actualizar mensajes.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `pga/views/css/pga.css`
    -   **Alcance:** Back-office.
    -   **Propósito:** Proporciona estilos para la interfaz de configuración del módulo en el Back Office de PrestaShop.
    -   **Componentes Principales de la UI:** Estilos para el campo de búsqueda de productos, la tabla de restricciones de productos, botones y cualquier elemento personalizado introducido por el método `getContent()` del módulo.
    -   **Selectores de Clases CSS Clave:** Los desarrolladores pueden inspeccionar la salida HTML del módulo en el Back Office para identificar clases específicas (por ejemplo, `.pga-product-search`, `.pga-restriction-table`) para posibles sobrescrituras si se requiere un estilo de tema de administración personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Todas las plantillas son para la configuración del Back Office.

-   `pga/views/templates/admin/AdminTab.tpl`

    -   **Propósito:** Esta plantilla es probablemente un envoltorio genérico o una plantilla parcial utilizada dentro de la vista de configuración principal. Podría definir la estructura para una interfaz con pestañas o un encabezado/pie de página común para las páginas de administración.
-   `pga/views/templates/admin/csv.tpl`

    -   **Propósito:** Sugiere funcionalidad relacionada con la importación/exportación CSV de restricciones de productos. Esta plantilla renderizaría la interfaz para subir un archivo CSV o generar uno.
-   `pga/views/templates/admin/csv_file.tpl`

    -   **Propósito:** Una subplantilla o parcial utilizada por `csv.tpl`, posiblemente para mostrar un formulario de carga de archivos o una lista de archivos CSV.
-   `pga/views/templates/admin/customerGroups.tpl`

    -   **Propósito:** Esta plantilla es crucial para la funcionalidad "Seleccionar Grupos de Clientes". Renderiza la lista de grupos de clientes con casillas de verificación o un menú desplegable de selección múltiple, permitiendo al administrador elegir qué grupos están permitidos para un producto específico.
-   `pga/views/templates/admin/main.tpl`

    -   **Propósito:** Esta es la plantilla principal para la página de configuración del módulo (renderizada por `getContent()`). Orquesta todas las demás parciales y muestra la configuración general, la tabla de restricciones de productos y los formularios para añadir/editar restricciones.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo almacena su configuración en la tabla `ps_configuration` de PrestaShop para ajustes generales (por ejemplo, `PGA_ENABLED`, `PGA_BLOCK_VIEW`, `PGA_HIDE_LISTS`, `PGA_MESSAGE`).
    -   Para restricciones específicas de productos, el módulo probablemente crea una tabla de base de datos personalizada (por ejemplo, `ps_pga_product_group`) para almacenar el mapeo entre `id_product` e `id_group`. El método `install()` en `pga/index.php` definiría esta tabla.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para cargar CSS/JS específicos del módulo para la visualización del front-office (por ejemplo, si un mensaje personalizado necesita estilo) o para realizar comprobaciones tempranas para la redirección de la página del producto. |
| `displayRightColumn` / `displayLeftColumn` | En la barra lateral derecha/izquierda de las páginas del front-office. | Menos probable para este módulo, pero podría usarse para mostrar un bloque personalizado (por ejemplo, "Iniciar sesión para acceso exclusivo") si está configurado. |
| `displayProductButtons` / `displayProductActions` (o hooks similares de página de producto) | En la página del producto, cerca del botón Añadir al Carrito. | Se utiliza para ocultar o deshabilitar el botón "Añadir al Carrito" para usuarios no autorizados, o para mostrar el mensaje de restricción personalizado. |
| `displayFooter` | En el pie de página de cada página del front-office. | Menos común para la funcionalidad principal, pero podría usarse para scripts de carga tardía o análisis relacionados con el acceso a productos. |
| `actionCartSave` / `actionObjectCartAddAfter` (o hooks similares de carrito) | Cuando se añade o guarda un producto en el carrito. | **CRÍTICO:** Aquí es donde el módulo intercepta el proceso del carrito para verificar si el producto añadido está restringido para el grupo de clientes actual. Si está restringido, impide la adición o marca el artículo como inválido, mostrando el mensaje personalizado. |
| `actionProductListOverride` (o hooks similares de listado de productos) | Cuando PrestaShop genera una lista de productos (por ejemplo, página de categoría, resultados de búsqueda). | **CRÍTICO:** Se utiliza para filtrar productos restringidos de las listas de productos si "Ocultar producto en listas de productos" está habilitado. |
| `actionDispatcherBefore` / `actionFrontControllerSetMedia` | Antes de que se despache un controlador frontal o antes de que se establezcan los activos multimedia. | Podría usarse para implementar la lógica de redirección para "Bloquear posibilidad de ver página de producto" verificando el ID del producto solicitado contra las restricciones. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Acceso a Productos", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener.
