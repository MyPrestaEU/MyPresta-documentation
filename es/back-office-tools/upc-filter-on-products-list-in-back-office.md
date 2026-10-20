---
title: "Filtro UPC en la lista de productos en el back office - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Filtro UPC en la lista de productos en el back office' de MyPresta.eu."
sidebar:
  label: "Filtro UPC en la lista de productos en el back office - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo UPC filter on products list in back office en MyPresta.eu](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# Filtro UPC en la lista de productos en el back office

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo está diseñado para ser plug-and-play. No tiene una pantalla de configuración dedicada con ajustes para ajustar. Una vez instalado, el módulo integra automáticamente la columna y el filtro UPC en su lista de productos en el back office.

Encontrará la nueva funcionalidad navegando a:
**Back Office > Catálogo > Productos**

En esta página, ahora verá:

- Una nueva columna etiquetada como "UPC" que muestra el código UPC de cada producto.
- Un nuevo campo de filtro en la parte superior de la columna "UPC", que le permite escribir un código UPC (o parte de uno) para filtrar la lista de productos.

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo la columna UPC ni el filtro en mi lista de productos.**
R:
\* **Borrar caché:** La solución más común es borrar la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
\* **Verificar estado del módulo:** Asegúrese de que el módulo esté habilitado. Vaya a **Módulos > Gestor de módulos**, busque "Filtro UPC en la lista de productos en el back office" y verifique que esté activo.
\* **Compatibilidad con el tema:** Aunque es raro para los módulos de back office, un tema de administración altamente personalizado *podría* interferir. Si borrar la caché no funciona, cambie temporalmente al tema de administración predeterminado de PrestaShop para ver si aparece la columna.
\* **Posición del módulo:** Este módulo modifica las plantillas existentes. Asegúrese de que el módulo esté correctamente instalado y no muestre ningún error durante la instalación.

**P: La columna UPC está ahí, pero algunos productos no muestran un UPC.**
R: Este módulo simplemente muestra el código UPC que ya está almacenado en la información de su producto. Si un producto no muestra un UPC, significa que el campo UPC para ese producto específico en su catálogo de PrestaShop está vacío. Deberá editar el producto (Catálogo > Productos > Editar producto > pestaña Cantidades) e introducir el código UPC allí.

**P: ¿Puedo cambiar la posición de la columna UPC?**
R: El módulo integra la columna UPC en una posición específica dentro de la tabla de la lista de productos. No hay una opción de configuración dentro del módulo para cambiar su posición. Esto requeriría modificaciones personalizadas de la plantilla (consulte la Guía del desarrollador).

**P: ¿Este módulo añade campos UPC a los productos si no existen?**
R: No, este módulo asume que su instalación de PrestaShop ya tiene el campo UPC estándar disponible para los productos (lo cual hace por defecto). Solo muestra y filtra basándose en los datos que ya ha introducido en ese campo.

**P: ¿Este módulo ralentizará mi back office?**
R: El módulo está altamente optimizado. Aprovecha los mecanismos de filtrado existentes de PrestaShop y solo añade una simple visualización de columna. No debería afectar notablemente el rendimiento de la lista de productos de su back office.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Filtro UPC en la lista de productos en el back office".

### 4.1 Resumen de la arquitectura

El módulo funciona principalmente anulando plantillas Twig específicas utilizadas para la lista del catálogo de productos en el back office de PrestaShop. Inyecta el HTML necesario para el encabezado de la columna UPC y la entrada del filtro, y luego modifica la plantilla de la fila del producto para mostrar el valor UPC. La lógica de filtrado es manejada por el controlador nativo `AdminProducts` de PrestaShop, que reconoce automáticamente el campo `upc` para filtrar una vez que está presente en la plantilla.

### 4.2 Controladores (`controllers/`)

Este módulo **no** introduce ningún controlador personalizado de front office o back office. Su funcionalidad se logra a través de anulaciones de plantillas y aprovechando la lógica del controlador existente de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** introduce ninguna clase PHP personalizada o definiciones de `ObjectModel`. Interactúa directamente con los datos de productos existentes de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. La funcionalidad de filtrado se maneja en el lado del servidor por el controlador `AdminProducts` de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado del back office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo utiliza el nuevo motor de plantillas Twig introducido en PrestaShop 1.7+ para las páginas del back office. Anula dos plantillas principales de la lista de productos:

- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

  - **Propósito:** Esta plantilla es responsable de renderizar la página principal del catálogo de productos, incluyendo el encabezado de la tabla y el formulario de búsqueda/filtro.
  - **Modificación:** El módulo inyecta un nuevo elemento `<th>` para la columna "UPC" en el encabezado de la tabla y un campo de entrada correspondiente para filtrar en el formulario de búsqueda. Esto permite que el campo `upc` sea reconocido por el controlador `AdminProducts` para filtrar.
- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

  - **Propósito:** Esta plantilla es responsable de renderizar las filas individuales de la tabla de la lista de productos.
  - **Modificación:** El módulo añade un nuevo elemento `<td>` dentro del bucle de productos para mostrar el valor `product.upc` para cada producto.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo **no** crea ninguna tabla de base de datos personalizada. Lee el campo `upc` de la tabla estándar `ps_product`.
- **Tabla de Hooks registrados**: Este módulo **no** registra ningún hook específico en el sentido tradicional de PrestaShop (por ejemplo, `displayHeader`, `actionValidateOrder`). Su integración se logra puramente a través de anulaciones de plantillas Twig, que son una forma de "enganche" implícito en el proceso de renderizado.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Filtro UPC en la lista de productos en el back office", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.
"""
