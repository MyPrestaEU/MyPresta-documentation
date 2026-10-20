---
title: "Compartir producto en Twitter + código de cupón - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Compartir producto en Twitter + código de cupón' de MyPresta.eu."
sidebar:
  label: "Compartir producto en Twitter + código de cupón - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Twitter product share + voucher code en MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Compartir producto en Twitter + código de cupón

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Compartir producto en Twitter + código de cupón", accesible después de la instalación haciendo clic en el botón "Configurar". Aquí, definirá cómo se comporta el botón de compartir y cómo se generan los códigos de cupón.

#### **Configuración general**

-   **Activar módulo:**

    -   **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar todo el módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El botón de compartir en Twitter aparecerá en sus páginas de producto (según su selección de hook), y el sistema de generación de códigos de cupón estará activo.
        -   *Cuando está desactivado (NO):* El botón de compartir en Twitter no aparecerá, y no se generarán códigos de cupón para las comparticiones.
    -   **Valor recomendado:** SÍ (para activar la funcionalidad del módulo).
    -   **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez o realizando mantenimiento, podría desactivarlo temporalmente. De lo contrario, manténgalo activado para beneficiarse del intercambio social.
-   **Hook para mostrar el botón:**

    -   **Qué hace este ajuste:** Determina dónde se colocará visualmente el botón de compartir en Twitter en sus páginas de producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Opciones (ejemplos):* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
        -   *Cuando se establece en `displayProductButtons` (común):* El botón probablemente aparecerá cerca del botón "Añadir al carrito" o del selector de cantidad del producto.
        -   *Cuando se establece en `displayRightColumnProduct`:* El botón aparecerá en la columna derecha de su página de producto (si su tema tiene una).
        -   *Cuando se establece en `displayFooterProduct`:* El botón aparecerá en la sección del pie de página del producto.
    -   **Valor recomendado:** `displayProductButtons` o `displayProductExtraContent` para una máxima visibilidad y compromiso, ya que estos suelen estar cerca de la información principal del producto.
    -   **Escenario / ejemplo de comerciante:** Podría probar diferentes hooks para ver qué ubicación genera más comparticiones en su tema específico. Una ubicación prominente suele ser la mejor.
-   **Número de comparticiones requeridas para un cupón:**

    -   **Qué hace este ajuste:** Define cuántas comparticiones de productos únicas debe realizar un cliente antes de recibir un cupón de descuento.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 1:* Un cliente recibe un cupón inmediatamente después de su primera compartición.
        -   *Cuando se establece en 3:* Un cliente debe compartir tres productos diferentes (o el mismo producto tres veces, dependiendo de la lógica interna) antes de que se emita un cupón.
    -   **Valor recomendado:** 1 (para fomentar la acción y la recompensa inmediatas) o 2 (para fomentar un poco más de compromiso sin ser demasiado exigente).
    -   **Escenario / ejemplo de comerciante:** Si desea facilitar que los clientes obtengan un descuento, configúrelo en 1. Si desea fomentar un intercambio más extenso, configúrelo más alto, pero tenga en cuenta que un número más alto podría reducir la participación.

#### **Configuración del código de cupón**

-   **Prefijo del código de cupón:**

    -   **Qué hace este ajuste:** Una cadena de caracteres personalizada que aparecerá al principio de cada código de cupón generado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en `TWITTER-`:* Un código de cupón podría verse como `TWITTER-ABCDE123`.
        -   *Cuando se deja vacío:* El código de cupón será puramente caracteres aleatorios.
    -   **Valor recomendado:** `TWITTER-` o `SHARE-` para identificar fácilmente el origen del cupón.
    -   **Escenario / ejemplo de comerciante:** Usar un prefijo le ayuda a rastrear qué campañas de marketing están generando cupones específicos en sus informes de ventas de PrestaShop.
