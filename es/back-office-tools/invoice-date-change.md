---
title: "Cambio de fecha de factura - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio de fecha de factura' de MyPresta.eu."
sidebar:
  label: "Cambio de fecha de factura - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Invoice date change en MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/invoice-date-change/)
>
> ---


# Cambio de fecha de factura

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Cambio de fecha de factura". Esto le llevará a la pantalla de configuración principal.

En esta pantalla, encontrará la funcionalidad principal del módulo, que le permite establecer la fecha de factura deseada para un pedido.

**Cómo usarlo:**

1. **Navegue a un pedido:**
   - Vaya a **Pedidos > Pedidos** en su Back Office de PrestaShop.
   - Haga clic en un pedido existente para ver sus detalles.
2. **Localice la sección de fecha de factura:**
   - En la página de detalles del pedido, desplácese hacia abajo. Encontrará una nueva sección o bloque relacionado con "Cambio de fecha de factura".
   - Esta sección aparecerá típicamente dentro del bloque "Documentos" o un área similar donde se gestionan las facturas.
3. **Seleccione la fecha deseada:**
   - Verá un campo de selección de fecha. Haga clic en este campo para abrir un calendario.
   - Elija la fecha exacta que desea que aparezca en la factura. Esta puede ser una fecha pasada o una fecha futura.
4. **Guarde sus cambios:**
   - Después de seleccionar la fecha, habrá un botón "Guardar" o "Actualizar" dentro de esta sección. Haga clic en él para aplicar la nueva fecha de factura al pedido.
5. **Genere o regenere la factura:**
   - Una vez que la fecha se haya guardado, si genera una nueva factura para este pedido (o regenera una existente), el PDF reflejará la fecha que acaba de establecer.

**Qué hace esta configuración:** Este módulo no tiene un interruptor global de "encendido/apagado" ni configuraciones complejas. Su función principal es inyectar un selector de fecha directamente en las páginas de detalles de su pedido en el Back Office. Este selector de fecha le permite anular manualmente la fecha de generación de factura predeterminada para pedidos individuales.

**Efecto de cambiar esta configuración:**

- *Cuando selecciona una fecha y guarda:* La fecha elegida se almacena para ese pedido específico. Cualquier factura generada para este pedido *después* de haber establecido esta fecha utilizará la fecha seleccionada en lugar de la fecha actual del sistema.
- *Cuando no utiliza el selector de fecha del módulo:* PrestaShop continuará generando facturas con la fecha actual, como lo hace por defecto.

**Valor recomendado:** Utilice el selector de fecha para seleccionar la fecha exacta requerida para cada factura específica. No hay un "valor recomendado" global, ya que la fecha variará por pedido.

**Escenario / ejemplo de comerciante:**
Imagine que un cliente realizó un pedido el 15 de enero, pero debido a un retraso en el stock, el producto solo se envió y facturó el 25 de enero. Sin embargo, por motivos contables, necesita que la fecha de la factura refleje la fecha original del pedido del 15 de enero.

1. Va a la página de detalles de este pedido específico.
2. En la sección "Cambio de fecha de factura", abre el calendario y selecciona el 15 de enero.
3. Hace clic en "Guardar".
4. Ahora, cuando genere la factura en PDF para este pedido, mostrará "15 de enero" como fecha de la factura, aunque la haya generado el 25 de enero.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de detalles del pedido (Back Office) | Selector de fecha (dentro de la sección "Cambio de fecha de factura") | Varía por pedido | Permite la selección manual de la fecha de emisión de la factura para un pedido específico. La fecha seleccionada aparecerá en la factura PDF generada, anulando la fecha actual predeterminada. |
| Página de detalles del pedido (Back Office) | Botón Guardar/Actualizar | N/A | Aplica la fecha de factura seleccionada al pedido actual. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Cambié la fecha, pero la factura sigue mostrando la fecha antigua. ¿Qué pasa?**
R: Asegúrese de haber hecho clic en el botón "Guardar" o "Actualizar" después de seleccionar la nueva fecha en la página de detalles del pedido. Además, asegúrese de estar generando una *nueva* factura o *regenerando* la existente *después* de guardar la nueva fecha. Si está viendo un PDF ya descargado, no se actualizará mágicamente. Debe descargarlo de nuevo.

**P: El selector de fecha no aparece en la página de mi pedido.**
R:

