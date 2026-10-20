---
title: "Pay By Phone Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Pay By Phone Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Pay By Phone Pro en MyPresta.eu](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas para PrestaShop en sí, y este módulo no tiene requisitos específicos adicionales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Pay By Phone Pro)

Esta es la pantalla de configuración principal donde define cómo aparece y se comporta el método de pago "Pay By Phone Pro" en su tienda.

- **Ubicación del Menú:** Back Office > Módulos > Gestor de módulos > Busque "Pay By Phone Pro" > Haga clic en "Configurar".

#### Ajustes y Opciones

1. **Título del Método de Pago**

   - **Qué hace este ajuste:** Este es el nombre del método de pago que sus clientes verán durante el proceso de compra. Es lo que aparece en la lista de opciones de pago.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en "Pagar por teléfono":* Los clientes verán "Pagar por teléfono" como una opción.
     - *Cuando se establece en "Llámenos para pagar":* Los clientes verán "Llámenos para pagar" como una opción.
   - **Valor recomendado:** Algo claro y profesional, como "Pagar por teléfono" o "Llamar para completar el pedido".
   - **Escenario / ejemplo del comerciante:** Si desea enfatizar el contacto directo, podría usar "Llame a nuestro equipo de ventas para pagar". Si desea que suene más como una opción de pago estándar, "Pagar por teléfono" es mejor.
2. **Descripción del Método de Pago**

   - **Qué hace este ajuste:** Esta es una breve descripción que aparece debajo del título del método de pago durante el proceso de compra. Explica al cliente en qué consiste este método de pago.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en "Llámenos para proporcionar los detalles de su tarjeta de crédito y finalizar su pedido.":* Este texto aparecerá, guiando al cliente sobre los siguientes pasos.
     - *Cuando se establece en "Contacte con nuestro servicio de atención al cliente para discutir las opciones de pago.":* Se mostrará este texto alternativo.
   - **Valor recomendado:** Indique claramente lo que el cliente debe hacer, por ejemplo, "Por favor, llámenos al [Su Número de Teléfono] para finalizar su pago y los detalles del pedido."
   - **Escenario / ejemplo del comerciante:** Podría escribir: "Después de realizar su pedido, por favor llámenos al +1-800-123-4567 durante el horario comercial para completar su pago. Tenga su número de pedido a mano."
3. **Instrucciones para el Cliente en la Página de Confirmación de Pedido**

   - **Qué hace este ajuste:** Este es un mensaje más detallado que se muestra al cliente en la página de confirmación del pedido *después* de que haya seleccionado "Pay By Phone Pro" y haya realizado su pedido. Aquí es donde proporciona instrucciones específicas.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en "Gracias por su pedido. Por favor, llámenos para finalizar su pago.":* Se mostrará este mensaje.
     - *Cuando se establece en "Su pedido está pendiente. Por favor, contacte con nuestro equipo de soporte con su número de pedido para organizar el pago.":* Se mostrará este mensaje alternativo.
   - **Valor recomendado:** Incluya su número de teléfono, horario comercial y qué información debe tener el cliente lista (por ejemplo, número de pedido).
   - **Escenario / ejemplo del comerciante:** "Su pedido #12345 ha sido realizado. Por favor, llame a nuestro equipo de ventas al +1-800-123-4567 (Lun-Vie, 9 AM - 5 PM EST) dentro de las 24 horas para proporcionar los detalles de pago. Tenga su número de pedido a mano."
4. **Estado del Pedido para Pagos Pendientes**

   - **Qué hace este ajuste:** Esto determina el estado inicial de un pedido realizado utilizando "Pay By Phone Pro" en su Back Office de PrestaShop. Este estado indica que el pago aún no está completo y requiere su acción.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en "Esperando transferencia bancaria":* Los pedidos aparecerán con este estado.
     - *Cuando se establece en "Pago aceptado":* (No recomendado para este módulo) Esto marcaría incorrectamente el pedido como pagado antes de que usted lo haya procesado.
   - **Valor recomendado:** Elija un estado que indique claramente "pago pendiente" o "esperando pago". Las opciones comunes son "Esperando transferencia bancaria", "Pago pendiente" o "Esperando pago por cheque". Si tiene un estado de pedido personalizado como "Esperando Pago por Teléfono", sería ideal.
   - **Escenario / ejemplo del comerciante:** Seleccionar "Esperando transferencia bancaria" asegura que estos pedidos sean fácilmente identificables en su lista de pedidos como que necesitan procesamiento de pago manual.
