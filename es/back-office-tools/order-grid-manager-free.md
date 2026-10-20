---
title: "Order Grid Manager Free - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Order Grid Manager Free de PrestaShop por MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order Grid Manager Free en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente incluidas en cualquier entorno de alojamiento web moderno.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo. Aquí encontrará una lista de todas las columnas que aparecen en la lista de pedidos de su Back Office de PrestaShop. Cada columna tiene un simple interruptor de ENCENDIDO/APAGADO.

**Nombre de la pantalla y ubicación del menú:**

- **Ruta del menú:** Back Office > Módulos > Gestor de módulos > Order Grid Manager Free > Configurar

**Configuraciones disponibles:**
Verá una lista de casillas de verificación o interruptores, cada uno correspondiente a una columna en su lista de Pedidos del Back Office. La lista exacta de columnas puede variar ligeramente dependiendo de su versión de PrestaShop y otros módulos instalados, pero los ejemplos comunes incluyen:

- **ID:** El identificador único para cada pedido.

  - **Qué hace esta configuración:** Controla si la columna "ID" es visible en su lista de pedidos.
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "ID" se mostrará.
    - *Cuando está deshabilitada:* La columna "ID" se ocultará.
  - **Valor recomendado:** SÍ (A menudo útil para referencia rápida y soporte).
  - **Escenario / ejemplo de comerciante:** Si con frecuencia hace referencia a los pedidos por su ID único al comunicarse con los clientes o su almacén, mantenga esta opción habilitada. Si utiliza principalmente otros identificadores como el nombre del cliente o la referencia, podría ocultarla.
- **Referencia:** El número de referencia interno del pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Referencia".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Referencia" se mostrará.
    - *Cuando está deshabilitada:* La columna "Referencia" se ocultará.
  - **Valor recomendado:** SÍ (Crucial para el seguimiento y la comunicación interna).
  - **Escenario / ejemplo de comerciante:** La mayoría de los comerciantes utilizan la referencia del pedido para albaranes, facturas y servicio al cliente. Mantenga esta opción visible a menos que tenga un flujo de trabajo muy específico que no la utilice.
- **Nuevo cliente:** Indica si el pedido es de un nuevo cliente.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Nuevo cliente".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Nuevo cliente" se mostrará.
    - *Cuando está deshabilitada:* La columna "Nuevo cliente" se ocultará.
  - **Valor recomendado:** NO (A menos que se dirija específicamente a los datos de nuevos clientes en su flujo de trabajo diario).
  - **Escenario / ejemplo de comerciante:** Si su equipo de marketing revisa con frecuencia los pedidos para identificar tendencias de adquisición de nuevos clientes, podría mantener esta opción visible. De lo contrario, a menudo es una buena candidata para ocultar para una vista más limpia.
- **Cliente:** El nombre del cliente que realizó el pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Cliente".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Cliente" se mostrará.
    - *Cuando está deshabilitada:* La columna "Cliente" se ocultará.
  - **Valor recomendado:** SÍ (Casi siempre esencial para la identificación del pedido).
  - **Escenario / ejemplo de comerciante:** Casi con certeza necesita ver quién realizó el pedido. Mantenga esta opción habilitada.
- **Total:** El importe total del pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Total".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Total" se mostrará.
    - *Cuando está deshabilitada:* La columna "Total" se ocultará.
  - **Valor recomendado:** SÍ (Importante para la visión financiera).
  - **Escenario / ejemplo de comerciante:** Esencial para ver rápidamente el valor de cada pedido. Mantenga esta opción habilitada.
- **Pago:** El método de pago utilizado para el pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Pago".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Pago" se mostrará.
    - *Cuando está deshabilitada:* La columna "Pago" se ocultará.
  - **Valor recomendado:** SÍ (Útil para la conciliación de pagos).
  - **Escenario / ejemplo de comerciante:** Si necesita ver rápidamente si un pedido se pagó con tarjeta de crédito, PayPal o transferencia bancaria, mantenga esta opción habilitada.
- **Estado:** El estado actual del pedido (por ejemplo, Pago aceptado, Enviado, Entregado).

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Estado".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Estado" se mostrará.
    - *Cuando está deshabilitada:* La columna "Estado" se ocultará.
  - **Valor recomendado:** SÍ (Crítico para el seguimiento del progreso del pedido).
  - **Escenario / ejemplo de comerciante:** Absolutamente esencial para gestionar el cumplimiento de pedidos. Mantenga esta opción habilitada.