-   **Valor del código de cupón (porcentaje):**

    -   **Qué hace este ajuste:** El porcentaje de descuento aplicado por el código de cupón generado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 10:* El cupón otorgará un 10% de descuento en el pedido del cliente.
        -   *Cuando se establece en 5:* El cupón otorgará un 5% de descuento.
    -   **Valor recomendado:** 5-15% (dependiendo de sus márgenes de beneficio y el nivel de incentivo deseado).
    -   **Escenario / ejemplo de comerciante:** Un descuento del 10% suele ser un buen equilibrio entre atraer a los clientes y mantener la rentabilidad.
-   **Validez del código de cupón (días):**

    -   **Qué hace este ajuste:** Cuántos días será válido el código de cupón generado desde el momento en que se emite.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 7:* El cupón caducará 7 días después de que el cliente lo reciba.
        -   *Cuando se establece en 30:* El cupón será válido durante un mes.
    -   **Valor recomendado:** 7-14 días (para crear una sensación de urgencia sin ser demasiado restrictivo).
    -   **Escenario / ejemplo de comerciante:** Un período de validez más corto anima a los clientes a realizar una compra antes, evitando que se olviden del cupón.
-   **Cantidad mínima para que el cupón sea válido:**

    -   **Qué hace este ajuste:** La cantidad total mínima del pedido (antes del envío) requerida para que el cliente pueda usar el cupón de descuento.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en 50:* El cupón solo se puede usar si el total del carrito del cliente es de 50 € o más.
        -   *Cuando se establece en 0 (o vacío):* El cupón se puede usar en cualquier cantidad de pedido.
    -   **Valor recomendado:** Una cantidad razonable que fomente una compra ligeramente mayor, o 0 si desea permitirlo en cualquier pedido.
    -   **Escenario / ejemplo de comerciante:** Si el valor promedio de su pedido es de 40 €, establecer un mínimo de 50 € podría animar a los clientes a añadir otro artículo a su carrito para alcanzar el umbral y usar el descuento.
-   **Descripción del código de cupón:**

    -   **Qué hace este ajuste:** Una breve descripción de texto que se asociará con el código de cupón en su back office de PrestaShop (y potencialmente visible para el cliente en su cuenta si revisa sus cupones).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Descuento por compartir en Twitter":* Este texto aparecerá en los detalles del cupón.
    -   **Valor recomendado:** "Descuento por compartir en Twitter" o "¡Gracias por compartir en Twitter!"
    -   **Escenario / ejemplo de comerciante:** Esto le ayuda a usted y a sus clientes a comprender el origen del cupón.
-   **Nombre del código de cupón:**

    -   **Qué hace este ajuste:** El nombre interno de la regla del cupón en PrestaShop. Esto es principalmente para su organización interna.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Cupón de compartir en Twitter":* Este nombre aparecerá en su sección "Reglas de carrito" de PrestaShop.
    -   **Valor recomendado:** "Cupón de compartir en Twitter" o "Descuento por compartir en redes sociales".
    -   **Escenario / ejemplo de comerciante:** Un nombre claro facilita la búsqueda y gestión de estos cupones generados automáticamente dentro de su administración de PrestaShop.

#### **Configuración del texto para compartir en Twitter**

-   **Texto predeterminado para compartir:**
    -   **Qué hace este ajuste:** El texto predeterminado que se precargará en la ventana emergente para compartir en Twitter cuando un cliente haga clic en el botón de compartir. Este texto se combinará con el nombre del producto y el enlace.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "¡Echa un vistazo a este increíble producto!":* El tweet podría verse como "¡Echa un vistazo a este increíble producto! [Nombre del producto] [Enlace del producto]".
    -   **Valor recomendado:** Algo atractivo como "¡Echa un vistazo a este increíble producto de [Nombre de tu tienda]!" o "¡Acabo de encontrar este gran producto!"
    -   **Escenario / ejemplo de comerciante:** Un texto predeterminado convincente fomenta más clics y compromiso por parte de los seguidores del cliente.

