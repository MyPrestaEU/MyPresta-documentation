---
title: "Cambio de número de factura - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio de número de factura' de MyPresta.eu."
sidebar:
  label: "Cambio de número de factura - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Invoice number change en MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/invoice-number-change/)
>
> ---


# Cambio de número de factura

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, navegue a **Módulos > Gestor de módulos** y busque "Cambio de número de factura". Haga clic en el botón "Configurar".

Este módulo no tiene una pantalla de configuración separada con múltiples ajustes. Su funcionalidad está integrada directamente en la página de detalles del pedido en su Back Office. El botón "Configurar" simplemente confirmará que el módulo está instalado y listo para usar.

La funcionalidad principal de este módulo es añadir un nuevo campo o modificar una visualización existente en la página de detalles del pedido, permitiéndole editar el número de factura directamente.

**Cómo usar el módulo:**

1.  **Navegue a un pedido:** En su Back Office de PrestaShop, vaya a **Pedidos > Pedidos**.
2.  **Seleccione un pedido:** Haga clic en cualquier pedido para ver sus detalles.
3.  **Localice la sección de facturas:** Desplácese por la página de detalles del pedido hasta que encuentre la sección "Documentos" o "Facturas".
4.  **Editar número de factura:** Ahora verá un campo editable o un botón junto al número de factura que le permite cambiarlo.
    -   **Qué hace este ajuste:** Esta función le permite escribir directamente un nuevo número de factura para una factura específica asociada con el pedido actual.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando introduce un nuevo número y guarda:* El número de factura para esa factura de pedido específica se actualizará en su base de datos y se reflejará en el documento de factura en sí (si se regenera o se visualiza). Este cambio es permanente y afecta a sus registros financieros.
    -   **Valor recomendado:** Solo cambie los números de factura cuando sea absolutamente necesario y siempre verifique la precisión. Asegúrese de que el nuevo número siga su esquema de numeración interno o los requisitos legales.
    -   **Escenario / ejemplo de comerciante:** Un pedido fue facturado inicialmente como INV00123. Debido a una migración de datos, necesita que esta factura sea INV2024-005. Navegaría al pedido, encontraría INV00123, haría clic para editar, introduciría INV2024-005 y guardaría.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de detalles del pedido (sección Documentos/Facturas) | Número de factura (campo editable) | N/A (depende de la factura existente) | Permite la modificación directa de un número de factura para un pedido específico. Crucial para correcciones, cumplimiento o integración con sistemas externos. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: He instalado el módulo, pero no veo ninguna página de configuración nueva. ¿Está funcionando?**
R1: Sí, el módulo funciona según lo previsto. Este módulo no añade una página de configuración separada. Su funcionalidad está integrada directamente en la página de detalles del pedido. Navegue a **Pedidos > Pedidos**, seleccione un pedido y debería encontrar un campo editable o una opción para cambiar el número de factura dentro de la sección "Documentos" o "Facturas".

**P2: Cambié un número de factura, pero el número antiguo sigue apareciendo en la factura PDF.**
R2: Después de cambiar el número de factura en el Back Office, es posible que deba regenerar la factura PDF para ese pedido para que el nuevo número se refleje. PrestaShop a menudo almacena en caché el contenido PDF. Descargue la factura nuevamente desde la página de detalles del pedido y debería mostrar el número actualizado.

**P3: ¿Puedo revertir un cambio de número de factura?**
R3: El módulo le permite cambiar el número a lo que desee. Si necesita revertir, simplemente editaría el campo nuevamente e introduciría el número original (si lo recuerda o lo tiene registrado). El módulo no mantiene un historial de cambios por sí mismo, por lo que se recomienda un registro cuidadoso por su parte.

**P4: ¿Cambiar un número de factura afectará mis informes contables en PrestaShop?**
R4: Sí, cambiar un número de factura actualizará el campo `invoice_number` en su base de datos para esa factura específica. Cualquier informe de PrestaShop que extraiga los números de factura directamente de la base de datos reflejará el nuevo número. Asegúrese de que sus cambios sean consistentes con sus prácticas contables.

