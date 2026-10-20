---
title: "Carrito de barra lateral deslizante - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Carrito de barra lateral deslizante' de MyPresta.eu."
sidebar:
  label: "Carrito de barra lateral deslizante - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Sliding sidebar cart en MyPresta.eu](https://mypresta.eu/modules/front-office-features/sliding-sidebar-cart.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/sliding-sidebar-cart/)
>
> ---


# Carrito de barra lateral deslizante

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes. Esta página le permite controlar exactamente qué información se muestra dentro del carrito de barra lateral deslizante.

-   **Mostrar imagen del producto**

    -   **Qué hace este ajuste:** Controla si la imagen en miniatura de cada producto en el carrito se muestra en la barra lateral.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Una pequeña imagen de cada producto aparecerá junto a su nombre en la barra lateral, facilitando a los clientes la identificación visual de los artículos.
        -   *Cuando está deshabilitado ("No"):* Solo se mostrará el nombre del producto y otros detalles de texto, ahorrando espacio pero potencialmente haciendo que el carrito sea menos atractivo visualmente.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** Habilitar esto ayuda a los clientes a confirmar rápidamente que han añadido el artículo correcto, especialmente útil para tiendas con muchos productos o variaciones con nombres similares.
-   **Mostrar nombre del producto**

    -   **Qué hace este ajuste:** Determina si el nombre de cada producto es visible en el carrito deslizante.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Se mostrará el nombre completo de cada producto.
        -   *Cuando está deshabilitado ("No"):* Los nombres de los productos se ocultarán. Esto generalmente no se recomienda, ya que dificulta la comprensión del carrito.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** Esta es una información fundamental. Manténgala siempre en "Sí" para que los clientes sepan exactamente qué hay en su carrito.
-   **Mostrar valores de atributos del producto**

    -   **Qué hace este ajuste:** Si sus productos tienen atributos (como talla, color, material), este ajuste controla si esos atributos seleccionados se muestran para cada producto en el carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Para un producto como "Camiseta (Talla: M, Color: Azul)", se mostrará "Talla: M, Color: Azul".
        -   *Cuando está deshabilitado ("No"):* Solo se mostrará "Camiseta", lo que podría confundir a los clientes sobre la variante exacta que añadieron.
    -   **Valor recomendado:** "Sí" (especialmente para tiendas que venden productos configurables)
    -   **Escenario / ejemplo de comerciante:** Crucial para tiendas que venden ropa, productos electrónicos con diferentes especificaciones o cualquier producto con múltiples opciones. Ayuda a los clientes a verificar que han seleccionado la variante correcta.
-   **Mostrar precio del producto**

    -   **Qué hace este ajuste:** Controla si se muestra el precio individual de cada producto en el carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* El precio unitario de cada artículo será visible.
        -   *Cuando está deshabilitado ("No"):* Los precios individuales de los productos se ocultarán, aunque el valor total del carrito seguirá mostrándose.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** La transparencia es clave. Mostrar los precios individuales ayuda a los clientes a comprender el desglose de costos y confirma sus selecciones.
-   **Mostrar campo de entrada de cantidad**

    -   **Qué hace este ajuste:** Permite a los clientes cambiar la cantidad de un artículo directamente dentro del carrito de la barra lateral utilizando un campo de entrada.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Aparecerá un campo de entrada numérico (por ejemplo, "1", "2", "3") junto a cada producto, permitiendo a los clientes escribir una nueva cantidad o usar botones de incremento/decremento.
        -   *Cuando está deshabilitado ("No"):* Los clientes no pueden cambiar las cantidades en la barra lateral; tendrían que ir a la página completa del carrito para hacerlo.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** Esto mejora significativamente la usabilidad. Un cliente que accidentalmente añadió 2 de un artículo en lugar de 1 puede corregirlo instantáneamente sin salir de su página actual, reduciendo la frustración y el posible abandono del carrito.
-   **Mostrar botón de eliminar**

    -   **Qué hace este ajuste:** Añade un botón (generalmente una "X" o un icono de papelera) junto a cada producto, permitiendo a los clientes eliminarlo del carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Los clientes pueden eliminar fácilmente artículos no deseados de su carrito directamente desde la barra lateral.
        -   *Cuando está deshabilitado ("No"):* Los clientes no pueden eliminar artículos de la barra lateral; tendrían que ir a la página completa del carrito.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** Esencial para una experiencia de compra flexible. Si un cliente cambia de opinión sobre un artículo, puede eliminarlo instantáneamente, evitando que abandone todo el carrito debido a un producto no deseado.
