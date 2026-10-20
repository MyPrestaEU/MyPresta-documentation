---
title: "Vista Previa Rápida de Pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Vista Previa Rápida de Pedidos de MyPresta.eu."
sidebar:
  label: "Vista Previa Rápida de Pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Quick Order Preview en MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/quick-order-preview/)
>
> ---


# Vista Previa Rápida de Pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Vista Previa Rápida de Pedidos". Esto le llevará a su pantalla de configuración principal.

No hay opciones de configuración específicas en esta pantalla para el módulo "Vista Previa Rápida de Pedidos". El módulo funciona de forma predeterminada mejorando la funcionalidad existente de la página "Pedidos". Su función principal es inyectar el JavaScript y las plantillas necesarias para habilitar la función de vista previa rápida directamente en su lista de pedidos.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### AdminPreviewOrderController (Back Office > Pedidos > Lista de Pedidos)

Este módulo no añade un nuevo elemento de menú a su back office de PrestaShop. En su lugar, mejora la página de lista de **"Pedidos"** existente (que se encuentra en **Back Office > Pedidos > Pedidos**).

- **Nombre de la Pantalla y Ubicación del Menú:** Accede a esta funcionalidad mejorada navegando a **Pedidos > Pedidos** en su back office de PrestaShop.
- **Acciones y Configuraciones Disponibles:**
  - **Funcionalidad de Vista Previa Rápida:** Cuando esté en la página de lista de "Pedidos", simplemente haga clic en cualquier fila de pedido. En lugar de ser redirigido a la página completa de detalles del pedido, el módulo expandirá la fila del pedido para mostrar información clave directamente debajo de ella. Esto incluye:
    - **Dirección del Cliente:** Direcciones de facturación y envío.
    - **Productos Pedidos:** Una lista de los artículos comprados, incluyendo cantidades y precios.
    - **Nota del Cliente:** Si el cliente dejó una nota durante el proceso de compra, será visible aquí.
  - **Botón "Ver Pedido":** Dentro de la vista previa expandida, seguirá encontrando un botón "Ver Pedido" (o un enlace similar) que le permite navegar a la página completa y tradicional de detalles del pedido si necesita realizar acciones como cambiar el estado del pedido, añadir productos o generar facturas.
  - **Guardado de Notas del Cliente:** El módulo también incluye la funcionalidad para guardar notas del cliente directamente desde esta vista previa rápida. Esto se gestiona mediante el script `save-customer-note.js`.
- **Efecto de los cambios:**
  - Al hacer clic en una fila de pedido, ahora se alterna la visualización de su información detallada directamente en la página de la lista de pedidos.
  - Puede revisar rápidamente los datos esenciales del pedido sin salir de la lista principal, acelerando significativamente su flujo de trabajo de procesamiento de pedidos.
  - La capacidad de guardar notas del cliente directamente desde la vista previa agiliza la comunicación y el mantenimiento de registros.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Vaya a **Pedidos > Pedidos**.
  2. Para verificar rápidamente lo que un cliente pidió o su dirección de envío, simplemente haga clic en la fila del pedido en la lista.
  3. Los detalles se expandirán debajo del pedido. Revise la información.
  4. Si necesita cambiar el estado del pedido, imprimir una factura o realizar otras acciones avanzadas, haga clic en el botón "Ver Pedido" dentro de la vista previa expandida para ir a la página completa de detalles del pedido.
  5. Si necesita añadir una nota rápida sobre el cliente o el pedido, utilice el campo de nota del cliente dentro de la vista previa y guárdela.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Lista de Pedidos | Clic en Fila de Pedido | N/A | Expande los detalles del pedido (productos, direcciones, notas) directamente en la página de la lista, ahorrando tiempo de navegación. |
| Lista de Pedidos | Campo de Nota del Cliente | N/A | Permite guardar notas directamente desde la vista previa rápida. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Los detalles del pedido no se expanden cuando hago clic en una fila de pedido. ¿Qué pasa?**
R:

