---
title: "Cambio automático de estado de pedido - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio automático de estado de pedido' de MyPresta.eu."
sidebar:
  label: "Cambio automático de estado de pedido - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Auto order status change en MyPresta.eu](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/auto-order-status-change/)
>
> ---


# Cambio automático de estado de pedido

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Cambio automático de estado de pedido)

Esta es la pantalla de configuración principal y única para el módulo "Cambio automático de estado de pedido". Aquí, definirá las reglas para cómo los estados de los pedidos transicionan automáticamente.

La página de configuración le presentará una lista de sus estados de pedido actuales. Para cada estado, podrá definir a qué nuevo estado debe cambiar automáticamente.

**Cómo configurar una regla:**

1. **Identifique el estado "Desde":** En el lado izquierdo de la tabla de configuración, verá una lista de todos sus estados de pedido existentes (por ejemplo, "Esperando pago por transferencia bancaria", "Pago aceptado", "Enviado", etc.). Este es el *estado inicial* que activa el cambio automático.
2. **Seleccione el estado "A":** Junto a cada estado "Desde", encontrará un menú desplegable. Este menú contiene todos los estados de pedido disponibles en su tienda. Seleccione el estado al que desea que el pedido *cambie automáticamente* cuando entre en el estado "Desde".
3. **Guarde sus cambios:** Después de configurar las transiciones deseadas, asegúrese de hacer clic en el botón **"Guardar"** (normalmente en la parte inferior de la página) para aplicar sus reglas.

Desglosemos los ajustes típicos que encontrará:

#### **Grupo de ajustes: Transiciones automáticas de estado**

Esta sección mostrará una tabla o una serie de menús desplegables, lo que le permitirá mapear los estados "Desde" a los estados "A".

- **Qué hace este ajuste:** Esta es la funcionalidad principal del módulo. Para cada estado de pedido existente en su tienda, puede especificar un *estado de destino* al que un pedido transicionará automáticamente *si* su estado cambia al estado "Desde".
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona un estado "A" para un estado "Desde":* Siempre que el estado de un pedido se actualice al estado "Desde" (ya sea manualmente por un administrador, por una pasarela de pago o por otro módulo), el módulo intentará inmediatamente cambiarlo al estado "A" seleccionado.
  - *Cuando se selecciona "Sin cambio" o similar (o se deja en blanco):* Si no selecciona un estado "A" para un estado "Desde" particular, no se producirá ningún cambio automático para los pedidos que entren en ese estado "Desde" específico. El pedido simplemente permanecerá en el estado "Desde" hasta que se cambie manualmente o se actúe sobre él mediante otra regla/módulo.
- **Valor recomendado:** Esto depende completamente del flujo de trabajo de su tienda.
  - **Ejemplo 1 (Pago aceptado a En proceso):**
    - **Estado Desde:** `Pago aceptado`
    - **Estado A:** `Procesando en curso` (o `Preparación en curso`)
    - **Propósito e impacto:** Esta es una configuración muy común y altamente recomendada. Cuando un cliente paga y el pago se confirma (por ejemplo, por PayPal, Stripe, módulo de tarjeta de crédito), el estado del pedido se actualiza automáticamente a "Pago aceptado". Esta regla lo mueve inmediatamente a "En proceso", indicando a su almacén o equipo de cumplimiento que comience a preparar el pedido sin ninguna intervención manual. Esto ahorra tiempo y garantiza un cumplimiento rápido.
  - **Ejemplo 2 (Enviado a Entregado):**
    - **Estado Desde:** `Enviado`
    - **Estado A:** `Entregado`
    - **Propósito e impacto:** Si bien "Enviado" indica que el artículo ha salido de su almacén, "Entregado" confirma que ha llegado al cliente. Si la integración de su transportista no se actualiza automáticamente a "Entregado", podría establecer esta regla. Sin embargo, tenga cuidado: esto asume que todos los pedidos "Enviados" finalmente son "Entregados". A menudo es mejor confiar en el seguimiento del transportista para el estado "Entregado" si es posible. Use esto si desea eliminar rápidamente los pedidos "Enviados" de su lista activa después de un tiempo de entrega razonable, pero tenga en cuenta que podría no reflejar la entrega real.
  - **Ejemplo 3 (Esperando transferencia bancaria a Cancelado - con precaución):**
    - **Estado Desde:** `Esperando pago por transferencia bancaria`
    - **Estado A:** `Cancelado`
    - **Propósito e impacto:** Si tiene una política estricta de que los pagos por transferencia bancaria deben recibirse dentro de un cierto plazo, y cambia manualmente los pedidos vencidos a "Cancelado", este módulo podría automatizar eso. Sin embargo, el módulo se activa *cuando el estado cambia a* "Esperando pago por transferencia bancaria". Si desea cancelar *después de un retraso*, este módulo por sí solo no lo hará. Necesitaría otro mecanismo (por ejemplo, un trabajo cron o otro módulo) para cambiar el estado a "Esperando pago por transferencia bancaria" *después* del retraso, lo que luego activaría este módulo para cambiarlo a "Cancelado". Este caso de uso específico es menos directo para el disparador inmediato de este módulo.