-   **Mostrar costo de envío**

    -   **Qué hace este ajuste:** Muestra una estimación o el costo de envío real dentro del resumen del carrito de la barra lateral.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* El costo de envío estimado o calculado se mostrará en el resumen del carrito.
        -   *Cuando está deshabilitado ("No"):* Los costos de envío no se mostrarán en la barra lateral, solo en el carrito completo o en la página de pago.
    -   **Valor recomendado:** "Sí" (si su cálculo de envío es preciso desde el principio)
    -   **Escenario / ejemplo de comerciante:** La transparencia sobre los costos de envío por adelantado puede evitar el "shock del precio" al finalizar la compra, que es una causa importante de abandono del carrito. Si su envío es complejo o depende en gran medida de la dirección del cliente, podría considerar dejarlo en "No" para evitar estimaciones engañosas.
-   **Mostrar subtotal (valor total de los productos)**

    -   **Qué hace este ajuste:** Muestra el valor total de todos los productos en el carrito, *antes* de aplicar cualquier envío, impuestos o descuentos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* Se mostrará la suma de todos los precios de los productos.
        -   *Cuando está deshabilitado ("No"):* Esta línea de subtotal específica se ocultará.
    -   **Valor recomendado:** "Sí"
    -   **Escenario / ejemplo de comerciante:** Proporciona un desglose claro para el cliente, ayudándole a comprender el costo de los artículos en sí, separado de otros cargos.
-   **Mostrar impuestos del subtotal**

    -   **Qué hace este ajuste:** Muestra el monto total de impuestos aplicados a los productos en el carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado ("Sí"):* El monto total de impuestos se mostrará en el resumen del carrito.
        -   *Cuando está deshabilitado ("No"):* Los detalles de los impuestos no se mostrarán en la barra lateral.
    -   **Valor recomendado:** "Sí" (especialmente en regiones donde la transparencia fiscal es legalmente requerida o esperada por los clientes)
    -   **Escenario / ejemplo de comerciante:** Importante para la transparencia, particularmente en países donde el IVA o el impuesto sobre las ventas es un componente significativo del precio final. Ayuda a los clientes a comprender el desglose completo de los costos antes de proceder al pago.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar imagen del producto | Sí | Muestra miniaturas de productos para identificación visual. |
| Configuración del módulo | Mostrar nombre del producto | Sí | Muestra el nombre de cada producto en el carrito. |
| Configuración del módulo | Mostrar valores de atributos del producto | Sí | Muestra los atributos seleccionados (talla, color) para productos configurables. |
| Configuración del módulo | Mostrar precio del producto | Sí | Muestra el precio individual de cada producto. |
| Configuración del módulo | Mostrar campo de entrada de cantidad | Sí | Permite a los clientes cambiar las cantidades de productos directamente en la barra lateral. |
| Configuración del módulo | Mostrar botón de eliminar | Sí | Permite a los clientes eliminar productos del carrito directamente en la barra lateral. |
| Configuración del módulo | Mostrar costo de envío | Sí | Muestra el costo de envío estimado/real en el resumen. |
| Configuración del módulo | Mostrar subtotal (valor total de los productos) | Sí | Muestra el valor total de los productos antes del envío/impuestos. |
| Configuración del módulo | Mostrar impuestos del subtotal | Sí | Muestra el monto total de impuestos aplicados a los productos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La barra lateral no se desliza cuando añado un producto al carrito.**
R1:

-   **Verificar el estado del módulo:** Asegúrese de que el módulo "Carrito de barra lateral deslizante" esté instalado y habilitado en **Módulos > Gestor de módulos**.
-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos de caché antiguos impiden que se cargue la nueva funcionalidad del módulo.
-   **Conflictos de tema:** Su tema podría tener su propia confirmación de "añadir al carrito" o JavaScript que entra en conflicto con este módulo. Cambie temporalmente al tema predeterminado de PrestaShop (Classic) para ver si la barra lateral funciona. Si lo hace, el problema está en el JavaScript o CSS de su tema personalizado. Es posible que necesite un desarrollador para investigar.
-   **Errores de JavaScript:** Abra la consola de desarrollador de su navegador (generalmente F12) y busque cualquier error de JavaScript cuando añada un producto. Estos errores pueden impedir que aparezca la barra lateral.

**P2: La barra lateral aparece, pero el estilo se ve mal (colores, fuentes o diseño incorrectos).**
R2:

-   **Conflictos de CSS del tema:** Esto casi siempre es un conflicto de CSS con su tema activo de PrestaShop. Las hojas de estilo de su tema podrían estar anulando los estilos del módulo.
-   **Solución:** Probablemente necesitará un webmaster o desarrollador para inspeccionar el CSS utilizando las herramientas de desarrollo del navegador. Podrán identificar los estilos conflictivos y añadir CSS personalizado a su tema (o al archivo CSS personalizado del módulo si está disponible) para asegurar que la barra lateral se muestre correctamente.

