---
title: "Tarjetas de Regalo - vender códigos de cupón - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Tarjetas de Regalo - vender códigos de cupón de MyPresta.eu."
sidebar:
  label: "Tarjetas de Regalo - vender códigos de cupón - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Gift Cards - sell voucher codes en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Tarjetas de Regalo - vender códigos de cupón

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento web modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Tarjetas de Regalo - vender códigos de cupón" ofrece varias pantallas de configuración para gestionar sus tarjetas de regalo de forma eficaz.

### 2.1 Página de configuración principal del módulo (Back Office > Módulos > Gestor de módulos > Configurar Tarjetas de Regalo - vender códigos de cupón)

Esta es la pantalla de configuración principal del módulo, donde se establece el comportamiento general y se accede a otras secciones de gestión.

-   **Qué hace esta configuración:** Esta sección suele contener ajustes globales para el módulo, como habilitar/deshabilitar funciones, enlazar a otras pantallas de gestión y, potencialmente, establecer comportamientos predeterminados para las tarjetas de regalo.
-   **Efecto de cambiar esta configuración:** Los cambios aquí afectarán a cómo se muestran, compran y gestionan las tarjetas de regalo en toda su tienda.
-   **Valor recomendado:** Revise cada opción cuidadosamente. Generalmente, habilite las funciones que pretenda usar y siga las recomendaciones predeterminadas del módulo a menos que tenga una razón específica para cambiarlas.
-   **Escenario / ejemplo del comerciante:** Podría encontrar una configuración aquí para habilitar un enlace dedicado a "Tarjetas de Regalo" en el pie de página de su tienda. Habilitar esto facilitaría a los clientes encontrar y comprar tarjetas de regalo.

### 2.2 Gestión de grupos de tarjetas de regalo (Back Office > Tarjetas de Regalo > Grupos de Tarjetas de Regalo)

Esta pantalla le permite definir diferentes categorías o grupos para sus tarjetas de regalo. Piense en ellos como plantillas o tipos de tarjetas de regalo que desea ofrecer.

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Tarjetas de Regalo > Grupos de Tarjetas de Regalo**
-   **Acciones y configuraciones disponibles:**
    *   **Tabla de listado:** Muestra todos los grupos de tarjetas de regalo existentes. Verá columnas como Nombre del grupo, Valor, Estado (activo/inactivo) y acciones (Editar, Eliminar).
    *   **Añadir nuevo grupo de tarjetas de regalo:** Haga clic en este botón para crear un nuevo tipo de tarjeta de regalo.
        *   **Nombre del grupo:** (por ejemplo, "Tarjeta de regalo de cumpleaños", "Vale de Navidad", "Tarjeta de regalo para cualquier ocasión")
            *   *Qué hace esta configuración:* Este es el nombre interno de su grupo de tarjetas de regalo. Le ayuda a organizar e identificar diferentes tipos de tarjetas de regalo en el back office.
            *   *Efecto de cambiar esta configuración:* Solo afecta a la organización de su back office.
            *   *Valor recomendado:* Descriptivo y claro.
        *   **Valor:** (por ejemplo, "25.00", "50.00", "100.00")
            *   *Qué hace esta configuración:* Esto define el valor monetario de la tarjeta de regalo en este grupo.
            *   *Efecto de cambiar esta configuración:* Esta es la cantidad que los clientes pagarán y los destinatarios recibirán como crédito.
            *   *Valor recomendado:* Denominaciones comunes y atractivas para su mercado objetivo.
        *   **Activo:** (Interruptor Sí/No)
            *   *Qué hace esta configuración:* Controla si las tarjetas de regalo de este grupo están disponibles para su compra en su tienda.
            *   *Efecto de cambiar esta configuración:*
                *   *Cuando está habilitado:* Los clientes pueden ver y comprar tarjetas de regalo de este valor.
                *   *Cuando está deshabilitado:* Las tarjetas de regalo de este valor están ocultas del front office y no se pueden comprar.
            *   *Valor recomendado:* SÍ para las tarjetas de regalo activas que desea vender.
        *   **Otros campos:** Puede incluir opciones para el período de validez, la compra mínima para el canje o restricciones de productos específicos.
            *   *Qué hace esta configuración:* Estos campos le permiten ajustar las condiciones bajo las cuales se puede usar la tarjeta de regalo.
            *   *Efecto de cambiar esta configuración:* Impacta directamente en la usabilidad y las restricciones de la tarjeta de regalo para el destinatario.
            *   *Valor recomendado:* Establezca según la política de su negocio (por ejemplo, 1 año de validez, sin compra mínima).
