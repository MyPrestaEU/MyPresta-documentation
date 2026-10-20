---
title: "Soporte para envío a pagar + productos virtuales - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Soporte para envío a pagar + productos virtuales' de MyPresta.eu."
sidebar:
  label: "Soporte para envío a pagar + productos virtuales - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Ship to pay + virtual products support en MyPresta.eu](https://mypresta.eu/modules/payment-process/ship-to-pay-virtual-products-support.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/ship-to-pay-virtual-products-support/)
>
> ---


# Soporte para envío a pagar + productos virtuales

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y normalmente están presentes en cualquier entorno de alojamiento compatible.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Soporte para envío a pagar + productos virtuales". Se le presentará una única y completa pantalla de configuración.

Esta pantalla muestra una matriz (una cuadrícula) donde puede vincular sus transportistas de envío disponibles con sus módulos de pago instalados.

**Entendiendo la cuadrícula de configuración:**

- **Filas (Transportistas):** Cada fila representa un transportista de envío que ha configurado en su tienda PrestaShop (por ejemplo, "Mi transportista", "Transportista predeterminado de PrestaShop", "DHL", "UPS", etc.).
- **Columnas (Módulos de pago):** Cada columna representa un módulo de pago que ha instalado y habilitado en su tienda PrestaShop (por ejemplo, "Transferencia bancaria", "Pago contra reembolso", "PayPal", "Stripe", etc.).
- **Casillas de verificación:** En la intersección de cada fila de transportista y columna de módulo de pago, hay una casilla de verificación.

**Cómo configurar:**

1. **Identifique sus transportistas:** Mire la columna de la izquierda para ver todos sus transportistas de envío activos.
2. **Identifique sus métodos de pago:** Mire la fila superior para ver todos sus módulos de pago activos.
3. **Vincúlelos:** Para cada transportista, recorra su fila y **marque la casilla** de cada método de pago que desee permitir para ese transportista específico.
   - *Qué hace este ajuste:* Esta casilla de verificación determina si se ofrecerá un método de pago particular al cliente cuando seleccione el transportista de envío correspondiente durante el proceso de compra.
   - *Efecto de cambiar este ajuste:*
     - **Cuando está marcada:** El método de pago será visible y seleccionable por el cliente si elige este transportista.
     - **Cuando no está marcada:** El método de pago estará oculto e no disponible para el cliente si elige este transportista.
   - *Valor recomendado:* Marque solo las combinaciones que tengan sentido para su lógica de negocio.
   - *Escenario/ejemplo de comerciante:* Si "DHL Express" es un servicio rápido y premium, podría marcar solo "PayPal" y "Tarjeta de crédito (Stripe)" para él, y desmarcar "Transferencia bancaria" para asegurar un pago rápido para una entrega rápida.

**Fila especial: "Productos virtuales"**

Este módulo incluye una característica única para productos virtuales. Verá una fila dedicada etiquetada como **"Productos virtuales"** (o similar, dependiendo de su versión e idioma de PrestaShop).

- **Qué hace este ajuste:** Esta fila le permite especificar qué métodos de pago están disponibles cuando el carrito de un cliente contiene *solo* productos virtuales. Dado que los productos virtuales no tienen un método de envío tradicional, esta fila actúa como su "transportista" para la asociación de métodos de pago.
- *Efecto de cambiar este ajuste:*
  - **Cuando está marcada (para un método de pago en la fila "Productos virtuales"):** Ese método de pago estará disponible si el carrito del cliente consiste únicamente en productos virtuales.
  - **Cuando no está marcada:** Ese método de pago no estará disponible para carritos que contengan solo productos virtuales.
- *Valor recomendado:* Marque los métodos de pago que sean adecuados para la entrega digital inmediata, típicamente pasarelas de pago en línea como PayPal, Stripe o módulos de tarjeta de crédito.
- *Escenario/ejemplo de comerciante:* Si vende libros electrónicos, probablemente marcaría "PayPal" y "Tarjeta de crédito (Stripe)" en la fila "Productos virtuales", pero desmarcaría "Pago contra reembolso" o "Transferencia bancaria", ya que no son adecuados para la entrega digital instantánea.

