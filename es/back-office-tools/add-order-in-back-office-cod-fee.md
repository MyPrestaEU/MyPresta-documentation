---
title: "Añadir pedido en el back office + tarifa contra reembolso - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Añadir pedido en el back office + tarifa contra reembolso' de MyPresta.eu."
sidebar:
  label: "Añadir pedido en el back office + tarifa contra reembolso - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Add order in back office + cod fee en MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Añadir pedido en el back office + tarifa contra reembolso

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
- **Módulo prerrequisito**: Este módulo requiere que un módulo de pago "Contra reembolso con tarifa" esté instalado y configurado en su tienda. Este módulo *amplía* la funcionalidad de dicho módulo de pago dentro del Back Office.

## 2. Recorrido completo de configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo tiene una página de configuración muy sencilla. Su función principal es habilitar o deshabilitar la funcionalidad principal del módulo.

**Acceso:** Back Office > Módulos > Gestor de módulos > Busque "Añadir pedido en el back office + tarifa contra reembolso" > Haga clic en "Configurar"

#### **Habilitar / Deshabilitar la funcionalidad del módulo**

- **Qué hace este ajuste:** Este es un interruptor de palanca estándar que controla si la funcionalidad del módulo está activa o inactiva. Cuando está habilitado, el módulo añadirá automáticamente las tarifas de contra reembolso a los pedidos creados manualmente en el Back Office. Cuando está deshabilitado, esta funcionalidad cesará.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo supervisará activamente el proceso de creación de pedidos del Back Office. Si selecciona un método de pago "Contra reembolso con tarifa" al crear un pedido, la tarifa asociada se calculará y añadirá automáticamente al total del pedido.
  - *Cuando está deshabilitado (NO):* El módulo no interferirá con el proceso de creación de pedidos del Back Office. Si selecciona un método de pago "Contra reembolso con tarifa", la tarifa *no* se añadirá automáticamente, y tendría que ajustar manualmente el total del pedido si desea incluirla.
- **Valor recomendado:** **SÍ**. Para beneficiarse del propósito principal del módulo de automatizar la inclusión de la tarifa de contra reembolso, debe estar habilitado.
- **Escenario / ejemplo de comerciante:** Está tomando un pedido telefónico de un cliente que desea pagar contra reembolso. Va a Back Office > Pedidos > Añadir nuevo pedido. Después de añadir productos y seleccionar al cliente, elige su método de pago "Contra reembolso con tarifa". Si este módulo está habilitado, la tarifa de contra reembolso aparecerá instantáneamente en el resumen del pedido, asegurando que se le cobre correctamente al cliente. Si está deshabilitado, la tarifa faltaría, lo que podría llevar a un total de pedido incorrecto.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar módulo | SÍ | Controla si el módulo añade automáticamente las tarifas de contra reembolso a los pedidos creados manualmente en el Back Office. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero la tarifa de contra reembolso no aparece cuando creo un pedido en el Back Office.**
R:

1. **Verifique el estado del módulo:** Vaya a Módulos > Gestor de módulos y asegúrese de que "Añadir pedido en el back office + tarifa contra reembolso" esté instalado y **habilitado**.
2. **Verifique el prerrequisito:** Este módulo *requiere* que un módulo de pago "Contra reembolso con tarifa" independiente esté instalado y configurado. Asegúrese de tener dicho módulo y de que esté configurado correctamente con sus tarifas. Este módulo *amplía* esa funcionalidad, no proporciona el mecanismo de tarifa de contra reembolso en sí mismo.
3. **Borrar caché:** A veces, la caché de PrestaShop puede evitar que la nueva funcionalidad del módulo aparezca inmediatamente. Vaya a Parámetros avanzados > Rendimiento y haga clic en "Borrar caché" en la esquina superior derecha.
4. **Verifique el método de pago:** Asegúrese de que está seleccionando el método de pago *específico* "Contra reembolso con tarifa" que proporciona su otro módulo, no una opción genérica de "Contra reembolso" sin tarifa.

**P: ¿Afectará este módulo a los pedidos realizados por los clientes en el front-office de mi tienda?**
R: No, este módulo solo afecta el proceso de creación de pedidos *manualmente* en el Back Office de PrestaShop. No altera cómo los clientes realizan pedidos ni cómo se calculan las tarifas en el proceso de pago del front-end.

