---
title: "Página de confirmación de pedido para pedidos gratuitos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Página de confirmación de pedido para pedidos gratuitos' de MyPresta.eu."
sidebar:
  label: "Página de confirmación de pedido para pedidos gratuitos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order confirmation page for free orders en MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Página de confirmación de pedido para pedidos gratuitos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y son suficientes para este módulo.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Página de confirmación de pedido para pedidos gratuitos)

Esta es la pantalla de configuración principal y única para el módulo. Es sencilla y le permite habilitar o deshabilitar la funcionalidad principal del módulo.

![Captura de pantalla de configuración del módulo (marcador de posición)]

- **Activar la página de confirmación de pedido**
  - **Qué hace esta configuración:** Este es el interruptor principal para activar o desactivar la funcionalidad del módulo. Controla si los pedidos gratuitos muestran la página de confirmación estándar o vuelven al comportamiento predeterminado de PrestaShop (redirigiendo al historial de pedidos).
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitado (seleccionado "Activado"):* Todos los pedidos, incluidos aquellos con un total de 0,00 €, mostrarán la página estándar de "Confirmación de pedido" después del pago.
    - *Cuando está deshabilitado (seleccionado "Desactivado"):* Los pedidos gratuitos volverán al comportamiento predeterminado de PrestaShop, redirigiendo a los clientes directamente a su página de historial de pedidos en lugar de mostrar la página de confirmación.
  - **Valor recomendado:** **Activado**. Este es el propósito principal del módulo y proporciona una mejor experiencia al cliente.
  - **Escenario / ejemplo de comerciante:** Si ofrece una descarga gratuita de un libro electrónico, habilitar esto asegura que los clientes vean una página de confirmación con un enlace de descarga, en lugar de confundirse con una redirección directa a su historial de pedidos. Si desea volver temporalmente al comportamiento predeterminado de PrestaShop para pedidos gratuitos (por ejemplo, para pruebas específicas), puede deshabilitarlo.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Activar la página de confirmación de pedido | Activado | Controla si los pedidos gratuitos muestran la página de confirmación de pedido estándar (Activado) o redirigen al historial de pedidos (Desactivado). |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis pedidos gratuitos siguen redirigigiéndose a la página de historial de pedidos, incluso después de habilitar el módulo. ¿Qué debo hacer?**
R:

1. **Verifique el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Página de confirmación de pedido para pedidos gratuitos" esté instalado y habilitado.
2. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos > Configurar** para este módulo y asegúrese de que la configuración "Activar la página de confirmación de pedido" esté establecida en **"Activado"**.
3. **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Esto suele ser necesario después de los cambios de configuración del módulo.
4. **Caché del navegador:** Intente borrar la caché de su navegador o pruebe en una ventana de navegación de incógnito/privada para descartar problemas de caché local.

**P: ¿Este módulo afectará a mis pedidos pagados?**
R: No, este módulo se dirige específicamente al comportamiento de los pedidos con un total de 0,00 €. Los pedidos pagados seguirán mostrando la página de confirmación de pedido estándar como siempre lo han hecho.

**P: ¿Este módulo requiere alguna modificación especial del tema?**
R: No, el módulo funciona anulando un controlador principal de PrestaShop. Aprovecha la plantilla de página de confirmación de pedido existente de su tema. No se requieren modificaciones del tema. Si su página de confirmación de pedido se ve bien para los pedidos pagados, también se verá bien para los pedidos gratuitos.

**P: ¿Qué pasa si quiero mostrar contenido diferente en la página de confirmación para pedidos gratuitos versus pedidos pagados?**
R: Este módulo asegura que se muestre la *misma* página de confirmación. Para mostrar contenido diferente, necesitaría personalizar su plantilla `order-confirmation.tpl` (generalmente encontrada en `themes/su-tema/templates/checkout/`) para incluir lógica condicional basada en el total del pedido o el método de pago. Esto requeriría asistencia de un desarrollador.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Página de confirmación de pedido para pedidos gratuitos" logra su funcionalidad anulando un controlador frontal principal de PrestaShop. Específicamente, se dirige a `OrderConfirmationController` para modificar la lógica de redirección que ocurre después de que se realiza un pedido gratuito. Este es un mecanismo de anulación estándar de PrestaShop, lo que garantiza un impacto mínimo en los archivos principales y permite una fácil desinstalación.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:
  - `freeorderconfirmation/override/controllers/front/index.php`
    - Este archivo es un marcador de posición o un artefacto del proceso de anulación. En PrestaShop 1.7+, las anulaciones suelen manejarse colocando la clase anulada directamente en el directorio `override/classes` o `override/controllers`, y el autocargador de PrestaShop se encarga del resto. Este archivo `index.php` en sí mismo no contiene una definición de clase ni lógica directa para la funcionalidad del módulo. Su presencia asegura que el mecanismo de anulación se active correctamente para el `OrderConfirmationController`.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Nombre de la clase y clase padre**: `OrderConfirmationController` (anula la clase principal `OrderConfirmationController`).
    - **Responsabilidad**: Este es el núcleo de la funcionalidad del módulo. Anula el método `initContent()` (o lógica similar dentro del ciclo de vida del controlador) del `OrderConfirmationController` original. La lógica original de PrestaShop verifica si el total del pedido es cero y, si es así, redirige al cliente a su historial de pedidos. Este controlador anulado elimina o modifica esa redirección condicional, asegurando que el método `initContent()` del `OrderConfirmationController` estándar (que renderiza la página de confirmación) siempre se ejecute, incluso para pedidos gratuitos. Evita efectivamente la llamada a `Tools::redirect()` para pedidos de valor cero.

### 4.3 Clases y modelos principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. El módulo opera puramente anulando un controlador principal de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

No se incluyen archivos JavaScript personalizados con este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se incluyen archivos CSS personalizados con este módulo. El módulo se basa en el estilo existente del tema para la página de confirmación de pedido.

### 4.6 Estructura de plantilla Smarty (`views/templates/`)

No se incluyen archivos de plantilla Smarty personalizados con este módulo. El módulo asegura que la plantilla de confirmación de pedido *estándar* de PrestaShop (normalmente `themes/su-tema/templates/checkout/order-confirmation.tpl`) se renderice para pedidos gratuitos, tal como lo hace para pedidos pagados.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla SQL personalizada.
  - Almacena sus configuraciones (por ejemplo, `freeorderconfirmation_oc`) en la tabla `ps_configuration`.
  - También almacena `mypresta_updates`, `update_`, `updatev_` para el seguimiento interno de actualizaciones por parte de MyPresta.eu.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus medios (CSS/JS). | Utilizado por el módulo para incluir potencialmente sus propios activos para la página de configuración del back-office. En el caso de este módulo, es probable que se utilice para asegurar que el formulario de configuración del módulo se renderice correctamente dentro de la interfaz de administración de PrestaShop, incluso si no se cargan explícitamente activos personalizados. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo está disponible para ayudar con cualquier problema o pregunta relacionada con el módulo "Página de confirmación de pedido para pedidos gratuitos".