5. **Habilitar para Países Específicos**

   - **Qué hace este ajuste:** Le permite restringir este método de pago a clientes de ciertos países solamente. Si se deja vacío, estará disponible para todos los países.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se seleccionan países específicos (por ejemplo, "Estados Unidos", "Canadá"):* Solo los clientes con una dirección de facturación en estos países verán "Pay By Phone Pro" como una opción.
     - *Cuando no se seleccionan países:* El método de pago está disponible globalmente.
   - **Valor recomendado:** Deje vacío si desea ofrecerlo en todo el mundo, o seleccione países específicos si tiene limitaciones operativas (por ejemplo, solo tiene soporte telefónico en ciertas regiones).
   - **Escenario / ejemplo del comerciante:** Si su soporte telefónico solo está disponible en inglés y solo realiza envíos a EE. UU. y Canadá, seleccionaría "Estados Unidos" y "Canadá" para evitar ofrecerlo a clientes a los que no puede atender.
6. **Habilitar para Monedas Específicas**

   - **Qué hace este ajuste:** Le permite restringir este método de pago a clientes que pagan en monedas específicas. Si se deja vacío, estará disponible para todas las monedas.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se seleccionan monedas específicas (por ejemplo, "USD", "EUR"):* Solo los clientes que pagan en estas monedas verán "Pay By Phone Pro".
     - *Cuando no se seleccionan monedas:* El método de pago está disponible para todas las monedas configuradas en su tienda.
   - **Valor recomendado:** Deje vacío si admite todas las monedas, o seleccione las específicas si su sistema de procesamiento de pagos manual tiene limitaciones de moneda.
   - **Escenario / ejemplo del comerciante:** Si su terminal de tarjeta de crédito solo procesa USD y EUR, seleccionaría estas dos monedas.
7. **Habilitar para Grupos de Clientes Específicos**

   - **Qué hace este ajuste:** Le permite restringir este método de pago a ciertos grupos de clientes (por ejemplo, "Invitados", "Clientes", "Mayoristas"). Si se deja vacío, estará disponible para todos los grupos de clientes.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se seleccionan grupos específicos (por ejemplo, "Mayoristas"):* Solo los clientes que pertenecen al grupo "Mayoristas" verán esta opción de pago.
     - *Cuando no se seleccionan grupos:* El método de pago está disponible para todos los grupos de clientes.
   - **Valor recomendado:** Deje vacío para uso general, o seleccione grupos específicos si este método de pago forma parte de un acuerdo especial (por ejemplo, para VIPs o clientes B2B).
   - **Escenario / ejemplo del comerciante:** Podría ofrecer esto solo a su grupo de clientes "Mayoristas", ya que a menudo tienen términos de pago personalizados que requieren discusión directa.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Título del Método de Pago | "Pagar por teléfono" | Nombre mostrado a los clientes durante el proceso de compra. |
| Configuración del Módulo | Descripción del Método de Pago | "Llámenos para proporcionar los detalles de su tarjeta de crédito y finalizar su pedido." | Breve explicación debajo del título del pago. |
| Configuración del Módulo | Instrucciones para el Cliente en la Página de Confirmación de Pedido | "Gracias por su pedido. Por favor, llámenos para finalizar su pago." | Instrucciones detalladas en la página de confirmación del pedido. |
| Configuración del Módulo | Estado del Pedido para Pagos Pendientes | "Esperando transferencia bancaria" (o estado pendiente similar) | Estado inicial de los pedidos realizados con este método. |
| Configuración del Módulo | Habilitar para Países Específicos | Vacío (Todos los Países) | Restringir el método de pago por país del cliente. |
| Configuración del Módulo | Habilitar para Monedas Específicas | Vacío (Todas las Monedas) | Restringir el método de pago por moneda seleccionada. |
| Configuración del Módulo | Habilitar para Grupos de Clientes Específicos | Vacío (Todos los Grupos) | Restringir el método de pago por grupo de clientes. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: La opción "Pay By Phone Pro" no aparece durante el proceso de compra.**
R:

