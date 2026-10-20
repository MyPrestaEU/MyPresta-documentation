---
title: "Mostrar precios base (sin descuentos) - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Mostrar precios base (sin descuentos)' de MyPresta.eu."
sidebar:
  label: "Mostrar precios base (sin descuentos) - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Display base prices (without discounts) en MyPresta.eu](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/display-base-prices-without-discounts/)
>
> ---


# Mostrar precios base (sin descuentos)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Esta es la pantalla principal donde controla cómo y dónde se muestran los precios base.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar módulo** | Este es el interruptor principal para activar o desactivar la funcionalidad del módulo. | *Cuando está habilitado:* El módulo comenzará a mostrar los precios base en su front office según otras configuraciones. *Cuando está deshabilitado:* El módulo dejará de mostrar los precios base, y su tienda volverá a mostrar solo los precios actuales. | SÍ | Acaba de instalar el módulo y desea activar sus funciones. |
| **Mostrar en la página de producto** | Controla si el precio base se muestra en las páginas de detalles de productos individuales. | *Cuando está habilitado:* El precio original aparecerá junto al precio con descuento en la página de cada producto. *Cuando está deshabilitado:* El precio base no se mostrará en las páginas de producto, incluso si está habilitado en otro lugar. | SÍ | Desea que los clientes que ven un producto específico vean claramente los ahorros. |
| **Mostrar en las páginas de categoría** | Controla si el precio base se muestra en las páginas de listado de productos (por ejemplo, páginas de categoría, resultados de búsqueda). | *Cuando está habilitado:* El precio original aparecerá junto al precio con descuento para cada producto listado en categorías, resultados de búsqueda, etc. *Cuando está deshabilitado:* El precio base no se mostrará en las páginas de listado de productos. | SÍ | Desea que los clientes que navegan por categorías identifiquen rápidamente los artículos con descuento y sus ahorros. |
| **Mostrar en el resumen del carrito** | Controla si el precio base se muestra en el resumen del carrito de compras. | *Cuando está habilitado:* El precio original será visible para cada producto en el carrito de compras del cliente, reforzando los ahorros totales. *Cuando está deshabilitado:* Solo se mostrará el precio actual con descuento en el carrito. | NO (o SÍ, dependiendo del tema) | Desea recordar a los clientes sus ahorros totales antes de que procedan al pago. Sin embargo, algunos temas podrían no tener un área de visualización adecuada, o podría saturar el carrito. Pruebe a fondo. |
| **CSS personalizado para el precio base** | Le permite añadir reglas CSS personalizadas para estilizar el precio base mostrado. | *Cuando se rellena con CSS:* El precio base se estilizará según su entrada (por ejemplo, tamaño de fuente, color, tachado). *Cuando está vacío:* El módulo utilizará su estilo predeterminado o heredará los estilos de su tema. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Desea que el precio base aparezca en gris y tachado para diferenciarlo claramente del precio actual. |
| **Posición del precio base** | Determina dónde se inyecta el precio base en relación con el precio actual. | *Opciones: Antes del precio actual, Después del precio actual.* *Cuando se establece en 'Antes':* El precio base aparecerá a la izquierda del precio actual. *Cuando se establece en 'Después':* El precio base aparecerá a la derecha del precio actual. | Antes del precio actual | Desea que el cliente vea primero el precio original y luego el nuevo precio más bajo. |

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar módulo | SÍ | Activa/desactiva la funcionalidad principal del módulo. |
| Configuración del módulo | Mostrar en la página de producto | SÍ | Muestra el precio base en las páginas de productos individuales. |
| Configuración del módulo | Mostrar en las páginas de categoría | SÍ | Muestra el precio base en las páginas de listado de productos (categorías, búsqueda). |
| Configuración del módulo | Mostrar en el resumen del carrito | NO (o SÍ, probar) | Muestra el precio base en el carrito de compras. |
| Configuración del módulo | CSS personalizado para el precio base | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Personaliza el estilo visual del precio base. |
| Configuración del módulo | Posición del precio base | Antes del precio actual | Controla la ubicación en relación con el precio actual. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Los precios base no aparecen en mi tienda, aunque el módulo está habilitado.**
R:

1.  **Verifique la configuración del módulo:** Asegúrese de que "Habilitar módulo" y las opciones de visualización específicas (por ejemplo, "Mostrar en la página de producto") estén configuradas en SÍ.
2.  **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A menudo es necesario borrar la caché de Smarty para que aparezcan los cambios en la plantilla.
3.  **Verifique los descuentos:** Asegúrese de que los productos que está probando realmente tengan descuentos activos (reglas de precio de catálogo, precios específicos o reducciones porcentuales) aplicados. El módulo solo muestra un precio base si hay una diferencia.
4.  **Compatibilidad con el tema:** Algunos temas altamente personalizados pueden anular las funciones principales de visualización de precios de PrestaShop. Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

**P: El precio base se muestra, pero no se ve bien con mi tema (color, tamaño incorrectos, etc.).**
R: Utilice la configuración "CSS personalizado para el precio base" en la configuración del módulo. Puede añadir reglas CSS para que coincidan con el diseño de su tema. Por ejemplo, para que aparezca en gris y tachado: `text-decoration: line-through; color: #999; font-size: 0.9em;`. Si no está seguro de cómo usar CSS, un desarrollador web puede ayudarle.