**P3: Las cantidades o los precios no se actualizan correctamente cuando los cambio en la barra lateral.**
R3:

-   **Borrar caché:** De nuevo, intente borrar la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
-   **Problemas de AJAX:** El módulo utiliza AJAX para actualizar el carrito. Si hay errores del lado del servidor o conflictos de JavaScript que impiden que las llamadas AJAX se completen, las actualizaciones no se registrarán. Verifique la consola de desarrollador de su navegador en busca de errores de red o errores de JavaScript cuando intente cambiar las cantidades.
-   **Configuración del módulo:** Verifique que "Mostrar campo de entrada de cantidad" esté habilitado en la configuración del módulo.

**P4: ¿Cómo traduzco el texto de la barra lateral a otros idiomas?**
R4:

-   **Sistema de traducción de PrestaShop:** Vaya a **Internacional > Traducciones** en su Back Office.
-   **Tipo de traducción:** Seleccione "Traducciones de módulos instalados".
-   **Seleccionar módulo:** Elija "Carrito de barra lateral deslizante" del menú desplegable de módulos.
-   **Seleccionar idioma:** Elija el idioma al que desea traducir.
-   **Traducir:** Verá una lista de cadenas traducibles del módulo. Introduzca sus traducciones y guarde.

**P5: ¿Puedo cambiar el lado desde el que se desliza la barra lateral (izquierda vs. derecha)?**
R5:

-   El comportamiento predeterminado del módulo es típicamente deslizarse desde la derecha. Cambiar esto requeriría modificaciones CSS personalizadas, ya que está controlado por los archivos `sidcart.css` y `sidcart-right.css`. Un desarrollador podría ajustar las propiedades CSS (por ejemplo, `right: 0` a `left: 0`) y potencialmente la lógica de animación para lograr esto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Carrito de barra lateral deslizante" (`sidcart`) sigue una arquitectura de módulo estándar de PrestaShop, centrándose principalmente en mejoras del front-office. Aprovecha el sistema de hooks de PrestaShop para inyectar su funcionalidad y plantillas en la tienda. La lógica central para la interacción del carrito (añadir, actualizar, eliminar productos) se maneja a través de un controlador frontal AJAX, asegurando una experiencia de usuario dinámica y no disruptiva. La configuración se gestiona a través del método `getContent()` de la clase principal del módulo, almacenando los ajustes en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nombre de la clase y clase padre**: `SidcartAjaxModuleFrontController` extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador es responsable de manejar todas las solicitudes AJAX relacionadas con el carrito deslizante. Cuando un usuario añade un producto, actualiza una cantidad o elimina un artículo de la barra lateral, el JavaScript envía una solicitud a este controlador. Procesa la modificación del carrito utilizando la clase `Cart` central de PrestaShop y luego devuelve un resumen del carrito actualizado (generalmente fragmentos HTML o datos JSON) al JavaScript del front-end, que luego actualiza el contenido de la barra lateral. Esto asegura actualizaciones en tiempo real sin recargas completas de la página.
-   **Controladores de administración de Back-Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase `ObjectModel` personalizada ni clases dedicadas en el directorio `classes/`. Su lógica central reside dentro del archivo `sidcart.php` y el controlador frontal `ajax.php`, interactuando directamente con las clases nativas `Cart` y `Product` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

-   `sidcart/views/js/sidcart.js`
    -   **Alcance**: Front-office.
    -   **Detalles**: Este es el archivo JavaScript principal del módulo.
        -   Escucha los eventos de "añadir al carrito" (por ejemplo, clics en botones con clases específicas como `.add-to-cart`).
        -   Intercepta el comportamiento predeterminado de "añadir al carrito" y, en su lugar, activa la barra lateral deslizante.
        -   Maneja la comunicación AJAX con `controllers/front/ajax.php` para actualizar el contenido del carrito.
        -   Gestiona la visualización y animación de la barra lateral (deslizándose hacia adentro/afuera).
        -   Vincula los oyentes de eventos para los cambios de cantidad y los botones de eliminación dentro de la propia barra lateral, enviando más solicitudes AJAX para actualizar el carrito.
        -   Es probable que utilice `jQuery` para la manipulación del DOM y las llamadas AJAX, común en PrestaShop 1.7.x y 8.x.
        -   También puede escuchar `prestashop.on('updateCart', ...)` o eventos similares para asegurar que la barra lateral refleje los cambios realizados por otros módulos o la funcionalidad central de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `sidcart/views/css/sidcart-right.css`

    -   **Alcance**: Estilo del cliente del Front-office.
    -   **Detalles**: Esta hoja de estilo define la apariencia visual y el posicionamiento de la barra lateral deslizante cuando aparece desde el lado derecho de la pantalla.
        -   Incluye reglas para el ancho, el fondo, el z-index y la posición `right` inicial de la barra lateral (por ejemplo, `right: -300px;` para ocultarla).
        -   Define las propiedades de transición para animaciones de deslizamiento suaves (por ejemplo, `transition: right 0.3s ease-in-out;`).
        -   Estiliza la superposición que aparece detrás de la barra lateral cuando está abierta.
        -   Contiene reglas específicas para la adaptabilidad móvil, ajustando el ancho o la posición de la barra lateral en pantallas más pequeñas.
        -   **Selectores de clase CSS clave**: `.sidcart-wrapper`, `.sidcart-content`, `.sidcart-overlay`, `.sidcart-open`.
