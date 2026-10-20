---
title: "Rango de precios de productos - desde / hasta - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Rango de precios de productos - desde / hasta' de MyPresta.eu."
sidebar:
  label: "Rango de precios de productos - desde / hasta - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product price range - from / to en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-price-range-from-to/)
>
> ---


# Rango de precios de productos - desde / hasta

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes para los módulos de PrestaShop. No se requieren requisitos de alojamiento especiales más allá de un entorno estándar compatible con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, navegue a **Módulos > Gestor de módulos** y haga clic en "Configurar" junto a "Rango de precios de productos - desde / hasta". Se le presentará la pantalla de configuración principal.

#### Ajustes generales

Esta sección controla el comportamiento principal del módulo.

- **Mostrar rango de precios en la lista de productos:**

  - **Qué hace este ajuste:** Este interruptor determina si el rango "desde [precio más bajo] hasta [precio más alto]" se muestra en las páginas que listan varios productos, como páginas de categoría, resultados de búsqueda o módulos como "Nuevos productos" o "Productos destacados".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Los productos con combinaciones y precios variables mostrarán un rango de precios en todas las páginas de listado de productos.
    - *Cuando está deshabilitado (NO):* Solo se mostrará un precio único (normalmente el precio base o el precio de combinación más bajo) en las páginas de listado de productos, según el comportamiento predeterminado de PrestaShop.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si vende camisetas que cuestan 10 € para la talla pequeña y 15 € para la talla grande, habilitar esto mostrará "desde 10,00 € hasta 15,00 €" en la página de categoría de sus camisetas, dando a los clientes una visión rápida de las opciones de precios.
- **Mostrar rango de precios en la página del producto:**

  - **Qué hace este ajuste:** Este interruptor controla si el rango de precios se muestra en la propia página de producto individual, normalmente cerca del área principal del precio del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* La página del producto mostrará el rango de precios para productos con combinaciones, informando al cliente de las variaciones de precio antes de que seleccione las opciones.
    - *Cuando está deshabilitado (NO):* La página del producto solo mostrará un precio único (normalmente el precio base o el precio de combinación más bajo), según el comportamiento predeterminado de PrestaShop.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** En la página de producto de un ordenador a medida, habilitar esto mostrará "desde 800,00 € hasta 2500,00 €" antes de que el cliente empiece a seleccionar opciones de CPU, RAM y almacenamiento, estableciendo expectativas claras.
- **Tener en cuenta los descuentos por cantidad:**

  - **Qué hace este ajuste:** Esta configuración crucial determina si el módulo debe considerar cualquier reducción de precio basada en la cantidad (precios específicos para cantidades) al calcular el precio *más bajo* en el rango.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* El módulo calculará el precio más bajo posible, incluyendo cualquier descuento por cantidad, para la parte "desde" del rango. Por ejemplo, si un producto cuesta 10 €, pero 8 € si compra 10 unidades, el precio "desde" será 8 €.
    - *Cuando está deshabilitado (NO):* Los descuentos por cantidad se ignorarán, y el precio "desde" se basará únicamente en el precio de combinación más bajo sin considerar los ahorros por compra al por mayor.
  - **Valor recomendado:** SÍ (para asegurar que se muestre el precio más bajo más atractivo y preciso).
  - **Escenario / ejemplo de comerciante:** Si vende bolígrafos a 1 € cada uno, pero los ofrece a 0,80 € si se compran en paquetes de 100, habilitar esto asegurará que el precio "desde" en su lista de productos refleje 0,80 €, haciendo que el producto parezca aún más asequible.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar rango de precios en la lista de productos | SÍ | Muestra el precio "desde/hasta" en las páginas de categoría, búsqueda y listado. |
| Configuración del módulo | Mostrar rango de precios en la página del producto | SÍ | Muestra el precio "desde/hasta" en la página de detalles del producto individual. |
| Configuración del módulo | Tener en cuenta los descuentos por cantidad | SÍ | Incluye las reducciones de precio basadas en la cantidad al calcular el precio más bajo en el rango. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El rango de precios no aparece en mis páginas de producto/listados.**
R:

1. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos > Rango de precios de productos - desde / hasta > Configurar**. Asegúrese de que "Mostrar rango de precios en la lista de productos" y "Mostrar rango de precios en la página del producto" estén ambos configurados en **SÍ**.
2. **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
3. **Combinaciones de productos:** ¿El producto realmente tiene combinaciones con precios *diferentes*? Si todas las combinaciones tienen el mismo precio, el módulo probablemente mostrará un precio único ya que no hay un rango que mostrar.
4. **Compatibilidad del tema:** Si bien el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados pueden requerir pequeños ajustes. Si el problema persiste después de verificar lo anterior, póngase en contacto con el soporte de MyPresta.eu.