- **Fecha:** La fecha y hora en que se realizó el pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Fecha".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Fecha" se mostrará.
    - *Cuando está deshabilitada:* La columna "Fecha" se ocultará.
  - **Valor recomendado:** SÍ (Importante para el orden cronológico y el envejecimiento).
  - **Escenario / ejemplo de comerciante:** Útil para ordenar los pedidos por la fecha en que se realizaron o identificar pedidos más antiguos que necesitan atención. Mantenga esta opción habilitada.
- **Factura:** Enlace para ver/descargar la factura.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Factura".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Factura" se mostrará.
    - *Cuando está deshabilitada:* La columna "Factura" se ocultará.
  - **Valor recomendado:** SÍ (Conveniente para un acceso rápido a las facturas).
  - **Escenario / ejemplo de comerciante:** Si su equipo necesita con frecuencia descargar o ver facturas directamente desde la lista de pedidos, mantenga esta opción habilitada.
- **Albarán:** Enlace para ver/descargar el albarán.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Albarán".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Albarán" se mostrará.
    - *Cuando está deshabilitada:* La columna "Albarán" se ocultará.
  - **Valor recomendado:** SÍ (Conveniente para un acceso rápido a los albaranes).
  - **Escenario / ejemplo de comerciante:** Si su almacén o equipo de envío utiliza albaranes, mantener esta opción visible proporciona un acceso rápido.
- **Acciones:** Botones para ver, editar o eliminar el pedido.

  - **Qué hace esta configuración:** Controla la visibilidad de la columna "Acciones".
  - **Efecto de cambiar esta configuración:**
    - *Cuando está habilitada:* La columna "Acciones" se mostrará.
    - *Cuando está deshabilitada:* La columna "Acciones" se ocultará.
  - **Valor recomendado:** SÍ (Esencial para gestionar pedidos individuales).
  - **Escenario / ejemplo de comerciante:** Casi siempre necesitará ver o editar un pedido. Mantenga esta opción habilitada.

**Guardar sus cambios:**
Después de haber realizado sus selecciones, recuerde hacer clic en el botón **"Guardar"** (normalmente en la parte inferior de la página de configuración) para aplicar sus cambios. Una vez guardado, navegue a **Pedidos > Pedidos** en su Back Office para ver el diseño de columna actualizado.

### 2.2 Tabla de referencia rápida de la configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ID | SÍ | Muestra/oculta el ID único del pedido. |
| Configuración del módulo | Referencia | SÍ | Muestra/oculta la referencia interna del pedido. |
| Configuración del módulo | Nuevo cliente | NO | Muestra/oculta el indicador para nuevos clientes. |
| Configuración del módulo | Cliente | SÍ | Muestra/oculta el nombre del cliente. |
| Configuración del módulo | Total | SÍ | Muestra/oculta el importe total del pedido. |
| Configuración del módulo | Pago | SÍ | Muestra/oculta el método de pago utilizado. |
| Configuración del módulo | Estado | SÍ | Muestra/oculta el estado actual del pedido. |
| Configuración del módulo | Fecha | SÍ | Muestra/oculta la fecha de realización del pedido. |
| Configuración del módulo | Factura | SÍ | Muestra/oculta el enlace de descarga de la factura. |
| Configuración del módulo | Albarán | SÍ | Muestra/oculta el enlace de descarga del albarán. |
| Configuración del módulo | Acciones | SÍ | Muestra/oculta los botones de acción (ver, editar, eliminar). |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero la cuadrícula de pedidos no ha cambiado.**
R: Después de guardar sus cambios en la configuración del módulo, es posible que deba borrar la caché de PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Además, intente actualizar la página de su navegador (Ctrl+F5 o Cmd+R) para asegurarse de que no está viendo una versión en caché del Back Office.

**P: ¿Puedo tener diferentes vistas de columna para diferentes usuarios administradores?**
R: El módulo "Order Grid Manager Free" aplica una configuración única y universal para todos los administradores. No admite preferencias de usuario individuales para la visibilidad de las columnas. Si necesita esta funcionalidad avanzada, es posible que deba buscar un módulo premium o un desarrollo personalizado.

**P: ¿Afectará este módulo al rendimiento de mi tienda?**
R: No, este módulo tiene un impacto insignificante en el rendimiento. Solo cambia qué columnas se muestran en la lista de pedidos del Back Office, lo cual es un ajuste de renderizado del lado del cliente (navegador) basado en una configuración simple. No altera las consultas de la base de datos ni los tiempos de carga del front-office.

