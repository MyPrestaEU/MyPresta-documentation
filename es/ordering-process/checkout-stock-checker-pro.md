---
title: "Checkout stock checker PRO - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Checkout stock checker PRO para PrestaShop de MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Checkout stock checker PRO en MyPresta.eu](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y están disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla principal y única de configuración del módulo "Checkout stock checker PRO". Esta pantalla le permite habilitar o deshabilitar la funcionalidad principal del módulo.

#### **Habilitar / Deshabilitar Módulo**
-   **Qué hace esta configuración:** Este es el interruptor principal para activar o desactivar la funcionalidad de verificación de stock.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado (SÍ):* El módulo verificará activamente los niveles de stock de los productos justo antes de que se realice un pedido. Si un artículo está agotado, el cliente será redirigido al carrito con una notificación.
    -   *Cuando está deshabilitado (NO):* El módulo estará inactivo. No se realizarán verificaciones de stock, y los clientes podrían realizar pedidos de artículos agotados, dependiendo únicamente del comportamiento predeterminado de gestión de stock de PrestaShop (que normalmente solo verifica al añadir al carrito, no en la finalización del pedido).
-   **Valor recomendado:** **SÍ**. Para beneficiarse plenamente del propósito del módulo, siempre debe estar habilitado.
-   **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y quiere empezar a prevenir pedidos de artículos agotados. Lo configuraría en "SÍ". Si necesita deshabilitar temporalmente la función por mantenimiento o pruebas, lo configuraría en "NO".

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Página de Configuración del Módulo | Habilitar / Deshabilitar Módulo | SÍ | Controla si el módulo verifica activamente el stock antes de realizar un pedido. Previene pedidos de artículos agotados cuando está habilitado. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: El módulo está habilitado, pero los clientes siguen realizando pedidos de artículos agotados. ¿Qué está mal?**
R:
1.  **Borrar Caché:** Primero, intente borrar la caché de su PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
2.  **Verificar Estado del Módulo:** Vuelva a verificar que el módulo esté realmente habilitado en su página de configuración.
3.  **Conflictos de Tema:** Algunos temas altamente personalizados u otros módulos que modifican el proceso de pago podrían interferir. Cambie temporalmente al tema predeterminado de PrestaShop (Classic) y pruebe de nuevo. Si funciona, el problema es probablemente un conflicto de tema, y es posible que necesite que un desarrollador lo investigue.
4.  **Versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación específica de PrestaShop.

**P: Mis clientes son redirigidos al carrito, pero el mensaje de notificación no aparece, o está mal diseñado.**
R:
1.  **Borrar Caché:** Como siempre, borre la caché de su PrestaShop.
2.  **Estilo del Tema:** El mensaje de notificación utiliza clases de alerta estándar de PrestaShop. Si su tema ha personalizado o eliminado en gran medida estos estilos, el mensaje podría ser invisible o estar formateado incorrectamente. Un webmaster puede inspeccionar el HTML y CSS para asegurarse de que el mensaje esté presente y con el estilo correcto.
3.  **Archivos del Módulo:** Asegúrese de que todos los archivos del módulo se hayan subido correctamente. A veces, las cargas incompletas pueden llevar a la falta de archivos de plantilla para las notificaciones.

**P: ¿Funciona este módulo con tiendas multi-idioma?**
R: Sí, el módulo utiliza mecanismos de traducción estándar de PrestaShop. Los mensajes de notificación mostrados a los clientes pueden traducirse a todos los idiomas configurados en su tienda. Puede gestionar estas traducciones en **Internacional > Traducciones > Traducciones de Módulos Instalados**.

**P: ¿Este módulo ralentizará mi proceso de pago?**
R: La verificación de stock realizada por el módulo es muy rápida, añadiendo típicamente solo milisegundos al proceso de pago. Es una consulta directa a la base de datos para los niveles de stock, que está altamente optimizada. El impacto en el rendimiento es insignificante y es superado con creces por los beneficios de prevenir pedidos de artículos agotados.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)
Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura
El módulo "Checkout stock checker PRO" (`csc`) está diseñado para integrarse perfectamente en el flujo de pago de PrestaShop. Opera principalmente enganchándose a la etapa final del proceso de realización de pedidos, aprovechando un controlador frontal para realizar una verificación de stock basada en AJAX. Este enfoque garantiza que la verificación de stock se realice en tiempo real justo antes de que el pedido se confirme en la base de datos, evitando condiciones de carrera en las que el stock podría cambiar entre la revisión del carrito y la confirmación final del pedido. El módulo se adhiere al patrón MVC de PrestaShop para su interacción y configuración de front-end.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office
-   `csc/controllers/front/AjaxCheck.php`
    *   **Nombre de la clase y clase padre:** `CscAjaxCheckModuleFrontController` que extiende `ModuleFrontController`.
    *   **Responsabilidad:** Este controlador es el núcleo de la funcionalidad del módulo. Es responsable de manejar la solicitud AJAX iniciada desde la página de pago del front-office. Al recibir la solicitud, itera a través de los productos en el carrito del cliente, verifica sus niveles de stock actuales contra las cantidades solicitadas y devuelve una respuesta JSON indicando si todos los artículos están en stock o qué artículos están agotados. No renderiza una página completa, sino que proporciona datos para que JavaScript actúe.
-   `csc/controllers/front/index.php`
    *   **Nombre de la clase y clase padre:** Este es un archivo `index.php` estándar vacío, típicamente incluido en los directorios de módulos de PrestaShop para evitar la lista directa de directorios. No contiene una clase o lógica específica.

