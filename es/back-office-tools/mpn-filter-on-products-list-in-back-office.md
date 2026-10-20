---
title: "Filtro MPN en la lista de productos del back office - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Filtro MPN en la lista de productos del back office' de MyPresta.eu."
sidebar:
  label: "Filtro MPN en la lista de productos del back office - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo MPN filter on products list in back office en MyPresta.eu](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# Filtro MPN en la lista de productos del back office

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo está diseñado para ser plug-and-play. No tiene una pantalla de configuración dedicada con ajustes para ajustar. Tras la instalación, el módulo integra automáticamente la columna MPN y las capacidades de filtrado en su lista de productos.

Verá un botón estándar de "Configuración" después de la instalación, pero al hacer clic en él, normalmente se mostrará un mensaje simple que indica que el módulo está activo y no requiere más configuración.

**Cómo usar el módulo después de la instalación:**

1. Navegue a **Catálogo > Productos** en el back office de PrestaShop.
2. Ahora verá una nueva columna etiquetada como "MPN" en su lista de productos.
3. Puede hacer clic en el encabezado de la columna "MPN" para ordenar sus productos por MPN en orden ascendente o descendente.
4. Encima de la lista de productos, en la sección de filtro, encontrará un nuevo campo de entrada debajo de la columna "MPN". Puede escribir un MPN (o parte de un MPN) en este campo y presionar Enter o hacer clic en el botón "Filtrar" para filtrar su lista de productos por ese MPN.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | (Sin ajustes configurables) | N/A | El módulo funciona automáticamente tras la instalación, añadiendo la columna MPN y el filtro a Catálogo > Productos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo la columna MPN en mi lista de productos.**
R: Primero, asegúrese de que está viendo la página "Catálogo > Productos" en su back office de PrestaShop. Si aún no es visible, intente borrar la caché de PrestaShop:
1. Vaya a **Parámetros avanzados > Rendimiento**.
2. Haga clic en "Borrar caché" en la esquina superior derecha.
3. Además, borre la caché de su navegador.
4. Si el problema persiste, asegúrese de que el módulo esté habilitado en el Gestor de módulos.

**P: ¿Puedo usar este módulo para añadir MPN al front office para los clientes?**
R: No, este módulo es estrictamente para la administración del back office. No modifica el front office ni muestra los MPN a los clientes. Necesitaría un módulo separado o un desarrollo personalizado para la visualización de MPN en el front office.

**P: ¿Este módulo crea nuevos campos de base de datos para MPN?**
R: No, PrestaShop ya tiene un campo `mpn` en la tabla `ps_product`. Este módulo simplemente hace que ese campo existente sea visible y filtrable en la lista de productos del back office. No añade nuevas tablas o campos de base de datos.

**P: El filtro no funciona o la columna no se ordena correctamente.**
R: Esto podría ser un problema de caché o un conflicto con otro módulo que modifica la lista de productos.
1. Borre la caché de PrestaShop (como se describe anteriormente).
2. Si tiene otros módulos que personalizan en gran medida la página "Catálogo > Productos", intente deshabilitarlos temporalmente uno por uno para identificar un conflicto.
3. Asegúrese de que su versión de PrestaShop sea totalmente compatible con la versión del módulo que descargó.

**P: ¿Cómo introduzco o edito el MPN de un producto?**
R: Edita el MPN directamente en la página de edición del producto:
1. Vaya a **Catálogo > Productos**.
2. Haga clic en "Editar" junto al producto que desea modificar.
3. Navegue a la pestaña "Cantidades" (o "Ajustes básicos" en versiones anteriores).
4. Allí encontrará el campo "MPN (Número de Pieza del Fabricante)". Introduzca o actualice el valor y guarde el producto. El nuevo MPN aparecerá entonces en la lista de productos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Filtro MPN en la lista de productos del back office" es un módulo ligero de PrestaShop diseñado principalmente para extender la funcionalidad existente de la lista de productos del Back Office. Lo logra sobrescribiendo plantillas Twig específicas responsables de renderizar la página del catálogo de productos en PrestaShop 1.7.x, 8.x y 9.x. No introduce nuevos controladores, modelos o activos complejos de JavaScript/CSS. Su función principal es inyectar la columna MPN y su filtro asociado en la vista estándar de la lista de productos.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda su funcionalidad se logra a través de sobrescrituras de plantillas y los mecanismos de módulo centrales de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase PHP personalizada o definiciones de `ObjectModel`. Aprovecha el `ObjectModel` `Product` existente y su campo `mpn`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La funcionalidad de filtrado y ordenación para la nueva columna MPN es manejada por la implementación existente de DataTables.js de PrestaShop para la lista de productos, que se adapta automáticamente a las nuevas columnas.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo de la nueva columna MPN y el campo de filtro heredarán directamente del tema de su back office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El mecanismo principal del módulo es sobrescribir las plantillas Twig del Back Office de PrestaShop para inyectar la columna MPN.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**:
  - **Propósito**: Esta plantilla es una sobrescritura directa de la plantilla de lista de productos principal de PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` o una ruta similar dependiendo de la versión de PS).
  - **Funcionalidad**: Modifica la estructura de la lista de productos para incluir el encabezado de la columna MPN y el campo de entrada de filtro correspondiente. Asegura que el campo MPN sea reconocido como una columna ordenable y filtrable dentro de la configuración de DataTables.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**:
  - **Propósito**: Esta plantilla es una sobrescritura directa de la plantilla de tabla de productos principal de PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` o una ruta similar).
  - **Funcionalidad**: Modifica las filas de la tabla para mostrar el valor MPN real de cada producto en la columna recién añadida. Accede a la propiedad `product.mpn` de los datos del producto pasados a la plantilla.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla nueva en la base de datos. Se basa en la columna `mpn` existente dentro de la tabla `ps_product` (o `ps_product_shop` para MPN específicos de la tienda, aunque normalmente está en `ps_product`).
- **Tabla de hooks registrados**: Este módulo no registra explícitamente ningún hook nuevo. Su funcionalidad se logra a través de sobrescrituras de plantillas. Aunque no utiliza `displayHeader`, `displayRightColumn`, `actionValidateOrder`, etc., en su método `install()`, es probable que se registre para sobrescrituras de plantillas, lo cual es una forma implícita de engancharse al proceso de renderizado.

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier consulta relacionada con el módulo "Filtro MPN en la lista de productos del back office", consulte su cuenta de cliente de MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.

- **Historial de pedidos y descargas de MyPresta.eu**: <https://mypresta.eu/my-account/orders/>
- **Contacto de soporte de MyPresta.eu**: <https://mypresta.eu/contact>
