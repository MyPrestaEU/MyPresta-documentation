---
title: "Product Grid Pro - columnas y diseño de productos en lista - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Product Grid Pro - columnas y diseño de productos en lista de MyPresta.eu."
sidebar:
  label: "Product Grid Pro - columnas y diseño de productos en lista"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product Grid Pro - columns & layout of list products en MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - columnas y diseño de productos en lista

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

Este módulo funciona principalmente anulando el controlador de lista de productos predeterminado de PrestaShop. Su configuración se gestiona principalmente directamente dentro de la sección "Catálogo > Productos" misma, con una sencilla opción de "restablecer" disponible en la configuración principal del módulo.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a esto, navegue a **Módulos > Gestor de módulos**, busque "Product Grid Pro" y haga clic en "Configurar".

Esta pantalla ofrece una única y crucial opción:

-   **Restablecer la configuración del módulo**
    -   **Qué hace este ajuste:** Este botón le permite revertir todos los cambios realizados por el módulo a su configuración predeterminada. Esto significa que cualquier orden de columna personalizado, visibilidad o columnas añadidas que haya configurado en la lista "Catálogo > Productos" se restablecerá al estado inicial del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Al hacer clic:* El módulo borrará sus preferencias almacenadas para el diseño de su cuadrícula de productos. Esto es útil si ha realizado muchos cambios y desea empezar de nuevo, o si encuentra un problema de visualización inesperado y desea descartar problemas de configuración.
    -   **Valor recomendado:** Solo haga clic en esto si desea restablecer explícitamente la personalización de su cuadrícula de productos.
    -   **Escenario / ejemplo de comerciante:** Ha estado experimentando con diferentes diseños de columnas durante meses, y ahora su lista de productos se siente desordenada o desorganizada. Al hacer clic en "Restablecer la configuración del módulo", volverá a un estado limpio y predeterminado, lo que le permitirá reconfigurarlo desde cero.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

La funcionalidad principal de "Product Grid Pro" se experimenta directamente dentro de la sección **Catálogo > Productos** de su Back Office de PrestaShop. Este módulo mejora la lista de productos estándar, añadiendo nuevas columnas y permitiéndole personalizar su diseño.

-   **Nombre de la pantalla y ubicación del menú:** **Catálogo > Productos**
-   **Acciones y ajustes disponibles:**
    -   **Nuevas columnas:** El módulo introduce varias columnas nuevas y muy útiles en su lista de productos. Estas incluyen:
        -   **EAN13:** Número de Artículo Europeo (código de barras).
        -   **Referencia del proveedor:** Su referencia interna para el producto de su proveedor.
        -   **Fabricante:** La marca o fabricante del producto.
        -   **Combinaciones:** Indica si el producto tiene variaciones (tallas, colores, etc.).
        -   **Unidades vendidas:** El número total de unidades de este producto vendidas.
        -   **Última venta:** La fecha en que se vendió la última unidad de este producto.
        -   **Peso:** El peso del producto.
        -   **Mayorista:** El precio al por mayor del producto.
        -   **Creado:** La fecha en que se añadió el producto a su catálogo.
        -   **Condición:** La condición del producto (Nuevo, Usado, Reacondicionado).
        -   **En oferta:** Indica si el producto está actualmente en oferta.
        -   **Disponible para pedido:** Si los clientes pueden comprar el producto actualmente.
        -   **Mostrar precio:** Si el precio del producto se muestra en el front office.
        -   **Solo online:** Indica si el producto solo está disponible online (no en tiendas físicas).
        -   **Visibilidad:** Dónde es visible el producto (Catálogo, Búsqueda, Ambos, Ninguno).
        -   **Virtual:** Indica si el producto es un producto virtual (por ejemplo, descarga, servicio).
        -   **Pack:** Indica si el producto es un pack de productos.
        -   **Indexado:** Si el producto está indexado para la búsqueda.
        -   **Personalizable:** Si el producto tiene campos de personalización.
        -   **Proveedor:** El proveedor específico asociado al producto.
    -   **Visibilidad de columnas:** Puede elegir cuáles de estas columnas nuevas y existentes son visibles en su lista de productos. Esto ayuda a despejar la vista y a centrarse en lo importante.
    -   **Orden de columnas (Arrastrar y soltar):** Puede reordenar fácilmente las columnas arrastrándolas y soltándolas en la secuencia que prefiera. Esto le permite organizar la información más crítica a la izquierda para un acceso rápido.
    -   **Filtrado y clasificación:** Cada una de las nuevas columnas admite el filtrado y la clasificación, al igual que las columnas predeterminadas de PrestaShop. Esto significa que puede, por ejemplo, ordenar productos por "Unidades vendidas" para ver sus productos más vendidos, o filtrar por "Fabricante" para gestionar productos de una marca específica.