#### **Botón Guardar**

-   **Guardar:**
    -   **Qué hace este botón:** Aplica todos los cambios que ha realizado en esta página de configuración.
    -   **Efecto de hacer clic en este botón:** Sus ajustes se guardan en la base de datos y el comportamiento del módulo se actualizará inmediatamente en su front office.
    -   **Acción recomendada:** Siempre haga clic en "Guardar" después de realizar cualquier cambio.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar módulo | SÍ | Activa/desactiva el módulo. |
| | Hook para mostrar el botón | `displayProductButtons` | Controla dónde aparece el botón de compartir en las páginas de producto. |
| | Número de comparticiones requeridas para un cupón | 1 | Cuántas comparticiones antes de que un cliente obtenga un cupón. |
| | Prefijo del código de cupón | `TWITTER-` | Añade un prefijo personalizado a los códigos de cupón generados. |
| | Valor del código de cupón (porcentaje) | 10 | El porcentaje de descuento del cupón. |
| | Validez del código de cupón (días) | 7-14 | Cuánto tiempo es válido el cupón después de su generación. |
| | Cantidad mínima para que el cupón sea válido | 0 (o cantidad razonable) | Total mínimo del carrito requerido para usar el cupón. |
| | Descripción del código de cupón | "Descuento por compartir en Twitter" | Descripción interna del cupón. |
| | Nombre del código de cupón | "Cupón de compartir en Twitter" | Nombre interno de la regla del cupón. |
| | Texto predeterminado para compartir | "¡Echa un vistazo a este increíble producto!" | Texto precargado para la ventana emergente de compartir en Twitter. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El botón de compartir en Twitter no aparece en mis páginas de producto.**

-   **R:** Primero, asegúrese de que el módulo esté **activado** en su configuración. Segundo, verifique la configuración **"Hook para mostrar el botón"**. Su tema podría no renderizar el hook elegido en una ubicación visible, o el hook podría no existir. Intente cambiar a un hook común diferente como `displayProductButtons` o `displayProductExtraContent`. Si aún no aparece, su tema podría requerir una integración personalizada para ciertos hooks, o podría haber un conflicto.
-   **Consejo profesional:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento) después de realizar cualquier cambio en la configuración del módulo o en los archivos del tema.

**P2: Los clientes están compartiendo, pero no reciben códigos de cupón.**

-   **R:**
    1.  **Verifique "Número de comparticiones requeridas para un cupón":** ¿Está configurado en 1? Si es más alto, los clientes necesitan compartir más veces antes de obtener un cupón.
    2.  **Verifique la configuración del cupón:** Asegúrese de que "Valor del código de cupón (porcentaje)" esté configurado en un número mayor que 0, y que "Validez del código de cupón (días)" también esté configurado.
    3.  **Reglas de carrito de PrestaShop:** Verifique su Back Office de PrestaShop en **Catálogo > Descuentos > Reglas de carrito**. Debería ver cupones generados automáticamente con el nombre que especificó (por ejemplo, "Cupón de compartir en Twitter"). Si no aparecen nuevas reglas, podría haber un problema con la lógica de generación de cupones.
-   **Consejo profesional:** Pruebe el proceso usted mismo. Comparta un producto de su tienda mientras está conectado como cliente y vea si se genera un cupón.

**P3: La ventana emergente para compartir en Twitter se ve extraña o no funciona correctamente.**

-   **R:** Esto a menudo se debe a conflictos de JavaScript con otros módulos o su tema.
    1.  **Verifique la consola del navegador:** Abra las herramientas de desarrollador de su navegador (generalmente F12) y busque errores en la pestaña "Consola" cuando haga clic en el botón de compartir.
    2.  **Conflictos de módulos:** Desactive temporalmente otros módulos que añadan JavaScript a las páginas de productos (especialmente módulos de redes sociales o ventanas emergentes) para ver si el problema se resuelve.