**Guardar su configuración:**

- Después de realizar todas sus selecciones, recuerde hacer clic en el botón **"Guardar"** (normalmente en la parte inferior de la página) para aplicar sus cambios.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Casilla de verificación para Transportista X / Pago Y | Desmarcada por defecto | **Propósito:** Vincula un método de pago específico a un transportista de envío específico. **Impacto:** Si está marcada, el método de pago está disponible cuando se elige el Transportista X. Si no está marcada, está oculto. |
| Página de configuración del módulo | Casilla de verificación para "Productos virtuales" / Pago Y | Desmarcada por defecto | **Propósito:** Vincula un método de pago específico a carritos que contienen solo productos virtuales. **Impacto:** Si está marcada, el método de pago está disponible para carritos solo de productos virtuales. Si no está marcada, está oculto. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He configurado el módulo, pero los métodos de pago no cambian en el proceso de compra. ¿Qué está mal?**
R1:

- **Borrar caché:** El problema más común. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
- **Módulo habilitado:** Asegúrese de que el módulo "Soporte para envío a pagar + productos virtuales" esté realmente habilitado en **Módulos > Gestor de módulos**.
- **Módulos de pago habilitados:** Asegúrese de que los módulos de pago que intenta vincular también estén habilitados y configurados correctamente en su tienda.
- **Compatibilidad del tema:** Aunque es raro, algunos temas muy personalizados podrían interferir. Si borrar la caché no funciona, intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si el problema persiste. Si se resuelve, su tema podría necesitar un ajuste.

**P2: ¿Por qué algunos métodos de pago siguen apareciendo incluso si los desmarqué para un transportista?**
R2:

- **Múltiples transportistas en el carrito:** Si un cliente tiene productos en su carrito que usarían diferentes transportistas (por ejemplo, un producto enviado por el Transportista A, otro por el Transportista B), la lógica de pago de PrestaShop podría volverse compleja. Este módulo funciona principalmente cuando se selecciona un único método de envío para todo el carrito.
- **Productos virtuales en el carrito:** Si el carrito contiene una mezcla de productos físicos y virtuales, la lógica del módulo para productos virtuales podría interactuar con la lógica específica del transportista. Asegúrese de que su fila "Productos virtuales" esté configurada según lo previsto.
- **Otros módulos:** Otro módulo podría estar anulando las opciones de pago. Deshabilite temporalmente otros módulos relacionados con el pago para verificar si hay conflictos.

**P3: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R3:

- Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
- Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el idioma que desea traducir.
- Busque el módulo "Soporte para envío a pagar + productos virtuales" en la lista y haga clic en "Modificar". Luego podrá editar cualquier cadena traducible.

**P4: He añadido un nuevo transportista o módulo de pago, pero no aparece en la cuadrícula de configuración.**
R4:

- **Actualizar configuración del módulo:** A veces, PrestaShop necesita una actualización para detectar nuevas entidades. Vaya a **Módulos > Gestor de módulos**, busque "Soporte para envío a pagar + productos virtuales" y haga clic en "Configurar" de nuevo. Esto debería recargar la página de configuración y mostrar el nuevo transportista/módulo de pago.
- **Asegúrese de que esté habilitado:** Asegúrese de que el nuevo transportista o módulo de pago esté completamente habilitado y configurado en su sección respectiva del Back Office de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Soporte para envío a pagar + productos virtuales" opera anulando una clase central de PrestaShop responsable de encontrar las opciones de pago disponibles durante el proceso de compra. Esto le permite inyectar su lógica personalizada basada en los transportistas seleccionados y la presencia de productos virtuales en el carrito, filtrando los métodos de pago presentados al cliente. Aprovecha el sistema de anulación de PrestaShop y el almacenamiento de configuración estándar.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Su lógica se maneja principalmente a través del archivo principal del módulo y una anulación.

### 4.3 Clases y modelos principales (`classes/`)