-   **Efecto de los cambios:**
    -   **Añadir/Eliminar columnas:** Cambia directamente la información mostrada en su lista "Catálogo > Productos". Eliminar una columna oculta esos datos; añadir una los hace visibles.
    -   **Reordenar columnas:** Cambia el diseño visual de la lista de productos, permitiéndole priorizar la información.
    -   **Filtrar/Clasificar:** Le ayuda a localizar y analizar rápidamente grupos específicos de productos basándose en los criterios que establezca.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Identifique sus métricas clave:** ¿Qué información del producto consulta con más frecuencia? (por ejemplo, stock, precio, unidades vendidas, referencia del proveedor).
    2.  **Habilite las columnas esenciales:** Vaya a **Catálogo > Productos**, busque las opciones de personalización de columnas (a menudo un icono de engranaje o un botón "Columnas") y habilite solo las columnas que realmente necesite.
    3.  **Organice para la eficiencia:** Arrastre y suelte sus columnas más importantes al lado izquierdo de la cuadrícula para que sean inmediatamente visibles sin desplazamiento horizontal.
    4.  **Use filtros:** Al gestionar el stock, use el filtro "Unidades vendidas" para identificar artículos de baja rotación, o filtre por "Última venta" para encontrar productos que no se han vendido recientemente.
    5.  **Revise regularmente:** Revise periódicamente la configuración de sus columnas para asegurarse de que sigue satisfaciendo sus necesidades operativas.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de configuración del módulo | Restablecer configuración del módulo | N/A (botón) | Revierte todos los ajustes personalizados de la cuadrícula de productos (visibilidad, orden de columnas) a los valores predeterminados del módulo. Úselo para empezar de nuevo o solucionar problemas. |
| Cuadrícula de Catálogo > Productos | Columna EAN13 | Deshabilitado | Muestra el código de barras EAN13 para cada producto. Útil para inventario y escaneo. |
| Cuadrícula de Catálogo > Productos | Columna de referencia del proveedor | Deshabilitado | Muestra la referencia interna del proveedor para el producto. Esencial para la gestión de proveedores. |
| Cuadrícula de Catálogo > Productos | Columna Fabricante | Deshabilitado | Muestra el fabricante/marca del producto. Útil para la gestión específica de marcas. |
| Cuadrícula de Catálogo > Productos | Columna Combinaciones | Deshabilitado | Indica si un producto tiene combinaciones. Verificación rápida para productos complejos. |
| Cuadrícula de Catálogo > Productos | Columna Unidades vendidas | Deshabilitado | Muestra el total de unidades vendidas para cada producto. Ideal para identificar los más vendidos. |
| Cuadrícula de Catálogo > Productos | Columna Última venta | Deshabilitado | Muestra la fecha de la última venta de un producto. Ayuda a identificar stock de baja rotación. |
| Cuadrícula de Catálogo > Productos | Columna Peso | Deshabilitado | Muestra el peso del producto. Importante para los cálculos de envío. |
| Cuadrícula de Catálogo > Productos | Columna Mayorista | Deshabilitado | Muestra el precio al por mayor. Útil para cálculos de margen y tiendas B2B. |
| Cuadrícula de Catálogo > Productos | Columna Creado | Deshabilitado | Muestra la fecha en que se añadió el producto. Ayuda a rastrear el crecimiento del catálogo. |
| Cuadrícula de Catálogo > Productos | Columna Condición | Deshabilitado | Muestra la condición del producto (Nuevo, Usado, Reacondicionado). Relevante para ciertos tipos de productos. |
| Cuadrícula de Catálogo > Productos | Columna En oferta | Deshabilitado | Indica si el producto está actualmente en oferta. Resumen rápido de promociones. |
| Cuadrícula de Catálogo > Productos | Columna Disponible para pedido | Deshabilitado | Muestra si el producto se puede pedir. Esencial para la gestión de stock. |
| Cuadrícula de Catálogo > Productos | Columna Mostrar precio | Deshabilitado | Indica si el precio es visible en el front office. |
| Cuadrícula de Catálogo > Productos | Columna Solo online | Deshabilitado | Muestra si el producto es exclusivo para ventas online. |
| Cuadrícula de Catálogo > Productos | Columna Visibilidad | Deshabilitado | Muestra dónde es visible el producto (catálogo, búsqueda, ambos, ninguno). |
| Cuadrícula de Catálogo > Productos | Columna Virtual | Deshabilitado | Indica si el producto es virtual (descargable, servicio). |
| Cuadrícula de Catálogo > Productos | Columna Pack | Deshabilitado | Muestra si el producto es un pack de otros productos. |
| Cuadrícula de Catálogo > Productos | Columna Indexado | Deshabilitado | Indica si el producto está indexado para la búsqueda. |
| Cuadrícula de Catálogo > Productos | Columna Personalizable | Deshabilitado | Muestra si el producto tiene opciones de personalización. |
| Cuadrícula de Catálogo > Productos | Columna Proveedor | Deshabilitado | Muestra el proveedor principal del producto. |
| Cuadrícula de Catálogo > Productos | Orden de columnas (Arrastrar y soltar) | N/A (definido por el usuario) | Personalice la secuencia visual de las columnas para un flujo de trabajo óptimo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: He habilitado nuevas columnas, pero no aparecen en la lista de productos.**
R1: Después de habilitar las columnas, asegúrese de guardar los cambios (si hay un botón de guardar en la interfaz de personalización de columnas). A veces, borrar la caché de su navegador o la caché de Smarty de PrestaShop puede ayudar. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.