**P2: El precio "desde" no parece incluir mis descuentos por cantidad.**
R:

1. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos > Rango de precios de productos - desde / hasta > Configurar**. Asegúrese de que "Tener en cuenta los descuentos por cantidad" esté configurado en **SÍ**.
2. **Verifique los descuentos por cantidad:** Vuelva a verificar que sus descuentos por cantidad (precios específicos) estén configurados correctamente para el producto y sus combinaciones en el back office de PrestaShop.
3. **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios en la configuración.

**P3: El rango de precios se ve un poco extraño o desalineado con el diseño de mi tema.**
R:
El módulo intenta integrarse sin problemas, pero cada tema es único.

1. **Borrar caché:** A veces, los problemas de estilo se deben a archivos antiguos en caché.
2. **CSS personalizado:** Es posible que deba agregar algo de CSS personalizado a su tema para ajustar la apariencia. Las clases CSS del módulo suelen estar bien definidas (consulte la Sección 7.5). Un webmaster puede ayudarle a apuntar a estas clases para que coincidan con su tema.
3. **Contactar con soporte:** Si no se siente cómodo con CSS, el soporte de MyPresta.eu a menudo puede brindarle orientación o pequeños fragmentos de CSS para ayudarle.

**P4: ¿Este módulo ralentizará mi tienda?**
R:
El módulo está optimizado para el rendimiento. Calcula los precios de manera eficiente. Si bien cualquier módulo agrega una pequeña sobrecarga, este está diseñado para ser ligero. Si nota ralentizaciones significativas, asegúrese de que su servidor cumpla con las especificaciones recomendadas de PrestaShop y de que otros módulos no estén causando conflictos. Borrar la caché regularmente también ayuda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo "Rango de precios de productos - desde / hasta" (`prange`) es un módulo estándar de PrestaShop que sigue el patrón MVC. Opera principalmente mediante la conexión a varios puntos de visualización (`displayProductPriceBlock`, `displayProductListReviews`, etc.) para inyectar su rango de precios calculado. La lógica central reside en el archivo principal `index.php`, que actúa como punto de entrada del módulo y maneja la configuración, instalación y registro de hooks. Aprovecha las clases `Product` y `SpecificPrice` de PrestaShop para calcular el rango de precios, incluidos los descuentos por cantidad.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front-office o back-office. Toda la lógica está encapsulada dentro de la clase principal del módulo y se ejecuta a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define clases personalizadas ni extiende `ObjectModel`. Todas las manipulaciones de datos y cálculos de precios necesarios se realizan utilizando las clases nativas `Product` y `SpecificPrice` de PrestaShop dentro del archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Alcance:** Front-office (Página de producto)
  - **Propósito:** Este script probablemente contiene lógica para ocultar o modificar la visualización predeterminada del precio del producto en la página de producto individual cuando el rango de precios del módulo está activo. Podría escuchar los cambios del DOM o los eventos de carga de la página para asegurar que el rango del módulo sea el precio principal mostrado.
- **`prange/views/js/prange-hide-pl.js`**
  - **Alcance:** Front-office (Páginas de listado de productos)
  - **Propósito:** Similar a `prange-hide-p.js`, pero se dirige específicamente a las páginas de listado de productos (categorías, resultados de búsqueda). Está diseñado para ocultar o ajustar la visualización del precio único predeterminado en estas páginas para dar paso al rango de precios del módulo.
- **`prange/views/js/prange.js`**
  - **Alcance:** Front-office
  - **Propósito:** Este es probablemente el archivo JavaScript principal del módulo. Podría contener:
    - Lógica para actualizar dinámicamente el rango de precios si los atributos del producto se cambian a través de AJAX (por ejemplo, seleccionando una combinación).
    - Escuchadores de eventos para eventos `prestashop.on` relacionados con actualizaciones de datos de productos.
    - Cualquier renderizado o manipulación del lado del cliente requerido para la visualización del rango de precios.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Alcance:** Estilo del cliente del Front-office.
  - **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilo proporciona la presentación visual predeterminada para el texto del rango de precios. Definirá estilos para el contenedor que contiene el texto "desde/hasta", tamaños de fuente, colores, márgenes y, potencialmente, ajustes responsivos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores deben inspeccionar el HTML renderizado para identificar las clases específicas (por ejemplo, `.prange-price-range`, `.prange-from`, `.prange-to`) utilizadas por el módulo. Estas se pueden luego dirigir en el `custom.css` o `theme.css` de un tema personalizado para ajustar la apariencia.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**: Este módulo no define explícitamente plantillas en un subdirectorio `hook/` según el inventario proporcionado, pero las plantillas que se enumeran a continuación se renderizan efectivamente a través de hooks.
