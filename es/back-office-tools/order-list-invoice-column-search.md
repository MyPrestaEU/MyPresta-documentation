---
title: "Columna y Búsqueda de Facturas en la Lista de Pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Columna y Búsqueda de Facturas en la Lista de Pedidos de MyPresta.eu."
sidebar:
  label: "Columna y Búsqueda de Facturas en la Lista de Pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order List Invoice Column & Search en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Columna y Búsqueda de Facturas en la Lista de Pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo "Columna y Búsqueda de Facturas en la Lista de Pedidos". Este módulo tiene una configuración muy simple y directa, ya que su funcionalidad principal es mejorar la lista de pedidos existente.

La página de configuración de "Columna y Búsqueda de Facturas en la Lista de Pedidos" es sencilla. Sirve principalmente para habilitar o deshabilitar la funcionalidad del módulo.

-   **Nombre del Ajuste:** Habilitar Columna y Búsqueda de Facturas
-   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar las características del módulo. Cuando está habilitado, el módulo añadirá la columna "Número de Factura" a su lista de pedidos e integrará la funcionalidad de búsqueda. Cuando está deshabilitado, su lista de pedidos volverá a su apariencia predeterminada de PrestaShop.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Aparecerá una nueva columna titulada "Número de Factura" en su Back Office bajo **Pedidos > Pedidos**. Esta columna mostrará el número de factura para cada pedido (si se ha generado una factura). Además, la barra de búsqueda en la página de Pedidos ahora le permitirá buscar por número de factura.
    -   *Cuando está deshabilitado (NO):* La columna "Número de Factura" se eliminará de la lista de pedidos y la capacidad de buscar por número de factura se desactivará. Su lista de pedidos se verá exactamente como antes de instalar este módulo.
-   **Valor recomendado:** **SÍ**. Para beneficiarse de las características del módulo, debe habilitarlo.
-   **Escenario / ejemplo de comerciante:** Si desea encontrar rápidamente todos los pedidos relacionados con una factura específica (por ejemplo, "INV00123"), habilitaría este ajuste. Luego, navegaría a **Pedidos > Pedidos**, escribiría "INV00123" en la barra de búsqueda y el sistema filtraría la lista para mostrar solo ese pedido. Si lo deshabilita, tendría que hacer clic manualmente en cada pedido para verificar su número de factura, lo cual consume mucho tiempo.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Columna y Búsqueda de Facturas | SÍ | Activa/desactiva la columna de factura y la funcionalidad de búsqueda en la lista de Pedidos en el Back Office. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He habilitado el módulo, pero no veo la columna "Número de Factura" o la búsqueda no funciona.**
R:

1.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, PrestaShop necesita una actualización de caché para mostrar nuevos elementos.
2.  **Verificar Estado del Módulo:** Verifique que el módulo esté realmente "Habilitado" en su página de configuración.
3.  **Versión de PrestaShop:** Asegúrese de que su versión de PrestaShop sea compatible con el módulo (1.7.x, 8.x, 9.x).
4.  **Caché del Navegador:** Intente borrar la caché de su navegador o usar una ventana de incógnito para descartar problemas específicos del navegador.

**P: Los números de factura muestran "N/A" o están vacíos para algunos pedidos.**
R: Esto generalmente significa que aún no se ha generado una factura para esos pedidos específicos en PrestaShop. El módulo solo muestra el número de factura si existe en la base de datos de PrestaShop. Deberá generar manualmente la factura para esos pedidos a través del proceso estándar de gestión de pedidos de PrestaShop.

**P: ¿Este módulo ralentizará mi Back Office?**
R: No, el módulo está diseñado para ser ligero y eficiente. Principalmente extiende una característica existente de PrestaShop (la lista de pedidos) en lugar de añadir nuevos procesos pesados. Su impacto en el rendimiento debería ser insignificante.

**P: ¿Puedo personalizar la posición de la columna "Número de Factura"?**
R: El módulo coloca la columna en una posición lógica dentro de la lista de pedidos. La personalización directa del orden de las columnas no es una característica incorporada de este módulo. Para cambios de diseño avanzados, normalmente necesitaría un desarrollo de tema personalizado u otro módulo especializado.

**P: ¿Este módulo crea nuevas facturas?**
R: No, este módulo no genera facturas. Solo muestra y permite buscar por números de factura que ya han sido generados por la funcionalidad principal de PrestaShop.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Columna y Búsqueda de Facturas en la Lista de Pedidos" (`olistinv`) es un módulo clásico de PrestaShop que extiende la funcionalidad principal al engancharse a los puntos de visualización y acción existentes dentro del Back Office. Principalmente modifica la vista de lista del controlador `AdminOrders` para añadir una nueva columna y mejora las capacidades de búsqueda sin introducir nuevas tablas de base de datos o interacciones complejas en el front-office. Su simplicidad radica en aprovechar el sistema de hooks de PrestaShop y anular la lógica de la plantilla cuando sea necesario.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda su lógica está contenida dentro del archivo principal del módulo, `olistinv/index.php`, y se ejecuta a través de hooks.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada u `ObjectModel`. Interactúa directamente con las clases principales y las estructuras de base de datos existentes de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La funcionalidad de búsqueda se integra modificando el comportamiento del formulario de búsqueda existente, que es manejado por el JS principal de PrestaShop.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. La nueva columna heredará el estilo de las tablas existentes del Back Office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Logra su funcionalidad inyectando dinámicamente contenido en las plantillas existentes de PrestaShop a través de hooks, específicamente modificando la visualización de la lista de `AdminOrders`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos nueva. Lee de la tabla `ps_orders` (específicamente el campo `invoice_number`) y potencialmente de `ps_order_invoice` para los detalles de la factura, y almacena su configuración en `ps_configuration`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Se renderiza antes del encabezado de la tabla de la lista de pedidos en el Back Office. | Se utiliza para añadir el encabezado de la columna "Número de Factura" a la lista de pedidos. |
| `displayAdminOrderList` | Se renderiza para cada fila (pedido) en la tabla de la lista de pedidos en el Back Office. | Se utiliza para mostrar el número de factura real de cada pedido en la columna recién añadida. |
| `actionAdminOrdersListingFieldsModifier` | Modifica el array de campos utilizado para construir la consulta y la visualización de la lista de pedidos. | Se utiliza para añadir el campo `invoice_number` a la lista de campos buscables y visualizables para el controlador `AdminOrders`. Esto es crucial tanto para mostrar la columna como para habilitar la búsqueda. |
| `actionAdminOrdersFilterModifier` | Modifica la consulta de filtro para la lista de pedidos. | Se utiliza para extender la funcionalidad de búsqueda para incluir el campo `invoice_number` cuando se envía una consulta de búsqueda. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Columna y Búsqueda de Facturas en la Lista de Pedidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad del módulo.