-   **Efecto de los cambios:** La creación de nuevos grupos le permite ofrecer varias denominaciones de tarjetas de regalo. La edición de grupos cambia el valor o la disponibilidad de los tipos de tarjetas de regalo existentes. La eliminación de un grupo elimina la opción de comprar ese tipo específico de tarjeta de regalo.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Comience creando algunos valores comunes de tarjetas de regalo (por ejemplo, $25, $50, $100).
    2.  A medida que su negocio crezca o para promociones estacionales, añada nuevos grupos con diferentes valores o períodos de validez específicos.
    3.  Desactive los grupos que ya no desee vender, en lugar de eliminarlos, para preservar los datos históricos.

### 2.3 Historial de tarjetas de regalo (Back Office > Tarjetas de Regalo > Historial de Tarjetas de Regalo)

Esta pantalla proporciona una visión general completa de todas las tarjetas de regalo que se han comprado y su estado actual.

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Tarjetas de Regalo > Historial de Tarjetas de Regalo**
-   **Acciones y configuraciones disponibles:**
    *   **Tabla de listado:** Muestra una lista de todos los certificados de regalo generados. Las columnas suelen incluir:
        *   **Código de cupón:** El código único asociado a la tarjeta de regalo.
        *   **Valor original:** El valor inicial de la tarjeta de regalo.
        *   **Saldo actual:** El saldo restante de la tarjeta de regalo (si se ha utilizado parcialmente).
        *   **Correo electrónico del destinatario:** La dirección de correo electrónico de la persona que recibió la tarjeta de regalo.
        *   **Nombre del remitente:** El nombre de la persona que compró la tarjeta de regalo.
        *   **ID de pedido:** El ID del pedido a través del cual se compró la tarjeta de regalo.
        *   **Estado:** (por ejemplo, "Pendiente", "Activo", "Usado", "Expirado").
        *   **Acciones:** Puede incluir opciones para ver los detalles del pedido, reenviar el correo electrónico de la tarjeta de regalo o ajustar manualmente el saldo (usar con precaución).
    *   **Buscar y filtrar:** Herramientas para encontrar tarjetas de regalo específicas por código, correo electrónico, ID de pedido o estado.
-   **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo y gestión. Puede rastrear el uso de las tarjetas de regalo, identificar saldos pendientes y ayudar a los clientes con sus consultas sobre tarjetas de regalo.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revise regularmente esta sección para monitorear las ventas y el canje de tarjetas de regalo.
    2.  Utilice la función de búsqueda para encontrar rápidamente una tarjeta de regalo si un cliente tiene una consulta sobre su saldo o estado.
    3.  Si un cliente informa que no recibió el correo electrónico de su tarjeta de regalo, puede verificar su estado y, potencialmente, reenviarlo desde aquí.

### 2.4 Gestión de vales de tarjetas de regalo (Back Office > Tarjetas de Regalo > Vales de Tarjetas de Regalo)

Esta pantalla está dedicada a la gestión de los códigos de vale individuales generados para cada compra de tarjeta de regalo.

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Tarjetas de Regalo > Vales de Tarjetas de Regalo**
-   **Acciones y configuraciones disponibles:**
    *   **Tabla de listado:** Muestra los códigos de vale de regalo individuales. Las columnas pueden incluir:
        *   **Código de vale:** El código único.
        *   **Grupo de tarjeta de regalo asociado:** A qué tipo de tarjeta de regalo pertenece este vale.
        *   **Valor:** El valor de este vale específico.
        *   **Cliente:** El cliente asociado con el vale (remitente o destinatario).
        *   **Fecha de adición/generación:** Cuándo se creó el vale.
        *   **Estado:** (por ejemplo, "Activo", "Usado", "Expirado").
        *   **Acciones:** Opciones para ver detalles, editar (por ejemplo, cambiar estado, extender validez) o eliminar (usar con extrema precaución ya que esto elimina el vale).