**P2: La reordenación por arrastrar y soltar no funciona, o el diseño se ve extraño.**
R2: Esto podría ser un conflicto de JavaScript con otro módulo o su tema.
    1.  Intente borrar la caché de su navegador y la caché de Smarty de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).
    2.  Si el problema persiste, intente hacer clic en el botón "Restablecer la configuración del módulo" en la página de configuración del módulo (**Módulos > Gestor de módulos > Product Grid Pro > Configurar**). Esto revertirá el diseño a los valores predeterminados y podría resolver el conflicto.
    3.  Si sigue siendo problemático, deshabilite temporalmente otros módulos que también modifiquen la lista de productos o la interfaz de administración para identificar un conflicto.

**P3: ¿Puedo añadir aún más campos personalizados a la cuadrícula de productos?**
R3: Este módulo proporciona un conjunto predefinido de campos comúnmente solicitados. No ofrece una forma genérica de añadir *cualquier* campo personalizado que haya podido crear (por ejemplo, con otro módulo de campos personalizados). Si necesita un campo personalizado muy específico, requeriría un desarrollo personalizado adicional.

**P4: ¿Este módulo ralentizará mi Back Office?**
R4: El módulo está diseñado para ser eficiente. Si bien añadir muchas columnas significa que se cargan más datos, el impacto en el rendimiento es generalmente mínimo y se ve superado por las ganancias de eficiencia. Si nota ralentizaciones significativas, considere deshabilitar las columnas menos críticas para reducir los datos cargados.

**P5: El módulo está instalado, pero no veo ninguna opción nueva en Catálogo > Productos.**
R5: Asegúrese de que el módulo esté correctamente instalado y habilitado. A veces, después de la instalación, es posible que deba actualizar su navegador o incluso cerrar sesión y volver a iniciarla en el Back Office para que los cambios surtan efecto. Además, verifique si hay mensajes de error durante la instalación. Si está en PrestaShop 1.6, la interfaz para la personalización de columnas podría ser ligeramente diferente a la de 1.7/8/9.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Product Grid Pro".

### 4.1 Descripción general de la arquitectura

El módulo "Product Grid Pro" funciona principalmente anulando el `AdminProductsController` central de PrestaShop. Esta es una técnica común y potente en el desarrollo de módulos de PrestaShop, que permite a los módulos extender o modificar el comportamiento de las funcionalidades centrales sin alterar directamente los archivos centrales. El módulo inyecta columnas, filtros y capacidades de clasificación adicionales en la tabla de la lista de productos manipulando el array `$this->fields_list` dentro del controlador anulado. También utiliza un archivo JavaScript dedicado para manejar la reordenación de columnas por arrastrar y soltar y, potencialmente, otras mejoras dinámicas de la interfaz de usuario. La configuración se almacena en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce nuevos controladores de front-office. Su interacción principal es con el `AdminProductsController` del Back Office.