- **`shiptopay/override/classes/checkout/PaymentOptionsFinder.php`**
  - **Propósito:** Este es el núcleo de la funcionalidad del módulo. Anula la clase `PaymentOptionsFinder` predeterminada de PrestaShop, que es responsable de determinar qué opciones de pago están disponibles para el cliente durante el proceso de compra.
  - **Clase padre:** `PaymentOptionsFinderCore`
  - **Métodos y lógica clave:**
    - El método `find()` anulado (o similar, según la versión de PrestaShop) es interceptado.
    - Dentro de este método, el módulo recupera el ID del transportista actualmente seleccionado (del carrito o la sesión) y verifica si el carrito contiene solo productos virtuales.
    - Luego consulta la configuración del módulo (almacenada en `ps_configuration`) para determinar qué módulos de pago están permitidos para el transportista seleccionado o para productos virtuales.
    - La lista original de opciones de pago devuelta por `PaymentOptionsFinderCore` se filtra, eliminando cualquier método de pago que no esté permitido según la configuración del módulo.
    - Esto asegura que solo se muestren al cliente los métodos de pago permitidos.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La actualización dinámica de las opciones de pago es manejada por el JavaScript de pago central de PrestaShop, que reacciona a los cambios en la selección del método de envío y vuelve a renderizar la sección de pago basándose en las opciones filtradas proporcionadas por el `PaymentOptionsFinder` anulado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Se integra perfectamente con el estilo de tema existente de PrestaShop para las opciones de pago.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`shiptopay/views/shiptopay.tpl`**
  - **Propósito:** Esta plantilla se utiliza probablemente para renderizar el formulario de configuración del módulo en el Back Office de PrestaShop. Construye la matriz HTML (cuadrícula) de transportistas y métodos de pago con casillas de verificación, permitiendo al comerciante vincularlos.
  - **Alcance:** Plantilla de administración.
  - **Variables:** Normalmente iteraría sobre los arrays `$carriers` y `$payment_modules`, utilizando `Configuration::get()` para recuperar la configuración guardada para cada casilla de verificación.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos:**

  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración (los enlaces entre transportistas/productos virtuales y métodos de pago) se almacena en la tabla `ps_configuration`. Cada configuración se almacenaría típicamente como un par clave-valor, donde la clave podría ser `SHIP_TO_PAY_CARRIER_X_PAYMENT_Y` y el valor `1` (habilitado) o `0` (deshabilitado). La configuración de "Productos virtuales" seguiría una convención de nombres similar.
- **Tabla de hooks registrados:**

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página. | Aunque se enumera como un hook potencial de front office, este módulo utiliza principalmente una anulación y no suele renderizar contenido visible a través de `displayHeader`. Podría usarse para la inicialización interna del módulo o la carga de activos si hubiera alguno presente. |
  | `displayRightColumn` | En la columna derecha de las páginas (si está habilitado por el tema). | No se utiliza directamente para la funcionalidad principal del módulo, ya que su impacto es en las opciones de pago del proceso de compra. |
  | `displayLeftColumn` | En la columna izquierda de las páginas (si está habilitado por el tema). | No se utiliza directamente para la funcionalidad principal del módulo, ya que su impacto es en las opciones de pago del proceso de compra. |
  | `displayFooter` | En la sección del pie de página de cada página. | No se utiliza directamente para la funcionalidad principal del módulo, ya que su impacto es en las opciones de pago del proceso de compra. |
  | `displayModuleConfigureExtraButtons` | En el gestor de módulos, junto al botón de configuración. | No se utiliza explícitamente para la funcionalidad principal, pero podría usarse para acciones administrativas adicionales. |
  | `actionPaymentOptionsModifier` | (Implícito/Interno) | Este módulo funciona principalmente anulando `PaymentOptionsFinder`, que se llama internamente durante el proceso de compra para generar la lista de opciones de pago. Aunque no es un hook `hookDisplay` o `action` tradicional, la anulación actúa como un punto de intercepción. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Soporte para envío a pagar + productos virtuales", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
