---
title: "Página de producto como página de inicio de la tienda - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Página de producto como página de inicio de la tienda' de MyPresta.eu."
sidebar:
  label: "Página de producto como página de inicio de la tienda - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page as shop homepage en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-as-shop-homepage/)
>
> ---


# Página de producto como página de inicio de la tienda

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Página de producto como página de inicio de la tienda". Verá una única y sencilla opción de configuración.

- **Nombre del ajuste:** Producto a mostrar en la página de inicio
  - **Qué hace este ajuste:** Este es el ajuste más crucial. Le permite seleccionar exactamente qué producto de su catálogo se convertirá en la nueva página de inicio de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona un producto:* La URL principal de su tienda mostrará la página de producto completa del producto elegido.
    - *Cuando no se selecciona ningún producto (o el módulo está deshabilitado):* Su tienda volverá a su comportamiento predeterminado de página de inicio (por ejemplo, mostrando productos destacados, categorías o una página CMS personalizada).
  - **Valor recomendado:** Seleccione el producto que desea destacar más prominentemente. Utilice la barra de búsqueda para encontrar rápidamente el producto deseado.
  - **Escenario / ejemplo de comerciante:** Acaba de lanzar un nuevo gadget revolucionario. Quiere que cada visitante de su tienda vea este producto primero. Escribiría el nombre del producto (por ejemplo, "Super Gadget X") en el cuadro de búsqueda, lo seleccionaría del menú desplegable y guardaría. Ahora, cualquiera que visite `www.sutienda.com` aterrizará directamente en la página de producto de "Super Gadget X".

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Producto a mostrar en la página de inicio | (Ninguno seleccionado inicialmente) / Seleccione su producto clave | Define qué página de producto reemplazará la página de inicio predeterminada de su tienda. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mi página de inicio sigue mostrando el contenido antiguo después de configurar el módulo. ¿Qué debo hacer?**
R: Esto suele ser un problema de caché.
1. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop.
2. Haga clic en "Borrar la caché" en la esquina superior derecha.
3. Además, borre la caché y las cookies de su navegador, luego intente acceder a su tienda nuevamente.

**P: ¿Puedo cambiar el producto destacado fácilmente?**
R: ¡Sí! Simplemente vuelva a **Módulos > Gestor de módulos**, busque "Página de producto como página de inicio de la tienda", haga clic en "Configurar" y seleccione un producto diferente del menú desplegable. Guarde sus cambios y borre su caché.

**P: ¿Qué sucede si el producto seleccionado está agotado o deshabilitado?**
R: Si el producto seleccionado está agotado, su página de producto seguirá mostrándose, pero el botón "Añadir al carrito" podría estar deshabilitado o mostrar un mensaje de "Agotado", dependiendo de la configuración de inventario de su PrestaShop. Si el producto está completamente deshabilitado, PrestaShop podría mostrar un error de "Página no encontrada" o volver a la página de inicio predeterminada. Siempre asegúrese de que el producto seleccionado esté activo y disponible.

**P: ¿Este módulo afecta mi SEO?**
R: Cuando configura una página de producto como su página de inicio, la URL principal de su tienda (`www.sutienda.com`) ahora servirá el contenido de esa página de producto. Los motores de búsqueda indexarán este contenido para su dominio principal. Si anteriormente tenía una página de inicio rica y optimizada para palabras clave, podría ver un cambio en cómo se clasifica su dominio principal. Asegúrese de que la página de producto elegida esté bien optimizada para SEO (título, descripción, imágenes, contenido).

**P: ¿Puedo usar esto con un tema personalizado?**
R: Sí, el módulo funciona anulando la forma en que PrestaShop despacha el `IndexController`. Debería ser compatible con la mayoría de los temas personalizados, ya que aprovecha la renderización estándar de la página de producto de PrestaShop. Si encuentra problemas de estilo, es probable que estén relacionados con el CSS de su tema, no con la funcionalidad central del módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Página de producto como página de inicio de la tienda" opera anulando los controladores frontales principales de PrestaShop para redirigir el comportamiento predeterminado de la página de inicio (`IndexController`). En lugar de cargar la plantilla estándar de la página de inicio, fuerza al `ProductController` a renderizar la página para un ID de producto específico, haciendo efectivamente que una página de producto sea la página de aterrizaje predeterminada para la URL raíz de la tienda. Esto se logra a través de una serie de anulaciones en el directorio `override/`.

### 4.2 Controladores (`controllers/`)

Este módulo utiliza principalmente anulaciones para modificar el comportamiento del controlador.