**P: ¿Qué pasa si accidentalmente oculto una columna que necesito?**
R: ¡No hay problema! Simplemente regrese a **Módulos > Gestor de módulos > Order Grid Manager Free > Configurar**, vuelva a habilitar la columna deseada marcando su casilla y guarde sus cambios. Luego, borre su caché y actualice su navegador.

**P: ¿Este módulo admite traducciones multilingües para los nombres de las columnas?**
R: El módulo en sí no introduce nuevas cadenas traducibles para los nombres de las columnas. Simplemente controla la visibilidad de los nombres de columna existentes de PrestaShop, que ya son gestionados por el sistema de traducción central de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que buscan comprender, depurar o extender el módulo "Order Grid Manager Free".

### 4.1 Descripción general de la arquitectura

El módulo `Order Grid Manager Free` es un módulo de PrestaShop sencillo diseñado principalmente para modificar la visualización de la lista `AdminOrders`. Aprovecha el sistema de configuración de PrestaShop para almacenar las preferencias del usuario para la visibilidad de las columnas e inyecta JavaScript para ocultar/mostrar dinámicamente las columnas basándose en estas configuraciones. Sigue una estructura básica de módulo de PrestaShop, con su lógica central residiendo en el archivo principal del módulo.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de Front-Office o Back-Office. Toda la configuración y la lógica se manejan dentro de la clase principal del módulo y su método `getContent()`.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada o instancias de `ObjectModel`. Opera directamente sobre la configuración central de PrestaShop y las estructuras existentes del Back Office.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript dedicado en `views/js/`. La lógica para ocultar/mostrar columnas probablemente se inyecta directamente en el Back Office a través de un hook o dentro de la plantilla del método `getContent()`, utilizando JavaScript en línea o una simple inyección de CSS. Dada la simplicidad del módulo y su designación "Free", es muy probable que el ocultamiento de columnas se logre agregando reglas CSS `display: none;` o manipulando el DOM directamente después de que la página se carga, basándose en la configuración almacenada.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS dedicado en `views/css/`. Similar a JavaScript, cualquier estilo (principalmente `display: none;` para columnas) probablemente se inyecta en línea o se genera dinámicamente basándose en la configuración.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`myordergridfree/views/templates/admin/advert.tpl`**:
  - **Alcance:** Back-office (página de configuración del administrador).
  - **Propósito:** Esta plantilla probablemente se utiliza para mostrar un anuncio o mensaje promocional dentro de la página de configuración del módulo en el Back Office. Es una práctica común para los módulos gratuitos incluir tales elementos. No controla directamente la funcionalidad de la cuadrícula de pedidos, pero forma parte de la salida de `getContent()` del módulo.

El formulario de configuración real para la visibilidad de las columnas probablemente se renderiza directamente dentro del método `getContent()` del archivo principal del módulo, posiblemente utilizando `HelperForm` de PrestaShop o HTML personalizado, y luego se incluye `advert.tpl` para el contenido promocional.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla SQL personalizada.
  - Almacena su configuración en la tabla estándar `ps_configuration` de PrestaShop. Cada configuración (por ejemplo, `MYORDERGRIDFREE_HIDE_ID_COLUMN`) corresponderá a una fila en esta tabla, almacenando un valor booleano (0 o 1) para la visibilidad.
- **Tabla de Hooks registrados**:
  La funcionalidad principal de este módulo se basa en modificar la visualización del Back Office. Dada la simplicidad de la versión "Free", es probable que utilice uno o más de los siguientes enfoques:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de las páginas del Back Office. | Hook más probable para inyectar CSS o JavaScript en línea para ocultar columnas en la página `AdminOrders`. Esto permite que el módulo aplique `display: none;` a elementos `<th>` y `<td>` específicos basándose en la configuración guardada. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos multimedia. | Podría usarse para registrar un pequeño archivo JS o un script en línea que se ejecuta específicamente en el controlador `AdminOrders` para manipular el DOM. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Antes/Después de que se renderice la tabla de la lista de pedidos. | Menos probable para este módulo, ya que modifica la lista en sí, no solo agrega contenido a su alrededor. |

El método `install()` del módulo registraría estos hooks, y el método `hookDisplayBackOfficeHeader()` (o similar) contendría la lógica para recuperar la configuración almacenada y generar el CSS/JS necesario para ocultar las columnas seleccionadas cuando se carga la página `AdminOrders`.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Order Grid Manager Free", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.
"""