-   **Efecto de los cambios:** Esta pantalla permite un control granular sobre los vales de tarjetas de regalo individuales. Puede activar/desactivar vales manualmente, extender su validez o incluso modificar su valor si es necesario (por ejemplo, para problemas de servicio al cliente).
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Utilice esta pantalla para tareas de gestión avanzadas, como emitir manualmente una tarjeta de regalo como gesto de buena voluntad o resolver problemas específicos de los clientes relacionados con un vale.
    2.  Tenga precaución al editar o eliminar vales, ya que esto afecta directamente el crédito del cliente.
    3.  Esta pantalla proporciona una vista detallada del ciclo de vida de cada vale.

### 2.5 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | *Configuración general* | Varía | Comportamiento global del módulo, opciones de visualización y enlaces a otras áreas de gestión. |
| **Grupos de Tarjetas de Regalo** | **Nombre del grupo** | Descriptivo | Nombre interno para el tipo de tarjeta de regalo. |
| | **Valor** | Denominaciones comunes (por ejemplo, $25, $50) | Valor monetario de la tarjeta de regalo. |
| | **Activo** | SÍ | Controla la visibilidad y la posibilidad de compra del tipo de tarjeta de regalo. |
| | *Período de validez* | Según la política | Define cuánto tiempo es válida la tarjeta de regalo después de la compra. |
| | *Compra mínima para canje* | Según la política | Establece un valor de pedido mínimo para que se pueda usar la tarjeta de regalo. |
| **Historial de Tarjetas de Regalo** | *Código de vale* | N/A | Identificador único para cada tarjeta de regalo comprada. |
| | *Saldo actual* | N/A | Crédito restante en la tarjeta de regalo. |
| | *Estado* | N/A | Rastrea el ciclo de vida de la tarjeta de regalo (Activa, Usada, Expirada). |
| **Vales de Tarjetas de Regalo** | *Código de vale* | N/A | Identificador único para cada vale generado. |
| | *Estado* | N/A | Rastrea el estado del vale individual. |
| | *Acciones de Editar/Eliminar* | Usar con precaución | Permite la modificación o eliminación manual de vales individuales. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no pueden encontrar las tarjetas de regalo en mi tienda.**

-   **R:** Primero, asegúrese de que los "Grupos de Tarjetas de Regalo" que ha creado estén marcados como "Activos" en el Back Office en **Tarjetas de Regalo > Grupos de Tarjetas de Regalo**. Segundo, revise la página de configuración principal de su módulo (Módulos > Gestor de módulos > Configurar Tarjetas de Regalo - vender códigos de cupón) para ver las opciones de mostrar enlaces en el encabezado, pie de página o columnas. Si su tema tiene una gestión de menú personalizada, es posible que deba agregar manualmente un enlace a la página de tarjetas de regalo (generalmente accesible a través de una URL amigable como `sutienda.com/regalos`).

**P2: Un cliente compró una tarjeta de regalo, pero el destinatario no ha recibido el correo electrónico.**

-   **R:** Vaya a **Tarjetas de Regalo > Historial de Tarjetas de Regalo** en su Back Office. Busque la tarjeta de regalo específica por ID de pedido o correo electrónico del remitente/destinatario. Verifique su estado; debería ser "Activo" o "Pendiente" si aún no se ha utilizado. Busque una opción para "Reenviar correo electrónico" para ese vale específico. Además, aconseje al cliente que revise su carpeta de spam/correo no deseado. Asegúrese de que la configuración de correo electrónico de su tienda (Parámetros avanzados > Correo electrónico) esté configurada correctamente y que su servidor pueda enviar correos electrónicos de manera confiable.

**P3: El descuento de la tarjeta de regalo no se aplica en la caja.**