- **Verificar el Estado del Módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Pay By Phone Pro" esté instalado y habilitado.
- **Configuración:** Revise los ajustes "Habilitar para Países Específicos", "Habilitar para Monedas Específicas" y "Habilitar para Grupos de Clientes Específicos". Si ha restringido el módulo, asegúrese de que el cliente/carrito de prueba actual cumpla con esos criterios.
- **Caché:** Borre la caché de su PrestaShop en **Parámetros avanzados > Rendimiento**. A veces, la caché antigua impide que aparezcan nuevos módulos o configuraciones.
- **Compatibilidad del Tema:** Aunque es raro, un tema altamente personalizado podría interferir. Cambie temporalmente a un tema predeterminado de PrestaShop (por ejemplo, Classic) para descartar conflictos de tema.

**P2: ¿Cómo cambio el texto que ven los clientes para este método de pago?**
R: Todo el texto visible para el cliente (título, descripción e instrucciones de confirmación) se puede personalizar directamente desde la página de configuración del módulo en su Back Office. Navegue a **Módulos > Gestor de módulos**, busque "Pay By Phone Pro" y haga clic en "Configurar". Encontrará campos como "Título del Método de Pago", "Descripción del Método de Pago" e "Instrucciones para el Cliente en la Página de Confirmación de Pedido". Recuerde guardar sus cambios.

**P3: ¿Qué sucede si un cliente realiza un pedido usando "Pay By Phone Pro" pero nunca llama?**
R: El pedido permanecerá en el estado de "pago pendiente" que configuró (por ejemplo, "Esperando transferencia bancaria"). Deberá monitorear estos pedidos en su Back Office. Puede configurar recordatorios automáticos o contactar manualmente al cliente después de un cierto período (por ejemplo, 24-48 horas) para hacer un seguimiento. Si no se establece contacto, es posible que eventualmente deba cancelar el pedido.

**P4: ¿Puedo traducir el texto del módulo a otros idiomas?**
R: Sí, el sistema de traducción de PrestaShop maneja los textos de los módulos. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Pay By Phone Pro". Luego podrá traducir todos los campos de texto configurables a los idiomas activos de su tienda.

**P5: ¿Cómo proceso el pago una vez que un cliente llama?**
R: Este módulo no procesa pagos por sí mismo. Facilita la realización del pedido. Una vez que un cliente llama, usted utilizará sus métodos de procesamiento de pagos fuera de línea existentes (por ejemplo, un terminal de tarjeta de crédito físico, un terminal virtual proporcionado por su banco o el registro de una transferencia bancaria) para tomar sus detalles de pago y completar la transacción. Después de un pago exitoso, debe actualizar manualmente el estado del pedido en su Back Office de PrestaShop de "pago pendiente" a "Pago aceptado" (o "Procesando") para reflejar el cambio.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada del módulo "Pay By Phone Pro" para desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo "Pay By Phone Pro" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente `PaymentModule` para su funcionalidad principal. Se integra en el flujo de pago registrando hooks y proporcionando controladores frontales para la ejecución y validación del pago. La configuración se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores manejan los aspectos del proceso de pago orientados al cliente.

- **`controllers/front/index.php`**

  - **Nombre de la clase y clase padre:** `PayByPhoneIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es típicamente responsable de mostrar el formulario de pago inicial o redirigir a la página de ejecución del pago. En el contexto de este módulo, probablemente actúa como una pasarela antes de la ejecución real del pago, potencialmente configurando datos de sesión o redirigiendo a `payment_execution.tpl`.
- **`controllers/front/validation.php`**

  - **Nombre de la clase y clase padre:** `PayByPhoneValidationModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este es el controlador crítico que procesa el pedido después de que el cliente selecciona "Pay By Phone Pro". Valida el pedido, lo crea en la base de datos de PrestaShop con el estado pendiente configurado y luego redirige al cliente a la página de confirmación del pedido, mostrando las instrucciones específicas. Utiliza el método `validateOrder` de la clase padre `PaymentModule`.

#### Controladores de Administración del Back-Office