1. **Verifique la instalación del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Cambio de fecha de factura" esté instalado y habilitado.
2. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop necesita una actualización de caché para mostrar nuevos elementos del módulo.
3. **Compatibilidad con el tema:** Aunque el módulo está diseñado para integrarse sin problemas, los temas muy personalizados pueden interferir ocasionalmente. Si borrar la caché no ayuda, cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el selector de fecha. Si lo hace, su tema podría requerir un pequeño ajuste.

**P: ¿Puedo cambiar la fecha de varias facturas a la vez?**
R: No, este módulo está diseñado para cambios individuales de fecha de factura de pedidos. Debe ir a la página de detalles de cada pedido para establecer su fecha de factura específica. No hay una función de edición masiva.

**P: ¿Este módulo afecta otras fechas en PrestaShop, como la fecha del pedido o la fecha de pago?**
R: No, este módulo *solo* cambia la fecha de emisión que aparece en la factura PDF generada. No altera la fecha de creación del pedido, la fecha de pago ni ninguna otra marca de tiempo asociada con el pedido en su base de datos.

**P: ¿Funcionará este módulo con mi plantilla de factura personalizada?**
R: Sí, el módulo inyecta la fecha elegida en el proceso de generación de facturas estándar de PrestaShop. Siempre que su plantilla de factura personalizada utilice correctamente las variables estándar para la fecha de la factura, debería mostrar la fecha establecida por el módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Cambio de fecha de factura" es un módulo ligero de PrestaShop diseñado principalmente para extender la funcionalidad de gestión de pedidos del Back Office. Aprovecha el sistema de hooks de PrestaShop para inyectar un campo de entrada de fecha personalizado en la página de detalles del pedido. Cuando se selecciona y guarda una nueva fecha, actualiza el campo `invoice_date` del objeto `OrderInvoice`, asegurando que las posteriores generaciones de facturas en PDF reflejen la fecha definida por el usuario. Sigue un enfoque simple y directo sin estructuras MVC complejas ni tablas de base de datos personalizadas, basándose en las funcionalidades principales existentes de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda la lógica se maneja dentro del archivo principal del módulo (`invoicedate/index.php`) y a través del sistema de hooks de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado en el directorio `classes/`. Interactúa directamente con el objeto `OrderInvoice` principal y sus propiedades.

### 4.4 Activos de JavaScript (`views/js/`)

No se incluyen archivos JavaScript personalizados en este módulo. La funcionalidad del selector de fecha suele ser proporcionada por las bibliotecas JavaScript principales de PrestaShop (por ejemplo, jQuery UI Datepicker) que ya están cargadas en el Back Office.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se incluyen archivos CSS personalizados en este módulo. El estilo para el selector de fecha y los elementos circundantes se basa en el CSS predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza dos plantillas específicas para mostrar el campo de entrada de fecha en la página de detalles del pedido, dependiendo de la versión de PrestaShop.

- **Plantillas de hook (`views/templates/hook/`)**:
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook**: Esta plantilla se renderiza en el hook `displayAdminOrder`, específicamente para las versiones de PrestaShop 1.6.x.
    - **Propósito**: Genera la estructura HTML para el campo de entrada de la fecha de la factura (un selector de fecha) y un botón de envío dentro de la página de detalles del pedido en el Back Office de PrestaShop 1.6. Permite al administrador seleccionar y guardar una fecha de factura personalizada para el pedido actual.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook**: Esta plantilla se renderiza en el hook `displayAdminOrder`, específicamente para PrestaShop 1.7.x y versiones más recientes.
    - **Propósito**: Similar a la versión 1.6, esta plantilla proporciona el HTML para el campo de entrada de la fecha de la factura y el botón de envío, adaptado a las diferencias estructurales y de estilo de la página de pedidos del Back Office de PrestaShop 1.7+.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  Este módulo no crea ninguna tabla de base de datos personalizada nueva. Modifica el campo `invoice_date` de la tabla `ps_order_invoice` existente (o `_order_invoice` dependiendo de su prefijo) cuando se actualiza una fecha de factura a través de la interfaz del módulo.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayAdminOrder` | Se ejecuta en la página de detalles del pedido del Back Office de PrestaShop. | Este hook se utiliza para inyectar el HTML personalizado del módulo (el selector de fecha y el botón de guardar) en la vista de detalles del pedido, permitiendo al comerciante interactuar con la configuración de la fecha de la factura. El módulo utiliza plantillas específicas de la versión (`displayAdminOrder16.tpl` o `displayAdminOrder17.tpl`) para este hook. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio de fecha de factura", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.
"""