-   **R:** Verifique lo siguiente:
    1.  **Introducción del código:** Asegúrese de que el cliente esté introduciendo el código de la tarjeta de regalo correcto y completo, sin errores tipográficos ni espacios adicionales.
    2.  **Validez:** Verifique el estado de la tarjeta de regalo en **Tarjetas de Regalo > Historial de Tarjetas de Regalo** o **Tarjetas de Regalo > Vales de Tarjetas de Regalo**. ¿Está "Activa"? ¿Ha caducado? ¿Tiene un saldo restante?
    3.  **Compra mínima:** ¿La tarjeta de regalo tiene un requisito de compra mínima que el total del carrito actual no cumple?
    4.  **Restricciones de productos:** ¿Hay alguna categoría de producto o productos específicos excluidos del uso de la tarjeta de regalo? (Esto se configuraría en la configuración del Grupo de Tarjetas de Regalo).
    5.  **Caché:** A veces, borrar la caché de PrestaShop (Parámetros avanzados > Rendimiento) puede resolver problemas de visualización o funcionalidad.

**P4: ¿Puedo personalizar la plantilla de correo electrónico para las tarjetas de regalo?**

-   **R:** Sí, el módulo incluye un gestor de plantillas de correo electrónico. Debería encontrar opciones dentro de la configuración del módulo o una sección dedicada (por ejemplo, en **Tarjetas de Regalo > Plantillas de Correo Electrónico**) para editar el contenido y la apariencia del correo electrónico enviado a los destinatarios de las tarjetas de regalo. Esto le permite personalizar el correo electrónico con su marca e incluir instrucciones o mensajes específicos.

**Q5: ¿Qué sucede si el total del pedido de un cliente es inferior al valor de la tarjeta de regalo?**

-   **R:** El módulo está diseñado para manejar esto. Si el total del pedido es inferior al valor de la tarjeta de regalo, el saldo restante debería permanecer en la tarjeta de regalo, lo que permite al destinatario usarlo para futuras compras hasta que el saldo se agote o la tarjeta caduque. Puede verificar el saldo restante en la sección **Tarjetas de Regalo > Historial de Tarjetas de Regalo**.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Tarjetas de Regalo - vender códigos de cupón" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, aunque no define explícitamente clases `ObjectModel` personalizadas en el directorio `classes/`. En su lugar, aprovecha la funcionalidad principal de `CartRule` (vale) de PrestaShop y extiende las capacidades de administración a través de `AdminController`s dedicados para gestionar grupos de tarjetas de regalo, historial y vales individuales. La interacción del front-office es manejada por `ModuleFrontController`s, principalmente para mostrar tarjetas de regalo y gestionar cuentas de usuario. El módulo se basa en gran medida en el sistema de configuración de PrestaShop (`Configuration::get()`) para sus ajustes y se integra con varios hooks para mostrar contenido y gestionar procesos de pedido.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `controllers/front/gifts.php`
    *   **Nombre de la clase y clase padre**: `GiftcertificateGiftsModuleFrontController` que extiende `ModuleFrontController`
    *   **Responsabilidad**: Este controlador es responsable de mostrar la página principal de tarjetas de regalo en el front office. Recupera los grupos de tarjetas de regalo disponibles y los renderiza utilizando la plantilla `gifts.tpl`, permitiendo a los clientes navegar y seleccionar tarjetas de regalo para su compra.
-   `controllers/front/index.php`
    *   **Nombre de la clase y clase padre**: `GiftcertificateIndexModuleFrontController` que extiende `ModuleFrontController`
    *   **Responsabilidad**: Este es un controlador de marcador de posición o de reserva, a menudo utilizado para redirigir o manejar el enrutamiento base del módulo. En muchos casos, simplemente podría redirigir al controlador `gifts.php` o servir como base para otras acciones del front-office.

#### Controladores de administración del Back-Office

-   `controllers/admin/AdminGiftcertificateGroupController.php`
    *   **Nombre de la pestaña y entidad gestionada**: "Grupos de Tarjetas de Regalo" (bajo el menú principal "Tarjetas de Regalo"). Gestiona entidades `gift_group`.
    *   **Responsabilidad**: Este controlador proporciona la interfaz para crear, editar y eliminar grupos de tarjetas de regalo. Maneja el envío de formularios para definir valores de tarjetas de regalo, nombres y otras configuraciones específicas del grupo. Utiliza `HelperList` y `HelperForm` de PrestaShop para renderizar la cuadrícula y los formularios.