- **Controladores de Front-Office**:
  - `homepageproduct/override/controllers/front/index.php`
    - Este archivo es un marcador de posición o una anulación más antigua. En PrestaShop moderno, el `IndexController` suele anularse directamente. Su presencia sugiere un mecanismo de compatibilidad o un enfoque más antiguo.
  - `homepageproduct/override/controllers/front/IndexController.php`
    - **Nombre de la clase y clase padre:** `IndexController` (anula `IndexControllerCore`)
    - **Responsabilidad:** Esta es la anulación principal. Cuando se accede a la URL raíz de la tienda, PrestaShop normalmente despacha `IndexController`. Esta anulación intercepta ese despacho. Verifica la configuración del módulo para un ID `homepageproduct_product`. Si se establece un ID de producto, redirige o reenvía internamente la solicitud al `ProductController` para ese producto específico, renderizando efectivamente la página de producto en lugar de la página de inicio predeterminada. Asegura que el contexto del controlador actual se establezca correctamente en `ProductController` y que los datos del producto se carguen.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo utiliza anulaciones para modificar el comportamiento de las clases principales, específicamente relacionadas con el manejo del controlador.

- `homepageproduct/override/classes/controller/FrontController.php`
  - **Nombre de la clase y clase padre:** `FrontController` (anula `FrontControllerCore`)
  - **Responsabilidad:** Esta anulación probablemente contiene lógica para asegurar que la anulación de `IndexController` funcione correctamente dentro del proceso de despacho de `FrontController`. Podría ajustar cómo se inicializa el controlador o cómo se asignan las plantillas cuando la página de inicio se sirve como una página de producto.
- `homepageproduct/override/classes/controller/index.php`
  - Similar a `override/controllers/front/index.php`, esto parece ser un marcador de posición o un mecanismo de anulación más antiguo.
- `homepageproduct/override/classes/index.php`
  - Otro marcador de posición o anulación más antigua.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Toda la interactividad del front-office para la página de producto proviene del JS de la página de producto principal de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. El estilo de la página de producto es manejado completamente por el tema activo de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo no introduce nuevas plantillas de front-office para mostrar. Reutiliza las plantillas de página de producto existentes de PrestaShop.

- **Plantillas de administración (`views/templates/admin/`)**:
  - `homepageproduct/lib/searchTool/views/scripts.tpl`
    - Esta plantilla probablemente se utiliza dentro del método `getContent()` del módulo en el back office. Probablemente contiene lógica JavaScript o Smarty para renderizar el campo de entrada de búsqueda de productos, permitiendo al administrador encontrar y seleccionar fácilmente un producto por nombre o ID para la página de inicio. Podría incluir llamadas AJAX a `AdminProducts` o controladores similares para sugerencias de productos.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena su configuración en la tabla `ps_configuration`:
    - `homepageproduct_product`: Almacena el ID del producto seleccionado para ser la página de inicio.
    - `mypresta_updates`, `update_`, `updatev_`: Utilizadas para las comprobaciones de actualización del módulo por MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una clave de configuración estándar de PrestaShop, no gestionada directamente por este módulo pero potencialmente accedida.
- **Tabla de Hooks registrados**:
  El módulo no registra explícitamente ningún nuevo hook de visualización. Su funcionalidad se logra a través de anulaciones de controladores. Sin embargo, dado que renderiza una página de producto estándar, todos los hooks normalmente presentes en una página de producto (por ejemplo, `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`) se ejecutarán como si fuera una página de producto regular.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Antes del contenido de la página | Para incluir CSS, JS, meta etiquetas. |
| `displayLeftColumn` | Columna izquierda de la página de producto | Mostrar bloques como categorías, filtros. |
| `displayRightColumn` | Columna derecha de la página de producto | Mostrar bloques como carrito, contenido personalizado. |
| `displayFooter` | Al final de la página | Para incluir JS, contenido del pie de página. |
| `displayProductButtons` | Cerca del botón Añadir al carrito | Añadir botones o acciones personalizadas en la página de producto. |
| `displayProductExtraContent` | Debajo de la descripción del producto | Añadir pestañas o contenido extra a la página de producto. |
| `actionValidateOrder` | Después de validar un pedido | Para el procesamiento posterior al pedido (por ejemplo, seguimiento). |
| *(Cualquier otro hook normalmente en una página de producto)* | Varía | Ejecución estándar de hooks de página de producto de PrestaShop. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Página de producto como página de inicio de la tienda", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de nuestros módulos.