- **Escenario / ejemplo de comerciante:**
  - "Quiero que todos los pedidos que completen el pago con éxito pasen automáticamente a 'Preparación en curso' para que mi equipo de empaque sepa que debe comenzar a trabajar en ellos de inmediato."
  - "Cuando un cliente solicita un reembolso y cambio el estado del pedido a 'Reembolsado', quiero que se mueva automáticamente a 'Cerrado' para que ya no esté en mi lista de pedidos activos."

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | `Estado Desde` (ej., Pago aceptado) | Varía según el flujo de trabajo | El estado inicial que activa un cambio automático. |
| Configuración del módulo | `Estado A` (desplegable para cada `Estado Desde`) | `Procesando en curso` (para `Pago aceptado`) | El estado de destino al que un pedido se moverá automáticamente cuando entre en el `Estado Desde`. Automatiza el flujo de trabajo, ahorra tiempo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis estados de pedido no cambian automáticamente. ¿Qué debo verificar?**

- **R:** Primero, vaya a **Módulos > Gestor de módulos > Cambio automático de estado de pedido > Configurar** y asegúrese de haber configurado correctamente los estados "Desde" y "A".
- **R:** Verifique que el cambio de estado inicial (el estado "Desde") realmente esté ocurriendo. Por ejemplo, si espera que "Pago aceptado" active un cambio, asegúrese de que el pedido realmente alcance "Pago aceptado" primero.
- **R:** Borre la caché de su PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha. A veces, las configuraciones de los módulos necesitan una actualización de la caché para que surtan efecto.

**P2: ¿Puede este módulo cambiar estados basándose en un retraso de tiempo (por ejemplo, cancelar un pedido si no se paga en 24 horas)?**

- **R:** No, este módulo se activa *inmediatamente* cuando el estado de un pedido *cambia* a un estado "Desde" específico. No tiene funcionalidad incorporada para retrasos basados en el tiempo o trabajos cron. Para acciones basadas en el tiempo, necesitaría un módulo separado o un desarrollo personalizado que cambie el estado del pedido después de un retraso, lo que luego activaría este módulo.

**P3: ¿Este módulo interferirá con las actualizaciones de estado de mi pasarela de pago?**

- **R:** No, funciona *con* ellas. Las pasarelas de pago suelen actualizar un pedido a un estado como "Pago aceptado" o "Esperando pago". Este módulo toma el control *después* de esa actualización inicial, aplicando su siguiente regla. No impide que la pasarela de pago establezca su estado inicial.

**P4: Tengo un tema personalizado. ¿Funcionará este módulo?**

- **R:** Sí, absolutamente. Este módulo opera completamente en el back-office de PrestaShop y en la lógica de procesamiento de pedidos. No tiene componentes visuales de front-office ni estilos específicos del tema, por lo que es totalmente compatible con cualquier tema de PrestaShop.