-   `controllers/admin/AdminGiftcertificateHistoryController.php`
    *   **Nombre de la pestaña y entidad gestionada**: "Historial de Tarjetas de Regalo" (bajo el menú principal "Tarjetas de Regalo"). Gestiona entidades `giftcertlist`.
    *   **Responsabilidad**: Este controlador muestra una visión histórica de todas las tarjetas de regalo compradas. Lista códigos de vale, valores, destinatarios y estados. Permite a los administradores rastrear el uso de tarjetas de regalo y, potencialmente, reenviar correos electrónicos. Utiliza `HelperList` de PrestaShop para la vista de cuadrícula e interactúa con claves de configuración como `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` para acciones relacionadas con el correo electrónico.
-   `controllers/admin/AdminGiftcertificateVoucherController.php`
    *   **Nombre de la pestaña y entidad gestionada**: "Vales de Tarjetas de Regalo" (bajo el menú principal "Tarjetas de Regalo"). Gestiona entidades `gift_voucher`.
    *   **Responsabilidad**: Este controlador proporciona una gestión detallada para códigos de vale de tarjetas de regalo individuales. Permite a los administradores ver, editar (por ejemplo, cambiar el estado, extender la validez) o eliminar vales específicos. Utiliza `HelperList` y `HelperForm` de PrestaShop para gestionar registros de vales individuales.
-   `controllers/admin/index.php`
    *   **Nombre de la pestaña y entidad gestionada**: N/A
    *   **Responsabilidad**: Este archivo suele servir como medida de seguridad para evitar la lista directa de directorios o el acceso. Normalmente contiene un simple `header('Location: ../../../index.php'); exit;` o similar para redirigir al administrador principal de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo:

1.  Manipula directamente las tablas de la base de datos utilizando `Db::getInstance()` sin `ObjectModel`s.
2.  Se basa en la clase principal `CartRule` (vale) de PrestaShop para la lógica real del vale, y sus propios controladores de administración gestionan el aspecto de la "tarjeta de regalo" como un envoltorio alrededor de la creación y gestión de `CartRule`.
3.  El archivo principal del módulo (`ajax_giftcertificate.php`) o sus bibliotecas incluidas contienen la lógica principal y el manejo de datos.

### 4.4 Activos JavaScript (`views/js/`)

-   `giftcertificate/js/script.js`
    *   **Alcance**: Probablemente funcionalidad del Front-office o general del módulo.
    *   **Detalles**: Contiene JavaScript general para el módulo, que potencialmente maneja solicitudes AJAX para agregar tarjetas de regalo al carrito, actualizaciones dinámicas en la página de tarjetas de regalo o validaciones de formularios front-end.
-   `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Gestiona la funcionalidad para editar y crear plantillas de correo electrónico dentro de la configuración del módulo. Esto incluiría el manejo de envíos de formularios, llamadas AJAX para guardar plantillas y, potencialmente, integraciones de editores de texto enriquecido.
-   `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Similar al gestor de plantillas de correo electrónico, pero para plantillas PDF, probablemente utilizado para generar tarjetas de regalo imprimibles. Maneja interacciones de formularios, guardado de diseños de plantillas PDF y funcionalidad de vista previa.
-   `giftcertificate/lib/searchTool/views/js/autocomplete.js`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Proporciona funcionalidad de autocompletado para campos de búsqueda dentro de los controladores de administración, como la búsqueda de clientes o productos al crear/editar tarjetas de regalo o vales.
-   `giftcertificate/lib/voucherengine/script.js`
    *   **Alcance**: Probablemente funcionalidad del Front-office o general del módulo.
    *   **Detalles**: Contiene JavaScript específico para la lógica de generación y canje de vales, que potencialmente interactúa con el carrito o el proceso de pago para aplicar descuentos de tarjetas de regalo.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `giftcertificate/css.css`
    *   **Alcance**: General, podría ser front-office o back-office.
    *   **Detalles**: Contiene el estilo principal para los elementos del módulo, que potencialmente incluye el diseño general, los estilos de los botones o los componentes comunes.