-   **Consejo profesional:** Asegúrese de que su instalación de PrestaShop y su tema estén actualizados. Los componentes obsoletos a veces pueden causar conflictos inesperados.

**P4: ¿Puedo personalizar la apariencia del botón de compartir?**

-   **R:** El módulo utiliza su propio CSS (`twittercoupon/css.css` y `twittercoupon/css/css.css`). Puede anular estos estilos en el archivo CSS personalizado de su tema. Inspeccione el botón usando las herramientas de desarrollador de su navegador para identificar sus clases CSS y luego añada sus estilos personalizados al archivo `custom.css` de su tema o equivalente.
-   **Consejo profesional:** Evite editar directamente los archivos CSS del módulo, ya que sus cambios se perderán durante las actualizaciones del módulo. Utilice siempre las capacidades de CSS personalizado de su tema.

**P5: ¿Cómo evita el módulo el abuso (por ejemplo, que alguien comparta repetidamente para obtener varios cupones)?**

-   **R:** El módulo normalmente rastrea las comparticiones por cliente (a menudo por dirección IP o ID de cliente si ha iniciado sesión) para evitar que un solo usuario genere cupones ilimitados. La configuración "Número de comparticiones requeridas para un cupón" también ayuda a gestionar esto. Para una prevención de fraude más avanzada, es posible que necesite módulos de seguridad adicionales de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Compartir producto en Twitter + código de cupón" (`twittercoupon`) es un módulo estándar de PrestaShop implementado principalmente dentro de su archivo PHP principal, `ajax_twittercoupon.php`. Aprovecha el sistema de hooks de PrestaShop para la visualización en el front-office y la clase `Configuration` para el almacenamiento de la configuración. El módulo genera dinámicamente objetos `CartRule` (cupones) basados en las acciones del usuario. Su funcionalidad de front-office se basa en JavaScript para interactuar con la API de Twitter y un endpoint AJAX dentro del módulo para procesar las comparticiones y emitir cupones.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office en el directorio `controllers/`. Todas las solicitudes AJAX del front-office y el manejo de la configuración del back-office se gestionan directamente dentro del archivo principal del módulo, `ajax_twittercoupon.php`, específicamente a través de su método `getContent()` para la configuración y un despacho AJAX personalizado para el procesamiento de comparticiones.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define clases personalizadas ni extiende `ObjectModel` en un directorio `classes/` dedicado. La lógica central para la generación de cupones interactúa directamente con las clases `CartRule` y `Configuration` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye archivos JavaScript para manejar las interacciones del front-office.

-   `twittercoupon/lib/voucherengine/script.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este parece ser el script principal responsable de la lógica del lado del cliente del módulo. Probablemente maneja:
        -   Vinculación de eventos de clic al botón de compartir en Twitter.
        -   Apertura de la ventana emergente para compartir en Twitter (utilizando la API de Twitter Web Intent).
        -   Detección de comparticiones exitosas (posiblemente a través de callbacks o sondeos).
        -   Realización de llamadas AJAX al backend del módulo para registrar la compartición y solicitar un cupón.
        -   Visualización del código de cupón al usuario tras una generación exitosa.
        -   Puede incluir lógica para evitar múltiples comparticiones del mismo usuario en un corto período o para rastrear el número de comparticiones.
-   `twittercoupon/trusted.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** El nombre "trusted.js" sugiere que podría estar relacionado con la seguridad, el seguimiento o la garantía de la integridad del proceso de compartición. Potencialmente podría manejar:
        -   Validación del lado del cliente antes de iniciar una compartición.
        -   Seguimiento de las interacciones del usuario para medidas antifraude.
        -   Integración con otros scripts de seguimiento o análisis.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo proporciona archivos CSS para estilizar los elementos del front-office.