**P: ¿Qué pasa si tengo varios módulos de "Contra reembolso con tarifa"?**
R: Este módulo está diseñado para integrarse con la forma estándar en que PrestaShop maneja los módulos de pago y sus tarifas asociadas. Debería funcionar con cualquier módulo de "Contra reembolso con tarifa" que registre correctamente su cálculo de tarifas dentro del marco de pago de PrestaShop. Si encuentra problemas, póngase en contacto con el soporte de MyPresta.eu.

**P: ¿Este módulo crea la opción de pago "Contra reembolso con tarifa" por sí mismo?**
R: No, no lo hace. Este módulo es una *mejora* para un módulo de pago "Contra reembolso con tarifa" existente. Debe tener un módulo de pago separado instalado que proporcione el método de pago contra reembolso real y su configuración de tarifa.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Añadir pedido en el back office + tarifa contra reembolso" es un módulo ligero de PrestaShop diseñado principalmente para extender la funcionalidad de `AdminOrdersController`. Logra su propósito al engancharse a acciones específicas dentro del proceso de creación de pedidos del Back Office, específicamente cuando se selecciona o actualiza un método de pago. Su lógica central reside dentro del archivo principal del módulo, aprovechando el sistema de hooks de PrestaShop para modificar el comportamiento existente sin modificar directamente los archivos del núcleo. Se basa en la presencia de un módulo de pago "Contra reembolso con tarifa" separado para proporcionar la lógica real de cálculo de la tarifa.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Su funcionalidad se inyecta en el `AdminOrdersController` existente a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancia de `ObjectModel`. Toda la lógica está contenida dentro del archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La funcionalidad se maneja en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Su configuración se maneja mediante el método estándar `getContent()`, que normalmente utiliza los formularios de ayuda de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

**Tablas de la base de datos**:
Este módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración (por ejemplo, estado de habilitación/deshabilitación) en la tabla estándar `ps_configuration`, utilizando una clave como `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos multimedia. | Se utiliza para inyectar potencialmente JS/CSS si es necesario, aunque este módulo no lo usa para eso. Es un hook común para modificaciones del lado del administrador. |
| `actionAdminOrdersControllerSaveAfter` | Se ejecuta después de que se guarda un pedido en `AdminOrdersController`. | Este es el hook principal utilizado por el módulo. Permite al módulo inspeccionar el pedido recién guardado, verificar el método de pago seleccionado y, si es un contra reembolso con tarifa, aplicar la tarifa. |
| `displayAdminOrder` | Se ejecuta en la página de detalles del pedido en el Back Office. | Podría usarse para mostrar información adicional relacionada con la tarifa de contra reembolso en la vista del pedido, aunque la función principal del módulo es *añadir* la tarifa, no solo mostrarla. |

**Lógica clave dentro de `add-order-in-back-office-cod-fee.php`:**

La funcionalidad principal del módulo probablemente se implementa dentro del método `hookActionAdminOrdersControllerSaveAfter`. Este método:

1. Recuperaría el objeto `Order` que acaba de ser guardado.
2. Identificaría el `PaymentModule` utilizado para el pedido.
3. Comprobaría si el módulo de pago seleccionado es del tipo "Contra reembolso con tarifa" (esto normalmente implica verificar el nombre del módulo o una propiedad/método específico que exponga).
4. Si lo es, llamaría a un método de ese módulo de pago (o calcularía directamente basándose en su configuración) para obtener la tarifa de contra reembolso.
5. Finalmente, actualizaría el total del pedido, añadiría un nuevo detalle de `OrderInvoice` (o modificaría uno existente) para reflejar la tarifa de contra reembolso y persistiría estos cambios en la base de datos. Esto podría implicar la creación de una nueva entrada de `OrderPayment` o el ajuste de los campos `total_paid_tax_incl` y `total_paid_tax_excl` del objeto `Order`.

Los desarrolladores deben tener en cuenta que este módulo depende en gran medida de la estructura interna y el comportamiento del módulo de pago "Contra reembolso con tarifa" con el que interactúa. Cualquier módulo de pago contra reembolso personalizado podría requerir ajustes o comprobaciones de compatibilidad específicas.

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones e información adicional sobre el módulo "Añadir pedido en el back office + tarifa contra reembolso", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/) o póngase en contacto directamente con el soporte de MyPresta.eu.