-   **Controladores de Front-Office**: Ninguno.
-   **Controladores de Administración del Back-Office**:
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Nombre de la clase y clase padre**: `AdminProductsController` (anula el `AdminProductsController` central).
        *   **Responsabilidad**: Este es el núcleo de la funcionalidad del módulo. Extiende la funcionalidad predeterminada de la lista de productos.
            *   Modifica el array `$this->fields_list` para añadir nuevas definiciones de columna (EAN13, Referencia del proveedor, Fabricante, Unidades vendidas, Última venta, Peso, Mayorista, Creado, Condición, En oferta, Disponible para pedido, Mostrar precio, Solo online, Visibilidad, Virtual, Pack, Indexado, Personalizable, Proveedor).
            *   Asegura que estos nuevos campos sean clasificables y filtrables.
            *   Maneja la lógica para recuperar los datos de estas nuevas columnas de la base de datos.
            *   Integra el JavaScript para la reordenación de columnas y la gestión de la visibilidad.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Nombre de la clase y clase padre**: Este archivo es probablemente un marcador de posición o un simple redireccionador dentro de la estructura de anulación y no contiene una definición completa de clase de controlador para una entidad específica. Su presencia en el directorio `override/controllers/admin/` sugiere que podría ser parte del mecanismo de anulación en sí, potencialmente asegurando que la anulación de `AdminProductsController.php` se cargue correctamente o manejando el contexto general de administración. En la mayoría de los casos, la lógica real reside en `AdminProductsController.php`.

### 4.3 Clases y modelos centrales (`classes/`)

Este módulo no define clases `ObjectModel` personalizadas. Interactúa directamente con los objetos `Product` y `Configuration` existentes de PrestaShop.

### 4.4 Recursos JavaScript (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Alcance**: Back-office (específicamente la página `Catálogo > Productos`).
    *   **Responsabilidad**:
        *   Maneja la manipulación dinámica de la tabla de la lista de productos en el Back Office de PrestaShop.
        *   Implementa la funcionalidad de arrastrar y soltar para reordenar columnas, permitiendo a los administradores personalizar el diseño.
        *   Gestiona la visibilidad de las columnas (mostrándolas/ocultándolas según las preferencias del usuario).
        *   Probablemente almacena y recupera las preferencias del usuario para el orden y la visibilidad de las columnas utilizando llamadas AJAX o almacenamiento local/cookies, que luego son utilizadas por el `AdminProductsController` anulado para renderizar la cuadrícula.
        *   Puede incluir escuchadores de eventos para elementos de la interfaz de usuario que controlan la selección de columnas (por ejemplo, un icono de engranaje o un menú desplegable para alternar columnas).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Alcance**: Back-office (específicamente la página `Catálogo > Productos`).
    *   **Responsabilidad**:
        *   Proporciona estilos para la cuadrícula de productos mejorada, asegurando que las nuevas columnas y los elementos de la interfaz de usuario (como los controladores de arrastre o los conmutadores de columna) se muestren correctamente y se integren sin problemas con el tema del Back Office de PrestaShop.
        *   Puede incluir estilos para indicadores de arrastrar y soltar, estados de columnas ocultas o anchos específicos para nuevas columnas.
        *   Selectores de clase CSS clave que los desarrolladores pueden anular en su tema: Busque clases con el prefijo `product-grid-pro` o similar, o clases específicas de encabezado/celda de tabla que puedan ser objetivo de estilos personalizados.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo no parece utilizar archivos `.tpl` personalizados según el inventario proporcionado. Esto sugiere que las modificaciones a la cuadrícula de productos se logran principalmente a través de PHP (en el controlador anulado) y JavaScript, que manipula dinámicamente la estructura HTML existente generada por las plantillas centrales de PrestaShop para el `AdminProductsController`. El módulo probablemente inyecta su JS y CSS a través de hooks como `displayBackOfficeHeader`.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    *   El módulo almacena principalmente sus ajustes de configuración (por ejemplo, orden de columna preferido, visibilidad) dentro de la tabla `ps_configuration`. Las claves de configuración normalmente tendrían el prefijo `MYPRODUCTGRIDPRO_` o similar.
    *   No crea nuevas tablas de base de datos personalizadas.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` del Back Office. | Se utiliza para incluir los recursos `product_grid_admin.js` y `product_grid_admin.css` del módulo, asegurando que se carguen en la página `AdminProductsController`. |
| `actionAdminProductsControllerSave` (o hooks `actionAdminController` similares) | Se ejecuta cuando un controlador de administración guarda datos. | Aunque no se lista explícitamente, el módulo podría usar tales hooks para guardar las preferencias de columna personalizadas (orden, visibilidad) en `ps_configuration` cuando un usuario administrador las modifica. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Se ejecuta antes de que se rendericen los campos de la lista de productos. | Este hook es crucial para los módulos que modifican el `$this->fields_list` del `AdminProductsController`. Permite al módulo añadir, eliminar o modificar definiciones de columna dinámicamente. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Se ejecuta después de que se recuperan los datos del producto pero antes de la renderización. | Permite al módulo modificar las filas de datos reales para las nuevas columnas (por ejemplo, calculando "Unidades vendidas" o "Última venta" si no están directamente disponibles en la consulta principal del producto). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Product Grid Pro - columnas y diseño de productos en lista", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
"""