**P: ¿Este módulo ralentizará mi tienda?**
R: El módulo está diseñado para ser ligero. Principalmente anula una clase central de PrestaShop (`Product.php`) para obtener el precio base e inyecta una pequeña plantilla. El impacto en el rendimiento debería ser insignificante. Asegúrese siempre de que la caché de PrestaShop esté habilitada para una velocidad óptima.

**P: ¿Este módulo funciona con tiendas multi-idioma?**
R: Sí, el módulo funciona con las capacidades multi-idioma de PrestaShop. Los precios se muestran en la moneda y el formato del idioma/país activo.

**P: Veo un error de "Conflicto de anulación" después de instalar el módulo.**
R: Este módulo anula la clase `Product.php`. Si otro módulo también intenta anular esta misma clase, podría encontrar un conflicto. PrestaShop 1.7+ tiene una mejor gestión de anulaciones, pero aún pueden ocurrir conflictos. Deberá deshabilitar uno de los módulos en conflicto o fusionar las anulaciones manualmente (requiere conocimientos de desarrollador). Póngase en contacto con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Mostrar precios base (sin descuentos)" opera principalmente anulando la clase `Product` principal para introducir un método que recupera el precio base del producto sin reducciones. Luego utiliza una plantilla Smarty para mostrar este precio en el front office, inyectado a través de un mecanismo de hook personalizado. La configuración del módulo se gestiona a través de un método `getContent()` estándar de PrestaShop en el archivo principal del módulo.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Su funcionalidad se integra directamente en los mecanismos de visualización de precios existentes de PrestaShop y a través de una anulación.

### 4.3 Clases y modelos principales (`classes/`)

- **`baseprices/override/classes/index.php`**: Un archivo `index.php` vacío estándar para evitar el listado de directorios.
- **`baseprices/override/classes/Product.php`**:
  - **Nombre de la clase**: `Product` (anula la clase `Product` principal)
  - **Clase padre**: `ProductCore`
  - **Responsabilidad**: Esta anulación es el núcleo de la funcionalidad del módulo. Introduce un nuevo método, `getBasePrice()`, que calcula y devuelve el precio del producto *antes* de que se apliquen precios específicos, reglas de precio de catálogo o reducciones de grupo. Este método asegura que el verdadero precio original esté siempre disponible para su visualización. Típicamente implica omitir la lógica estándar de cálculo de precios que tiene en cuenta los descuentos.

### 4.4 Activos de JavaScript (`views/js/`)

- **`baseprices/views/js/baseprices-admin.js`**:
  - **Alcance**: Back office (página de configuración del módulo).
  - **Responsabilidad**: Este script probablemente maneja cualquier comportamiento dinámico o validación en el formulario de configuración del módulo. Por ejemplo, podría mostrar/ocultar configuraciones basadas en otras selecciones, o proporcionar retroalimentación en tiempo real para el campo CSS personalizado.
- **`baseprices/views/js/baseprices.js`**:
  - **Alcance**: Front office.
  - **Responsabilidad**: Este script es responsable de inyectar dinámicamente el precio base en el DOM donde sea necesario, especialmente para contenido cargado con AJAX o cuando cambian los atributos del producto (por ejemplo, al seleccionar una combinación diferente en la página del producto). Escucha el evento `updateProduct` de PrestaShop o eventos similares para actualizar la visualización del precio. También podría manejar el estilo o los cambios de visibilidad para el elemento del precio base.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`baseprices/views/css/baseprices.css`**:
  - **Alcance**: Estilo del cliente del front office.
  - **Componentes de interfaz de usuario principales y contenedores que estiliza**: Esta hoja de estilo proporciona la presentación visual predeterminada para el precio base. Típicamente incluye reglas para:
    - `span.base-price` o selectores similares.
    - `text-decoration: line-through;` para tachar el precio.
    - `color`, `font-size`, `margin`, `padding` para posicionar y estilizar el precio base en relación con el precio actual.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: `span.base-price`, `div.product-price-and-shipping .base-price`, etc. Los desarrolladores pueden apuntar a estas clases en el CSS personalizado de su tema para anular el estilo predeterminado del módulo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`baseprices/views/templates/baseprices.tpl`**:
  - **Alcance**: Front office.
  - **Responsabilidad**: Esta plantilla es la salida principal para mostrar el precio base. Está diseñada para ser incluida o renderizada dondequiera que se muestre el precio de un producto. Típicamente recibe variables como `$base_price` y `$current_price` y las formatea de acuerdo con la configuración del módulo (por ejemplo, CSS personalizado, posición). Contendrá la estructura HTML (por ejemplo, `<span class="base-price">...</span>`) a la que apunta el CSS.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Sus ajustes de configuración se almacenan en la tabla `ps_configuration`, utilizando claves con el prefijo `BASEPRICES_`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front office. | Se utiliza para cargar los activos CSS y JavaScript del front office del módulo. |
| `displayProductPriceBlock` | Dentro del bloque de visualización del precio del producto en las páginas de productos y listados. | Es probable que el módulo aproveche este hook (o hooks similares relacionados con el precio) para inyectar su plantilla `baseprices.tpl`, mostrando el precio base junto con el precio actual. |
| `actionProductUpdate` / `actionProductSave` | Después de que un producto se actualiza o se guarda en el Back Office. | Aunque no se lista explícitamente, los módulos que anulan `Product.php` podrían usar tales hooks para borrar cachés o reindexar datos de productos si es necesario, aunque la función principal de este módulo es solo de visualización. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su plantilla. | Se utiliza para registrar archivos JavaScript y CSS del front office para la página actual. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Mostrar precios base (sin descuentos)", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