Este módulo no incluye ningún controlador de administración de Back-Office personalizado. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no contiene ninguna clase personalizada o definiciones de `ObjectModel` en el directorio `classes/`. Se basa en las clases `PaymentModule` y `Configuration` del núcleo de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. Su funcionalidad es principalmente del lado del servidor y basada en plantillas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Alcance:** Estilo del front-office para el cliente.
  - **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilo probablemente se utiliza para proporcionar un estilo básico para la apariencia del método de pago durante el proceso de compra, como el bloque de opciones de pago, el texto de descripción o cualquier elemento específico dentro de las plantillas `payment.tpl` o `shopping-cart.tpl`.
  - **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir:** Los desarrolladores pueden inspeccionar el HTML generado para el método de pago en la página de pago para identificar clases específicas (por ejemplo, `.paybyphone-payment-option`, `.paybyphone-description`) para sobrescribir en el `custom.css` de su tema o a través de las opciones de personalización del tema.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

Estas plantillas se renderizan cuando se ejecutan hooks específicos de PrestaShop.

- **`views/templates/hook/infos.tpl`**

  - **Hook:** Probablemente `displayPaymentTop` o similar, proporcionando información adicional sobre el método de pago.
  - **Bloque visual:** Podría usarse para mostrar un bloque de información general sobre la opción "Pagar por teléfono", quizás en la página del producto o en una columna, antes de que el cliente llegue al proceso de compra.
- **`views/templates/hook/payment.tpl`**

  - **Hook:** `displayPayment` (PrestaShop 1.6) o `paymentOptions` (PrestaShop 1.7+).
  - **Bloque visual:** Esta es la plantilla principal para mostrar la opción "Pay By Phone Pro" en la página de selección de pago durante el proceso de compra. Contendrá el título y la descripción del método de pago tal como se configuraron en el Back Office.

#### Plantillas de Administración (`views/templates/admin/`)

Este módulo no contiene ninguna plantilla de administración personalizada. El formulario de configuración probablemente se genera directamente dentro del método `getContent()` de `index.php` utilizando `HelperForm` de PrestaShop.

#### Plantillas del Front-office (`views/templates/front/`)

Estas plantillas son renderizadas por los controladores frontales del módulo.

- **`views/templates/front/payment_execution.tpl`**

  - **Propósito:** Esta plantilla probablemente es renderizada por `PayByPhoneIndexModuleFrontController` o directamente después de que el cliente selecciona el método de pago. Podría servir como una página intermedia o un paso de confirmación antes de la validación final, mostrando potencialmente un botón de "Confirmar Pedido".
- **`views/templates/front/shopping-cart.tpl`**

  - **Propósito:** Esta plantilla es probablemente un respaldo o una visualización alternativa para la opción de pago dentro del resumen del carrito de compras, posiblemente para versiones anteriores de PrestaShop o integraciones de temas específicos. Presentaría la opción "Pagar por teléfono" antes de que comience el proceso de pago completo.
- **`views/templates/front/validation.tpl`**

  - **Propósito:** Esta es la plantilla de la página de confirmación del pedido, renderizada después de que `PayByPhoneValidationModuleFrontController` valida y crea el pedido con éxito. Muestra el texto "Instrucciones para el Cliente en la Página de Confirmación de Pedido", junto con un resumen del pedido.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo "Pay By Phone Pro" no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones en la tabla `ps_configuration` de PrestaShop utilizando claves como `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES` y `PAYBYPHONE_GROUPS`.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | En la página de selección de pago durante el proceso de compra. | Muestra la opción de pago "Pay By Phone Pro". |
| `paymentOptions` (PrestaShop 1.7+) | En la página de selección de pago durante el proceso de compra. | Muestra la opción de pago "Pay By Phone Pro" (hook moderno). |
| `displayPaymentReturn` | En la página de confirmación del pedido después del pago. | Muestra las instrucciones específicas para que el cliente llame. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para cargar archivos CSS (`paybyphone.css`). |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | En las respectivas áreas de columna/pie de página. | Podría usarse para mostrar bloques de información sobre el método de pago (a través de `infos.tpl`). |
| `actionValidateOrder` | Después de que un pedido ha sido validado y creado con éxito. | Permite que el módulo realice acciones adicionales o registre información después de la creación del pedido (por ejemplo, establecer detalles específicos del pedido). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Pay By Phone Pro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la compatibilidad continua de nuestros módulos con las últimas versiones de PrestaShop.