#### Controladores de Administración de Back-Office
El módulo no utiliza ningún controlador de administración personalizado. Su configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)
El módulo no define ninguna clase `ObjectModel` personalizada ni clases de lógica de negocio dedicadas dentro del directorio `classes/`. Toda la lógica principal está encapsulada dentro del archivo principal del módulo (`ajax_csc.php`) y el controlador frontal `AjaxCheck`.

### 4.4 Activos JavaScript (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Alcance:** Front-office.
    *   **Detalles:** Este archivo JavaScript es responsable de iniciar la verificación de stock AJAX. Típicamente se engancha al evento de clic del botón final "Realizar Pedido" (o envío de formulario equivalente) en la página de pago. Antes de permitir que el envío del formulario continúe, envía una solicitud AJAX al controlador frontal `AjaxCheck`. Basándose en la respuesta JSON, permite que el pago se complete o evita el envío, redirige al usuario de vuelta al carrito y muestra el mensaje de error apropiado. Utiliza jQuery estándar o los eventos JavaScript nativos de PrestaShop (`prestashop.on`) para lograr esto.

### 4.5 Hojas de Estilo CSS (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Alcance:** Estilo del cliente de front-office.
    *   **Detalles:** Esta hoja de estilo proporciona un estilo básico para los mensajes de notificación mostrados en la página del carrito cuando se encuentran productos agotados. Probablemente apunta a clases CSS específicas añadidas a los elementos `div` de notificación.
    *   **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores pueden inspeccionar la salida HTML del mensaje de notificación para identificar las clases específicas (por ejemplo, `.alert-danger`, `.csc-notification`, etc.) y anularlas en el `custom.css` o `theme.css` de su tema para que coincidan con la marca de su tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna explícitamente listada, lo que sugiere que la interacción principal del módulo es a través de AJAX y redirección, con notificaciones renderizadas directamente por el controlador `AjaxCheck` o el módulo principal.
-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna, ya que la configuración se maneja mediante `getContent()`.
-   **Plantillas de front-office (`views/templates/front/`)**:
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Propósito:** Esta plantilla probablemente incluye el archivo JavaScript `csc.js` y potencialmente pasa variables de configuración del back-end del módulo al JavaScript del front-end. Probablemente está enganchada a `displayHeader` o `displayFooter` para asegurar que el JS se cargue en las páginas relevantes (por ejemplo, el pago).
    *   `csc/views/errors.tpl`
        *   **Propósito:** Esta plantilla se renderiza cuando la verificación de stock falla (es decir, los artículos están agotados). Muestra el mensaje de error y lista los productos específicos que ya no están disponibles. Esta es la plantilla responsable de la notificación visible en la página del carrito después de la redirección.
    *   `csc/views/no-errors.tpl`
        *   **Propósito:** Esta plantilla es probablemente un marcador de posición o una plantilla que se renderizaría si no hubiera errores, pero la función principal del módulo es mostrar errores. Podría usarse para lógica interna o simplemente ser una plantilla vacía.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: El módulo no crea ninguna tabla de base de datos personalizada. Se basa completamente en las tablas existentes de PrestaShop `ps_product`, `ps_stock_available` y `ps_configuration`. Los ajustes de configuración (como el interruptor de habilitar/deshabilitar) se almacenan en `ps_configuration` utilizando claves como `CSC_ENABLED`.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Renderiza contenido en la sección `<head>` de cada página. | Probablemente utilizado para incluir el script `csc.js` y la hoja de estilo `csc.css`, asegurando que estén disponibles en las páginas de pago. |
| `displayFooter` | Renderiza contenido al final de la sección `<body>` de cada página. | Hook alternativo a `displayHeader` para incluir JS/CSS, a menudo preferido por rendimiento. |
| `displayProductButtons` | Renderiza contenido cerca de los botones de producto (por ejemplo, añadir al carrito). | *No utilizado explícitamente para la funcionalidad principal, pero podría ser para futuras características o elementos menores de la interfaz de usuario.* |
| `displayRightColumn` | Renderiza contenido en la columna derecha de la tienda. | *No utilizado explícitamente para la funcionalidad principal, pero podría ser para futuras características o elementos menores de la interfaz de usuario.* |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus medios (JS/CSS). | Un hook más específico para añadir JS/CSS específicamente a los controladores frontales relevantes (por ejemplo, páginas de pago). |
| `actionBeforeUpdateQuantity` | Se ejecuta antes de que se actualice la cantidad de un producto en el carrito. | *No utilizado explícitamente para la funcionalidad principal, pero podría ser para futuras características o elementos menores de la interfaz de usuario.* |
| `actionCartSave` | Se ejecuta después de guardar un carrito. | *No utilizado explícitamente para la funcionalidad principal, pero podría ser para futuras características o elementos menores de la interfaz de usuario.* |
| `actionValidateOrder` | Se ejecuta después de validar un pedido. | *Crucial para la lógica del módulo.* Este es el punto donde el módulo interviene para realizar la verificación final de stock *antes* de que el pedido se confirme completamente. El JavaScript del módulo probablemente evita el envío del formulario que activa este hook si se encuentran problemas de stock. |

*Nota: El mecanismo principal del módulo para la verificación de stock es a través de su controlador frontal `AjaxCheck`, que se activa mediante JavaScript en la página de pago, en lugar de depender únicamente de los hooks nativos de PrestaShop para la verificación de stock en sí. Los hooks se utilizan principalmente para cargar activos y potencialmente para mostrar notificaciones.*

## 5. Soporte Oficial y Actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Checkout stock checker PRO", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