-   `twittercoupon/css.css`
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Responsabilidad:** Contiene los estilos principales para el botón de compartir en Twitter, cualquier ventana emergente asociada o mensajes mostrados al cliente.
    -   **Selectores de clase CSS clave:** Los desarrolladores deben inspeccionar el HTML renderizado para identificar clases específicas (por ejemplo, `.twitter-share-button`, `.twitter-coupon-message`) para anular en el `custom.css` de su tema.
-   `twittercoupon/css/css.css`
    -   **Alcance:** Estilo del cliente del front-office.
    -   **Responsabilidad:** Este archivo parece ser un duplicado o una ruta alternativa para el CSS principal. Es común que los módulos tengan rutas redundantes o que una sea una alternativa. Los desarrolladores deben verificar cuál se carga realmente en el navegador.
    -   **Selectores de clase CSS clave:** Igual que el anterior.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido de front-office.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `twittercoupon/share.tpl`
        -   **Hook:** Esta plantilla se renderiza en el hook elegido en la configuración del módulo (por ejemplo, `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
        -   **Propósito:** Genera el HTML para el botón "Compartir en Twitter" y, potencialmente, un marcador de posición para el mensaje del código de cupón o un disparador modal. Probablemente incluirá variables para el nombre del producto, la URL del producto y el texto predeterminado para compartir.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo almacena principalmente su configuración en la tabla `ps_configuration` de PrestaShop.
        -   `PS_TWITTERCOUPON_ENABLED` (booleano)
        -   `PS_TWITTERCOUPON_HOOK` (cadena)
        -   `PS_TWITTERCOUPON_SHARES_REQUIRED` (entero)
        -   `PS_TWITTERCOUPON_PREFIX` (cadena)
        -   `PS_TWITTERCOUPON_VALUE` (flotante)
        -   `PS_TWITTERCOUPON_VALIDITY` (entero)
        -   `PS_TWITTERCOUPON_MIN_AMOUNT` (flotante)
        -   `PS_TWITTERCOUPON_DESCRIPTION` (cadena)
        -   `PS_TWITTERCOUPON_NAME` (cadena)
        -   `PS_TWITTERCOUPON_DEFAULT_TEXT` (cadena)
    -   También es probable que utilice una tabla personalizada (por ejemplo, `ps_twittercoupon_shares` o similar) para rastrear las comparticiones individuales de los clientes (por `id_customer` o `ip_address`, `id_product`) y evitar el abuso, aunque no se listó ningún archivo SQL explícito, esta lógica se manejaría en el método `install()` del módulo principal. Esta tabla rastrearía:
        -   `id_customer` (si ha iniciado sesión)
        -   `ip_address`
        -   `id_product`
        -   `share_date`
        -   `voucher_issued` (booleano)
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para cargar los activos CSS y JavaScript del módulo (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | En la página del producto, normalmente cerca del botón de añadir al carrito. | Para mostrar el botón de compartir en Twitter (`share.tpl`). |
| `displayRightColumnProduct` | En la página del producto, en la columna derecha. | Hook alternativo para mostrar el botón de compartir en Twitter (`share.tpl`). |
| `displayFooterProduct` | En la página del producto, en el área del pie de página. | Hook alternativo para mostrar el botón de compartir en Twitter (`share.tpl`). |
| `displayProductExtraContent` | En la página del producto, a menudo debajo de la descripción principal del producto. | Hook alternativo para mostrar el botón de compartir en Twitter (`share.tpl`). |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido, permitiendo a los módulos añadir activos. | Para cargar los activos CSS y JavaScript del módulo condicionalmente según la página. |
| (Llamada AJAX interna) | Activado por JavaScript en el evento de compartir. | Para procesar la compartición, actualizar el recuento de comparticiones y generar una `CartRule` (cupón) si se cumplen las condiciones. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte técnico dedicado para el módulo "Compartir producto en Twitter + código de cupón", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se compromete a brindar asistencia oportuna y garantizar el rendimiento óptimo de su módulo.