-   `sidcart/views/css/sidcart.css`

    -   **Alcance**: Estilo del cliente del Front-office.
    -   **Detalles**: Esta hoja de estilo contiene reglas de estilo generales para los elementos *dentro* del carrito deslizante, independientemente de si se desliza desde la izquierda o la derecha.
        -   Estiliza los elementos de la lista de productos (`.sidcart-product-line`).
        -   Estiliza las imágenes de los productos, nombres, precios, atributos, campos de entrada de cantidad y botones de eliminación.
        -   Estiliza las secciones de resumen del carrito (subtotal, envío, total).
        -   Estiliza los botones "Continuar comprando" y "Proceder al pago".
        -   **Selectores de clase CSS clave**: `.sidcart-product-image`, `.sidcart-product-name`, `.sidcart-product-price`, `.sidcart-qty-input`, `.sidcart-remove-button`, `.sidcart-summary`, `.sidcart-buttons`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `sidcart/views/templates/hook/product-line.tpl`
        -   **Hook**: Esta plantilla no está directamente enganchada, sino que es renderizada dinámicamente por el controlador AJAX (`ajax.php`) para representar una única entrada de producto dentro del carrito deslizante.
        -   **Salida**: Renderiza el HTML para un producto, incluyendo su imagen, nombre, atributos, precio, entrada de cantidad y botón de eliminar, basándose en la configuración del módulo.
    -   `sidcart/views/templates/hook/sidcart.tpl`
        -   **Hook**: Es probable que esta plantilla sea renderizada por el hook `displayHeader` o `displayNav2` (o similar) para inyectar la estructura principal de la barra lateral deslizante en la página. Podría estar inicialmente oculta y luego revelada por JavaScript.
        -   **Salida**: Contiene la estructura HTML principal para toda la barra lateral deslizante, incluyendo el contenedor, el área de la lista de productos, el resumen del carrito y los botones de acción. Actúa como el envoltorio para el contenido de `product-line.tpl` cargado dinámicamente.
-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
-   **Plantillas de Front-office (`views/templates/front/`)**:

    -   `sidcart/views/templates/modal.tpl`
        -   **Hook**: Es probable que esta plantilla sea una alternativa o una estructura alternativa para una visualización tipo modal, o podría usarse para una parte específica de la barra lateral (por ejemplo, un mensaje de confirmación). Dada la descripción del módulo, es menos probable que sea el panel deslizante principal en sí, pero podría ser un componente dentro de él o una plantilla heredada.
        -   **Salida**: Renderiza una estructura genérica de modal o ventana emergente. Los desarrolladores deben verificar su uso real dentro de la lógica de `sidcart.js` o `ajax.php`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    El módulo no crea ninguna tabla SQL personalizada. Todos los ajustes de configuración se almacenan en la tabla `ps_configuration` de PrestaShop utilizando claves como `sc_ajaxInfo`, `sc_continueshopping`, `sc_pimage`, `sc_total`, `sc_subtotals_tax`, `sc_subtotals`, `sc_shipping`, `sc_remove`, `sc_qty_change`, `sc_price`, `sc_pname`, `sc_attributes`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para incluir los archivos CSS y JavaScript del módulo (`sidcart.css`, `sidcart-right.css`, `sidcart.js`) y, potencialmente, para inyectar la estructura HTML inicial y oculta de la barra lateral. |
| `actionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y se están configurando sus activos multimedia. | Se utiliza para incluir cualquier CSS/JS necesario para la página de configuración del módulo en el Back Office. |
| `displayNav2` | En la barra de navegación, típicamente cerca del icono del carrito. | Se utiliza para inyectar un pequeño resumen del carrito (por ejemplo, número de artículos, precio total) o para adjuntar el oyente de eventos al icono del carrito existente que activa la barra lateral. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Carrito de barra lateral deslizante", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