-   `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Estilos para la interfaz de gestión de plantillas de correo electrónico, asegurando una apariencia consistente dentro del back office de PrestaShop.
-   `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Estilos para la interfaz de gestión de plantillas PDF, similar al gestor de plantillas de correo electrónico.
-   `giftcertificate/lib/searchTool/views/css/autocomplete.css`
    *   **Alcance**: Back-office (Administración).
    *   **Detalles**: Estilo para los resultados de búsqueda de autocompletado y los campos de entrada.
-   `giftcertificate/lib/voucherengine/ps16.css`
    *   **Alcance**: Front-office (específicamente para temas de PrestaShop 1.6).
    *   **Detalles**: Contiene estilos de compatibilidad para temas de PrestaShop 1.6, abordando posibles diferencias de diseño o elementos para garantizar una visualización adecuada de los componentes de la tarjeta de regalo.
-   `giftcertificate/views/css/giftcertificate.css`
    *   **Alcance**: Front-office (cara al cliente).
    *   **Detalles**: Hoja de estilo principal para la visualización de las tarjetas de regalo en el front-office, incluida la página dedicada a las tarjetas de regalo, los elementos de la página del producto y, potencialmente, el estilo de la sección "Mi Cuenta". Los desarrolladores pueden anular estas clases en el `custom.css` de su tema o en un tema hijo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

-   `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
    *   **Hook**: `displayAdminOrder`
    *   **Salida**: Renderiza información relacionada con las tarjetas de regalo dentro de la página de detalles del pedido de PrestaShop en el Back Office. Esto podría mostrar qué tarjetas de regalo se compraron en el pedido o qué tarjetas de regalo se utilizaron para pagar el pedido.
-   `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
    *   **Hook**: `displayMyAccountBlock` (PrestaShop 1.6)
    *   **Salida**: Añade un enlace o bloque a la página "Mi Cuenta" del cliente, dirigiéndolos a sus tarjetas de regalo compradas o al historial de tarjetas de regalo.
-   `giftcertificate/views/templates/hook/my-account-16.tpl`
    *   **Hook**: `displayCustomerAccount` (PrestaShop 1.6)
    *   **Salida**: Plantilla específica para añadir un enlace a la página "Mi Cuenta" para temas de PrestaShop 1.6.
-   `giftcertificate/views/templates/hook/my-account-17.tpl`
    *   **Hook**: `displayCustomerAccount` (PrestaShop 1.7+)
    *   **Salida**: Plantilla específica para añadir un enlace a la página "Mi Cuenta" para temas de PrestaShop 1.7 y posteriores.
-   `giftcertificate/views/templates/hook/my-account.tpl`
    *   **Hook**: `displayCustomerAccount` (General/Reserva)
    *   **Salida**: Una plantilla general de enlace "Mi Cuenta", potencialmente utilizada como reserva o para versiones anteriores.

#### Plantillas de administración (`views/templates/admin/`)

-   `giftcertificate/views/templates/admin/admin.tpl`
    *   **Alcance**: Configuración general de administración.
    *   **Salida**: Probablemente el formulario de configuración principal para el módulo, renderizado a través de `getContent()` en el archivo principal del módulo. Podría incluir pestañas o secciones para varias configuraciones.
-   `giftcertificate/views/templates/admin/adminOrder.tpl`
    *   **Alcance**: Vista de pedidos de administración.
    *   **Salida**: Similar a `displayAdminOrder.tpl` pero potencialmente para una vista más integrada dentro de una página de pedidos de administración personalizada, si el módulo la anula o la extiende.
-   `giftcertificate/views/templates/admin/list/list_action_email.tpl`
    *   **Alcance**: Vistas de lista de administración (por ejemplo, Historial de Tarjetas de Regalo).
    *   **Salida**: Un botón de acción o enlace específico para enviar correos electrónicos, que normalmente se encuentra en la columna de acción de una tabla `HelperList`, lo que permite a los administradores reenviar correos electrónicos de tarjetas de regalo.

#### Plantillas de Front-office (`views/templates/front/`)