**P5: El módulo no parece estar activo en mi tema personalizado. ¿Qué debo hacer?**
R5: Este módulo utiliza el sistema de sobrescritura de PrestaShop para modificar el comportamiento central y se engancha a las plantillas de administración estándar. Debería funcionar con la mayoría de los temas personalizados sin problemas, ya que solo afecta al Back Office. Si encuentra problemas, primero borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). Si el problema persiste, podría ser un conflicto con otro módulo o una plantilla de administración altamente personalizada. Póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema y cualquier otro módulo relevante.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Cambio de número de factura" (`invoicenb`) está diseñado para extender la funcionalidad central de gestión de facturas de PrestaShop sin alterar el esquema de la base de datos. Esto se logra principalmente a través de una `override` de la clase `OrderInvoice` y enganchándose a la página de detalles del pedido del Back Office para proporcionar una interfaz editable para el número de factura. Este enfoque garantiza un impacto mínimo en el sistema central al tiempo que proporciona la característica deseada.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Toda la funcionalidad se integra a través del archivo principal del módulo, las sobrescrituras y los ganchos de plantilla.

### 4.3 Clases y modelos principales (`classes/`)

-   **`invoicenb/override/classes/order/OrderInvoice.php`**
    -   **Nombre de la clase**: `OrderInvoice` (sobrescribe la clase `OrderInvoice` principal)
    -   **Clase padre**: `OrderInvoiceCore`
    -   **Responsabilidad**: Esta sobrescritura es el núcleo de la funcionalidad del módulo. Modifica el comportamiento de la clase `OrderInvoice`, específicamente cómo se manejan y potencialmente se guardan los números de factura. La sobrescritura es responsable de permitir que el número de factura se actualice desde el Back Office. Es probable que añada o modifique un método para facilitar el guardado de un nuevo número de factura cuando se envía a través de la interfaz de administración.
    -   **Tabla de la base de datos**: `ps_order_invoice` (o su prefijo de tabla)
    -   **Campos `$definition`**: Esta sobrescritura funciona con la `$definition` existente de `OrderInvoiceCore`, particularmente el campo `number`.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La funcionalidad de edición interactiva se maneja directamente dentro de las plantillas Smarty y potencialmente a través de mecanismos AJAX estándar de PrestaShop si se trata de un envío de formulario.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo para el campo editable o el botón en la página del pedido se basará en el CSS predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo utiliza plantillas para inyectar el campo editable del número de factura en la página de detalles del pedido del Back Office.

-   **Plantillas de gancho (`views/templates/hook/`)**:
    -   **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
        -   **Gancho**: `displayAdminOrder` (para PrestaShop 1.6.x)
        -   **Propósito**: Esta plantilla se renderiza en la página de detalles del pedido en PrestaShop 1.6.x. Inyecta los elementos del formulario HTML (por ejemplo, un campo de entrada y un botón de guardar) que permiten al administrador ver y modificar el número de factura para un pedido específico. Probablemente incluye lógica para mostrar el número de factura actual y manejar el envío de uno nuevo.
    -   **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
        -   **Gancho**: `displayAdminOrder` (para PrestaShop 1.7.x, 8.x, 9.x)
        -   **Propósito**: Similar a `displayAdminOrder16.tpl`, pero adaptada para la estructura de la plantilla y los parámetros de gancho potencialmente diferentes de PrestaShop 1.7.x y versiones más recientes. Proporciona la misma funcionalidad: mostrar un campo de número de factura editable en la página de detalles del pedido.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada nueva. Interactúa con la tabla `ps_order_invoice` existente (o su prefijo de tabla) para actualizar la columna `number`.
    -   Los registros de configuración se almacenan en `ps_configuration` para la configuración interna del módulo (si la hay, aunque este módulo parece tener una configuración explícita mínima).
-   **Tabla de ganchos registrados**:

    | Nombre del gancho | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `displayAdminOrder` | Renderiza contenido en la página de detalles del pedido del Back Office. | Se utiliza para inyectar el formulario HTML para editar el número de factura directamente en la vista del pedido. El módulo proporciona plantillas separadas para PrestaShop 1.6 y 1.7+ para este gancho. |
    | `actionObjectOrderInvoiceUpdateAfter` | Se ejecuta después de que se ha actualizado un objeto `OrderInvoice`. | (Implícito, si la sobrescritura lo usa) Podría usarse para activar acciones adicionales o registrar después de que un número de factura se haya cambiado con éxito. |
    | `actionObjectOrderInvoiceAddAfter` | Se ejecuta después de que se ha añadido un objeto `OrderInvoice`. | (Implícito, si la sobrescritura lo usa) Podría usarse para modificar el número de factura inicial al crearse, aunque el enfoque principal es cambiar los existentes. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio de número de factura", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las versiones más recientes desde su historial de pedidos y acceder a nuestros canales de soporte dedicados para cualquier asistencia técnica o consulta.