1. **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. A veces, los archivos de caché antiguos impiden que se carguen los nuevos scripts del módulo.
2. **Módulo Habilitado:** Asegúrese de que el módulo "Vista Previa Rápida de Pedidos" esté habilitado en **Módulos > Gestor de Módulos**.
3. **Compatibilidad con el Tema:** Aunque el módulo está diseñado para ser compatible, los temas muy personalizados a veces pueden interferir. Revise la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript. Si ve errores relacionados con el módulo, póngase en contacto con el soporte de MyPresta.eu.
4. **Versión de PrestaShop:** Asegúrese de haber descargado e instalado la versión correcta del módulo para su instalación específica de PrestaShop.

**P: ¿Puedo personalizar qué información se muestra en la vista previa rápida?**
R: El módulo muestra información esencial como productos y direcciones. Personalizar los campos mostrados requeriría la modificación directa de los archivos de plantilla del módulo (`address.tpl`, `products.tpl`). Esta es una tarea a nivel de desarrollador.

**P: ¿Este módulo afecta el rendimiento de mi tienda?**
R: No, el módulo está diseñado para ser ligero. Solo carga contenido adicional cuando hace clic explícitamente en una fila de pedido en el back office. No añade ninguna sobrecarga a su front office o a la navegación general del back office.

**P: Estoy usando una versión anterior de PrestaShop 1.6, ¿funcionará esto?**
R: Sí, el módulo es compatible con PrestaShop 1.6.x. Asegúrese de descargar el paquete correcto para su versión de PrestaShop desde su cuenta MyPresta.eu.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Vista Previa Rápida de Pedidos" (`qov`) es principalmente un módulo de mejora del Back Office. Aprovecha el mecanismo de anulación de `AdminController` de PrestaShop y las plantillas Smarty para inyectar contenido dinámico en la lista de "Pedidos" existente. Utiliza JavaScript para manejar las solicitudes AJAX y la manipulación del DOM para expandir/contraer los detalles del pedido. El módulo no introduce nuevas tablas de base de datos ni estructuras `ObjectModel` complejas, centrándose en aumentar la funcionalidad existente de PrestaShop.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front Office**: Ninguno. Este módulo es puramente una herramienta de Back Office.
- **Controladores de Administración de Back Office**:

  - `qov/controllers/admin/AdminPreviewOrder.php`
    - **Nombre de la Clase y Clase Padre**: `AdminPreviewOrderController` extiende `AdminOrdersController`.
    - **Responsabilidad**: Este controlador anula el `AdminOrdersController` predeterminado para inyectar el JavaScript necesario y potencialmente modificar el método `renderList()` para incluir la funcionalidad de vista previa rápida. Es responsable de manejar las solicitudes AJAX que recuperan los detalles del pedido (productos, direcciones) cuando se hace clic en una fila de pedido, y de renderizar las plantillas `address.tpl` y `products.tpl` con los datos recuperados. También gestiona la clave de configuración `QOV_TRACKING_EMAIL`, aunque su uso directo no es evidente a partir de la información proporcionada.

### 4.3 Clases y Modelos Principales (`classes/`)

Ninguno. El módulo no define clases `ObjectModel` personalizadas ni clases de lógica de negocio complejas. Interactúa principalmente con las clases principales existentes de PrestaShop como `Order`, `Address`, `Product`, etc., a través de su controlador.

### 4.4 Activos JavaScript (`views/js/`)

- `qov/views/js/177-expand-all-imm.js`

  - **Alcance**: Back office (lista de Pedidos, PrestaShop 1.7.7+).
  - **Descripción**: Este script probablemente maneja la expansión inmediata de todos los detalles del pedido en la página de la lista de pedidos, posiblemente para una vista o acción específica. Vincularía eventos de clic a las filas de pedidos y activaría llamadas AJAX para recuperar y mostrar detalles de múltiples pedidos simultáneamente.