-   `giftcertificate/views/templates/front/gifts.tpl`
    *   **Alcance**: Página dedicada del front-office.
    *   **Salida**: La plantilla principal para mostrar la lista de tarjetas de regalo disponibles a los clientes, renderizada por `GiftcertificateGiftsModuleFrontController`.

#### Plantillas de biblioteca (`lib/`)

-   `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
    *   **Alcance**: Back-office (Administración).
    *   **Salida**: Plantillas para la interfaz de gestión de plantillas de correo electrónico (por ejemplo, `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
-   `giftcertificate/lib/helpers/views/orderStates.tpl`
    *   **Alcance**: Back-office (Administración).
    *   **Salida**: Una plantilla de ayuda, probablemente para mostrar o seleccionar estados de pedido dentro de las configuraciones o formularios del módulo.
-   `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
    *   **Alcance**: Back-office (Administración).
    *   **Salida**: Plantillas para la interfaz de gestión de plantillas PDF (por ejemplo, `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
-   `giftcertificate/lib/searchTool/views/scripts.tpl`
    *   **Alcance**: Back-office (Administración).
    *   **Salida**: Contiene lógica JavaScript o Smarty relacionada con la herramienta de búsqueda, que potencialmente incluye scripts de inicialización para autocompletar.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo probablemente crea tablas personalizadas para gestionar sus datos, aunque no se encontraron definiciones explícitas de `ObjectModel` en `classes/`. Basándose en los Controladores de Administración, se implican las siguientes tablas:

-   `ps_gift_group`: Almacena definiciones para grupos de tarjetas de regalo (por ejemplo, valor, nombre, validez, restricciones).
-   `ps_giftcertlist`: Almacena el historial de tarjetas de regalo compradas, incluidos sus códigos únicos, valor inicial, saldo actual, destinatario, remitente y pedido asociado.
-   `ps_gift_voucher`: Almacena detalles de códigos de vale individuales, potencialmente vinculándose a `ps_cart_rule` si aprovecha el sistema de vales nativo de PrestaShop.

Los registros de configuración almacenados en `ps_configuration` incluirían:

-   Configuraciones específicas del módulo configuradas a través de `getContent()`, como ID de plantilla de correo electrónico, ID de plantilla de PDF, opciones de visualización, etc.
-   `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` son configuraciones principales de PrestaShop utilizadas por el módulo para el envío de correos electrónicos.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar activos CSS/JS, metaetiquetas o datos específicos del módulo. |
| `displayLeftColumn` / `displayRightColumn` | En la columna izquierda/derecha del front office. | Mostrar un bloque para la promoción de tarjetas de regalo o un enlace a la página de tarjetas de regalo. |
| `displayProductAdditionalInfo` / `displayProductButtons` | En la página del producto. | Potencialmente mostrar un botón de "Comprar una tarjeta de regalo" o información relacionada. |
| `displayFooter` | En la sección del pie de página de cada página. | Añadir un enlace a la página de tarjetas de regalo. |
| `displayCustomerAccount` | En la página "Mi Cuenta" del cliente. | Añadir un enlace al historial/detalles de las tarjetas de regalo del cliente. |
| `displayMyAccountBlock` | En la página "Mi Cuenta" del cliente (específico de PrestaShop 1.6). | Añadir un enlace al historial/detalles de las tarjetas de regalo del cliente. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Activar la generación y el envío de vales de tarjetas de regalo cuando se compra un producto de tarjeta de regalo. Actualizar el historial de tarjetas de regalo. |
| `displayAdminOrder` | En la página de detalles del pedido del Back Office. | Mostrar información de la tarjeta de regalo relacionada con el pedido (comprada o utilizada). |
| `actionOrderStatusUpdate` | Cuando el estado de un pedido cambia. | Potencialmente activar/desactivar tarjetas de regalo según el estado del pedido (por ejemplo, activar en "Pago aceptado"). |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su plantilla. | Cargar activos CSS y JavaScript específicos del front-office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su plantilla. | Cargar activos CSS y JavaScript específicos del back-office. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la versión más reciente y segura del módulo "Tarjetas de Regalo - vender códigos de cupón", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia oportuna y mejoras continuas a nuestros módulos.