**P5: ¿Cómo traduzco la configuración del módulo si mi back-office está en otro idioma?**

- **R:** PrestaShop maneja automáticamente la traducción de los estados de los pedidos. El módulo utiliza los nombres de sus estados de pedido existentes. Si necesita traducir los elementos de la propia interfaz del módulo (como el botón "Guardar" o los títulos de las secciones), puede hacerlo a través de **Internacional > Traducciones** en su back-office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema, su idioma y luego busque el módulo "schange".

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Cambio automático de estado de pedido".

### 4.1 Descripción general de la arquitectura

El módulo "Cambio automático de estado de pedido" (`schange`) es un módulo PrestaShop sencillo diseñado principalmente para conectarse al evento `actionOrderStatusPostUpdate`. Sigue una estructura de módulo PrestaShop estándar, aprovechando la clase `Module` para la instalación, desinstalación y configuración. Su lógica central reside dentro del archivo principal del módulo, procesando los cambios de estado basándose en las configuraciones almacenadas en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada o instancias de `ObjectModel` en un directorio `classes/`. Toda la lógica está encapsulada dentro de la clase principal `schange`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. El estilo de la página de configuración se maneja mediante el CSS predeterminado del back-office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty para su interfaz de configuración.

- **Plantillas de administración (`views/templates/admin/`)**:
  - `schange/views/tpl/selectedProducts.tpl`: Esta plantilla se utiliza dentro del método `getContent()` para renderizar el formulario de configuración del módulo. Típicamente muestra la lista de estados de pedido "Desde" y sus correspondientes menús desplegables de estado "A". Los desarrolladores pueden inspeccionar este archivo para comprender la estructura del formulario de configuración y cómo se presenta el mapeo de estados.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo **no** crea ninguna tabla SQL personalizada.
  - Todas las configuraciones (los mapeos de estado "Desde" a "A") se almacenan en la tabla `ps_configuration`. Cada mapeo probablemente se almacena como una clave de configuración separada, o un array serializado bajo una única clave, utilizando el nombre del módulo como prefijo (por ejemplo, `SCHANGE_STATUS_FROM_X_TO_Y` o `SCHANGE_STATUS_MAP`).
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Se activa inmediatamente después de que el estado de un pedido se haya actualizado correctamente. | Este es el hook principal utilizado por el módulo. Cuando el estado de un pedido cambia (por ejemplo, de "Esperando pago" a "Pago aceptado"), este hook se dispara. El módulo verifica si el nuevo estado (el estado "Desde") tiene un estado "A" configurado. Si existe un mapeo, el módulo actualiza programáticamente el pedido al estado "A" designado. |

### 4.8 Archivo principal del módulo (`schange/index.php`)

- **Nombre de la clase**: `schange`
- **Clase padre**: `Module`
- **Métodos clave**:
  - `__construct()`: Inicializa los metadatos del módulo (nombre, pestaña, versión, autor, etc.).
  - `install()`: Registra el hook `actionOrderStatusPostUpdate` y potencialmente establece valores de configuración predeterminados.
  - `uninstall()`: Desregistra el hook y limpia los valores de configuración de `ps_configuration`.
  - `getContent()`: Renderiza la página de configuración del módulo en el Back Office. Este método maneja el envío del formulario, guarda la configuración en `ps_configuration` y muestra la interfaz de mapeo de estados utilizando `selectedProducts.tpl`.
  - `hookActionOrderStatusPostUpdate($params)`: Este es el controlador de lógica central.
    - Recibe `$params` que contienen `newOrderStatus` e `id_order`.
    - Recupera los mapeos de estado configurados de `ps_configuration`.
    - Si `newOrderStatus` coincide con un estado "Desde" configurado, carga el objeto `Order` para `id_order`.
    - Luego intenta actualizar el estado del pedido al estado "A" correspondiente utilizando `Order->setCurrentState()`.
    - Asegura que el cambio de estado sea válido y maneja posibles errores.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cambio automático de estado de pedido", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