- `qov/views/js/177-expand-all.js`

  - **Alcance**: Back office (lista de Pedidos, PrestaShop 1.7.7+).
  - **Descripción**: Similar a `177-expand-all-imm.js`, este script es responsable de la funcionalidad "expandir todo". Escucharía un disparador específico (por ejemplo, un clic de botón) para expandir todos los detalles de pedidos visibles en la página actual, realizando solicitudes AJAX para cada pedido.
- `qov/views/js/177orders-multiple.js`

  - **Alcance**: Back office (lista de Pedidos, PrestaShop 1.7.7+).
  - **Descripción**: Este es el script principal que habilita la funcionalidad de vista previa rápida. Vincula eventos de clic a filas de pedidos individuales en la lista `AdminOrders`. Cuando se hace clic en una fila de pedido, evita la navegación predeterminada a la página completa del pedido. En su lugar, realiza una solicitud AJAX al `AdminPreviewOrderController` (o un endpoint similar) para recuperar los productos, direcciones y otros detalles del pedido. Luego, inyecta dinámicamente el HTML renderizado (de `address.tpl` y `products.tpl`) en una nueva fila o una sección expandida debajo de la fila de pedido clicada. También maneja el colapso de los detalles cuando se vuelve a hacer clic en la fila.
- `qov/views/js/save-customer-note.js`

  - **Alcance**: Back office (lista de Pedidos, específicamente dentro de la vista previa rápida).
  - **Descripción**: Este script maneja la funcionalidad para guardar notas del cliente directamente desde la vista previa rápida del pedido. Se vincula a campos de entrada o botones dentro de los detalles del pedido expandidos. Cuando se introduce o actualiza una nota, envía una solicitud AJAX a un endpoint del back office (probablemente el `AdminPreviewOrderController` o el `AdminOrdersController` predeterminado con una acción específica) para persistir la nota en la base de datos, típicamente en la tabla `ps_order_note` o similar.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Ninguno. El módulo no incluye archivos CSS personalizados. Probablemente se basa en el estilo existente del back office de PrestaShop o en estilos en línea para los detalles del pedido expandidos. Los desarrolladores que deseen estilizar la vista previa deben apuntar a los elementos HTML inyectados dinámicamente.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `qov/views/templates/admin/address.tpl`
    - **Descripción**: Esta plantilla se utiliza para renderizar los detalles de la dirección de facturación y envío del cliente dentro de la vista previa rápida del pedido. Recibe los datos de la dirección del `AdminPreviewOrderController` y los formatea para su visualización.
  - `qov/views/templates/admin/products.tpl`
    - **Descripción**: Esta plantilla es responsable de renderizar la lista de productos pedidos por el cliente dentro de la vista previa rápida del pedido. Recibe los datos del producto (nombre, cantidad, precio, etc.) y los muestra en un formato claro, tabular o de lista.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada. Lee y potencialmente escribe (para notas de clientes) en tablas estándar de PrestaShop como `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer` y `ps_order_note`.
  - Los valores de configuración se almacenan en `ps_configuration`, específicamente `QOV_TRACKING_EMAIL`.
- **Tabla de Hooks Registrados**:
  El módulo no registra explícitamente ningún hook de front office (como `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`) ya que es un módulo de back office. Su funcionalidad se inyecta principalmente anulando el `AdminOrdersController` y añadiendo JavaScript y plantillas a la página existente de "Pedidos" del Back Office.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un Controlador de Administración establece sus activos multimedia. | Utilizado por `AdminPreviewOrderController` para encolar sus archivos JavaScript (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) para la página `AdminOrders`. |
| `displayAdminOrder` | Se ejecuta en la página de Pedidos de Administración. | Aunque no se enumera explícitamente como un hook, la funcionalidad principal del módulo se logra anulando `AdminOrdersController` y modificando su método `renderList()` o inyectando contenido a través de JavaScript en la lista de pedidos existente. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Vista Previa Rápida de Pedidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier pregunta o problema que pueda encontrar.