- **Plantillas de administración (`views/templates/admin/`)**: Este módulo no tiene plantillas de administración personalizadas más allá del formulario `getContent()` estándar.
- **Plantillas de front-office (`views/templates/front/`)**:
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Propósito:** Esta plantilla se utiliza probablemente cuando un producto *no* tiene combinaciones con precios variables, o cuando el módulo determina que solo se debe mostrar un precio único (por ejemplo, si los precios "desde" y "hasta" son idénticos). Asegura un formato consistente incluso para productos de precio único si el módulo está activo.
    - **Renderizado a través de:** Probablemente enganchado a `displayProductPriceBlock` o similar.
  - **`prange/views/templates/prange.tpl`**
    - **Propósito:** Esta es la plantilla principal para mostrar el rango real "desde [precio más bajo] hasta [precio más alto]". Recibe los precios más bajos y más altos calculados de la lógica PHP del módulo y los formatea para su visualización.
    - **Renderizado a través de:** Esta plantilla se renderizará cuando el módulo se enganche a `displayProductPriceBlock` (para la página del producto) y potencialmente a otros hooks para las páginas de listado de productos (por ejemplo, `displayProductListReviews`, `displayProductPriceBlock` en el contexto de la lista de productos, o anulando las plantillas principales).

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea tablas SQL personalizadas.
  - Almacena sus configuraciones (por ejemplo, `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) en la tabla estándar `ps_configuration`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para incluir los archivos CSS (`prange.css`) y JavaScript (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) del módulo para el estilo y la funcionalidad del front-office. |
| `displayProductPriceBlock` | Renderiza contenido dentro del bloque de precio del producto en las páginas de producto y, potencialmente, en los listados de productos. | Este es el hook principal para inyectar el rango de precios calculado en la visualización del precio del producto. El módulo probablemente verifica el parámetro `type` de este hook para determinar el contexto (página de producto vs. lista). |
| `displayProductListReviews` | Renderiza contenido cerca de las reseñas de productos en las páginas de listado de productos. | Aunque nombrado para reseñas, este hook es a menudo utilizado por los módulos para inyectar información adicional (como rangos de precios) en los elementos de la lista de productos. |
| `displayProductExtraContent` | Renderiza bloques de contenido extra en la página del producto. | Podría usarse como una ubicación alternativa o complementaria para el rango de precios en la página del producto. |
| `displayAfterProductThumbs` | Renderiza contenido después de las imágenes en miniatura del producto en la página del producto. | Otra ubicación potencial para mostrar el rango de precios en la página del producto. |
| `displayProductButtons` | Renderiza contenido cerca de los botones de acción del producto (por ejemplo, Añadir al carrito). | Menos probable para el rango de precios, pero posible para información contextual. |
| `displayFooterProduct` | Renderiza contenido en la sección del pie de página de la página del producto. | Una ubicación alternativa o de respaldo para el rango de precios en la página del producto. |
| `displayProductAdditionalInfo` | Renderiza información adicional en la página del producto. | Un hook común para inyectar detalles de productos personalizados. |
| `displayProductPrice` | Renderiza el precio del producto en sí. | Este hook es a menudo anulado o extendido por módulos que modifican la visualización del precio. |
| `actionProductUpdate` | Se ejecuta después de que un producto se actualiza en el back office. | Podría usarse para borrar cachés específicos del módulo o reindexar rangos de precios si el módulo mantuviera su propia caché. |
| `actionProductAdd` | Se ejecuta después de que se agrega un nuevo producto. | Similar a `actionProductUpdate`. |
| `actionProductDelete` | Se ejecuta después de que se elimina un producto. | Similar a `actionProductUpdate`. |

*Nota: Los hooks exactos utilizados pueden variar ligeramente entre las versiones del módulo y las versiones de PrestaShop. La lista anterior representa los hooks comunes para la funcionalidad de este módulo según su descripción.*

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, correcciones de errores y soporte dedicado para desarrolladores para el módulo "Rango de precios de productos - desde / hasta", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Asegúrese de estar ejecutando la última versión del módulo para un rendimiento y compatibilidad óptimos con su tienda PrestaShop.
