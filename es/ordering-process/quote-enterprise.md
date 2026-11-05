---
title: "Quote Enterprise - manual del comerciante"
sidebar:
  label: "Quote Enterprise - manual del comerciante"
description: "Cómo configurar Quote Enterprise, ejecutar el proceso completo de presupuesto a pedido y resolver problemas habituales."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Quote Enterprise en MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/quote-enterprise/)
>
> ---


## 1. Requirements

El módulo funciona en PrestaShop 1.7, 8 y 9, y en PHP 7.1 a 8.5.

El servidor necesita cURL y JSON. No necesita otro módulo.

Usted crea las claves de Google reCAPTCHA solo si activa reCAPTCHA. Los webhooks de Slack o Teams son opcionales y solo para digests del personal. Los correos de recordatorio y los digests requieren un trabajo cron del servidor en la URL de cron del módulo.

## 2. Installation

1. Suba el módulo en **Modules**, **Module Manager**, y actívelo.
2. Tras la instalación, **Orders** tiene dos entradas: **Quotes** y **Audit log**.
3. El módulo no limpia la caché durante la instalación.
4. La instalación crea las tablas de presupuestos y un producto virtual oculto para líneas de servicio personalizadas. También escribe los ajustes predeterminados descritos más abajo.

La desinstalación elimina las entradas de menú, las tablas del módulo y las claves de configuración. El producto de tarifa oculto del catálogo no se elimina al desinstalar.

## 3. Configuration and back-office work

Abra **Modules**, **Module Manager**, **Quote Enterprise**, **Configure**. El módulo se abre en **Dashboard**. La barra superior tiene: **Dashboard**, **Quotes**, **Audit log**, **Settings**, **PDF**, **Emails**, **API**, **Notifications**, **Updates**.

Las capturas de este manual proceden de un back office en inglés.

El trabajo diario con presupuestos también está en **Orders**, **Quotes** (lista completa y editor) y **Orders**, **Audit log**.

### 3.1 Full quote process

Use este flujo como mapa. Las secciones siguientes explican cada pantalla.

1. Un cliente solicita un presupuesto desde una página de producto, una lista de productos, el carrito o una lista de presupuesto multiproducto. Los invitados pueden ver botones si está permitido, pero guardar la solicitud siempre requiere una cuenta de cliente.
2. La solicitud se convierte en un presupuesto en **Pending review** (solicitud del cliente) o el personal crea un **Draft** desde el back office.
3. El personal abre el presupuesto en **Orders**, **Quotes**, define precios, descuentos, envío y mensajes, y luego **Save** o **Save & send**.
4. **Save & send** envía un correo al cliente y pasa el presupuesto a **Sent** (o mantiene el flujo de negociación al reenviar).
5. El cliente abre **My quotes**, ve la oferta, puede descargar el PDF, aceptar, rechazar o pedir cambios (**Negotiation**).
6. Tras **Accepted**, el cliente puede pasar por la caja. El checkout construye un carrito a partir del presupuesto y puede convertirse en un pedido (**Converted**). El presupuesto queda entonces bloqueado.
7. Pasada la fecha **valid until**, los presupuestos enviados o en negociación pasan a **Expired** al abrirlos o cuando se ejecuta el cron. Los correos de recordatorio requieren cron.

Estados que verá: **Draft**, **Pending review**, **Sent**, **Negotiation**, **Accepted**, **Converted**, **Expired**, **Rejected**, **Cancelled**.

Solo **Sent** y **Negotiation** pueden ser aceptados por el cliente. Cambie el estado manualmente en el editor cuando sea necesario.

### 3.2 Dashboard

El panel muestra el pipeline de presupuestos. Abra **Analytics parameters** para definir el periodo de KPI y los rangos de gráficos, luego pulse **Save analytics parameters**. Confirmación: **Tracking parameters updated.**

![Dashboard](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Dashboard tables](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Field | At the start | What it does |
|---|---|---|
| **KPI period** | **Last 90 days** | Ventana temporal para las tarjetas KPI, la tabla de embudo, los principales clientes y el personal. Elija 30, 90, 180 o 365 días y guarde. Cuenta presupuestos creados, enviados, aceptados, convertidos y rechazados en ese periodo. |
| **Weekly chart range** | 12 | Número de semanas en el gráfico de embudo semanal (4–52). La pestaña Weekly muestra creados, enviados, aceptados y convertidos por semana ISO. |
| **Monthly chart range** | 12 | Número de meses en el gráfico de embudo mensual (3–24). |
| **Yearly chart range** | 5 | Número de años en el gráfico de embudo anual (2–10). |
| **Default chart tab** | **Monthly** | Qué pestaña de gráfico se abre primero: Weekly, Monthly o Yearly. Puede cambiar de pestaña sin guardar. |
| **Expiring soon window** | 7 | Cuántos días por delante marcar presupuestos como próximos a caducar. Suele ser 7 o 14. Solo se listan presupuestos enviados y en negociación con fecha valid_until en esa ventana. |

Tarjetas KPI: valor del pipeline abierto, pendientes de revisión, próximos a caducar, valor convertido, tasa de conversión, tasa de éxito. Debajo: creados, enviados, aceptados, convertidos, rechazados, media de días hasta convertir, valor medio del presupuesto. Los gráficos muestran el embudo en el tiempo. Tablas: embudo del periodo, envejecimiento del pipeline abierto, próximos a caducar, actividad reciente, principales clientes y personal. Pipeline abierto significa presupuestos enviados, en negociación o aceptados.

### 3.3 Quotes tab in module configuration

Esta pestaña es un resumen breve. Los filtros completos, las acciones masivas y el editor están en **Orders**, **Quotes**.

![Quotes overview](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Finalidad de esta pantalla: una lista rápida de presupuestos recientes desde la configuración del módulo. Pulse **View** para abrir el editor completo. Use **Manage all quotes** para filtros, exportación y operaciones masivas. Efecto: mantiene ligera la configuración del módulo mientras el trabajo completo con presupuestos ocurre en la pantalla dedicada del back office.

**Create quote:** seleccione un cliente (búsqueda), opcionalmente escriba un **Internal note**, pulse **Create draft quote**. Se le redirige al editor completo. Sin cliente: **Please select a customer.**

**Quote templates** (cuando existen plantillas): elija una plantilla y un cliente, luego **Create from template**.

Columnas de **Recent quotes**: Reference, Customer, Status, Total. Vacío: **No quotes yet.** Enlaces: **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Quotes list (Orders menu)

Abra **Orders**, **Quotes**. Esta es la pantalla principal de gestión.

Columnas: **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Acciones de fila: editar y duplicar. No puede añadir un presupuesto en blanco desde la barra de la lista; créelo desde el resumen del módulo, desde una plantilla o duplicando. Error si lo intenta: **Create quotes from module configuration or duplicate an existing quote.**

Acciones masivas:

| Action | What it does |
|---|---|
| **Assign to employee** | Asigna el empleado a los presupuestos seleccionados. |
| **Extend validity** | Adelanta la validez (valid until) de la selección. |
| **Send expiry reminder** | Envía correos de recordatorio a los clientes seleccionados (diálogo de confirmación). |
| **Export CSV** | Descarga CSV de la selección. |
| **Export XML** | Descarga XML de la selección. |

Filtre por estado y busque como en una lista estándar de PrestaShop. Abra una fila para editar.

### 3.5 Quote editor — how to manage a request

Abra un presupuesto desde la lista. La leyenda muestra la referencia y el estado, por ejemplo `Q-2026-00001 — Pending review`.

**Ruta típica del personal para una solicitud nueva del cliente**

1. Filtre o abra presupuestos en **Pending review**.
2. Revise **Messages from customer** (texto de la solicitud, luego motivos de cambio o rechazo). Solo lectura.
3. Añada o ajuste **Line items** (productos del catálogo y servicios personalizados).
4. Defina **Global discount %** / **Global discount amount**, **Shipping label** e importes de envío.
5. Escriba **General message to customer** y, opcionalmente, **Internal note**.
6. Defina **Validity period** y **Validity unit**, compruebe el valid until actual.
7. Defina **Status** si hace falta, luego **Save** (**Quote saved.**) o **Save & send** (**Quote sent to customer by e-mail.**).

**Bloqueo.** Los presupuestos aceptados o convertidos se bloquean. Los caducados muestran: **This quote has expired. Click Unlock to extend validity and send an updated offer.** Convertidos: **This quote is locked because it was converted to an order.** Aceptados: **This quote is locked because the customer accepted it. Click Unlock to make changes.** Desbloqueo: **Quote unlocked for editing.** Volver a bloquear: **Quote locked again.**

| Field | What it does (from field descriptions) |
|---|---|
| **Status** | Etapa actual en el flujo de ventas. Draft: solo interno. Pending review: el cliente solicitó, a la espera de su precio. Sent: enviado por correo al cliente. Accepted: el cliente aceptó. Converted: se convirtió en pedido. Solo Sent y Negotiation pueden ser aceptados por el cliente. Cambie el estado manualmente cuando sea necesario. |
| **Validity period** | Cuánto tiempo tiene el cliente para aceptar, contado desde guardar/enviar. Ejemplos: 15 con Minutes, 1 con Hours, 30 con Days. Guardar recalcula el vencimiento desde ahora. El cliente no puede aceptar tras el vencimiento. Periodos cortos pueden caducar antes de que el cron diario envíe recordatorios. |
| **Validity unit** | Minutos, horas o días junto al número de validez. |
| **Payment hint** | Nota breve sobre el pago esperado, p. ej. "30 days net transfer". Se muestra en la vista del cliente y en el PDF. No fuerza un módulo de pago. |
| **Global discount %** | Descuento extra 0–100 sobre todas las líneas de producto antes del envío. En el checkout puede aplicarse como regla de carrito. |
| **Global discount amount (tax excl.)** | Descuento fijo sobre el subtotal de productos. El porcentaje se aplica primero cuando ambos están definidos. |
| **Shipping label** | Nombre en el PDF, p. ej. "Express delivery". |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Cargo de entrega. El importe con impuestos se calcula automáticamente desde el sin impuestos cuando hay una regla fiscal en los ajustes del módulo. Incluido en el total y pasado al checkout como envío fijo. |
| **Messages from customer** | Todo lo que escribió el cliente (solicitud, petición de cambio, rechazo). Solo lectura. Responda en los campos de abajo. |
| **General message to customer** | Mensaje permanente siempre visible para el cliente (alcance, plazo, condiciones). Se muestra en la vista del presupuesto, PDF y correos. |
| **Internal note** | Nota privada del equipo. Nunca se muestra al cliente. |
| **Line items** | Líneas de producto y de servicio personalizado. Añada un producto del catálogo (elija combinación si hace falta). Añada una línea personalizada: descripción, cantidad, precio unitario sin impuestos, % de impuestos. Las líneas personalizadas aparecen en el PDF y en el checkout van al producto de tarifa. Mensajes: **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | Nota puntual solo para este **Save & send**. Explica qué cambió. Se borra tras el envío. Aparece en la línea de tiempo, historial opcional del PDF y el correo de ese envío. |
| **Version history** | Instantáneas de versiones anteriores. |
| **Save as template** | Introduzca un nombre de plantilla y guarde. Luego cree nuevos presupuestos desde esa plantilla para otro cliente. Mensajes: **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Cronología de eventos del personal y del cliente en este presupuesto. |

Duplicar desde la lista o el editor: **Unable to duplicate quote.** si falla. Tras duplicar, edita la copia.

### 3.6 Audit log

Pestaña del módulo: actividad reciente (solicitudes, envíos, aceptación/rechazo, negociaciones). Use **View** para el contexto completo. Abra **Orders**, **Audit log** para filtros, exportación e historial completo.

Finalidad: rastro de solo anexión para cumplimiento y resolución de problemas. Las entradas no se pueden editar ni eliminar. Cada fila guarda el nombre e ID del actor (empleado o cliente) en el momento de la acción. Insignias de actor: Employee, Customer, System.

### 3.7 Settings — Theme & display

Abra **Settings**. Pulse **Save** al final tras los cambios.

![Theme and display](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Field | At the start | What it does |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Selecciona qué plantilla y conjunto CSS se usan para My quotes, la vista previa del presupuesto y el enlace de la cuenta de cliente. Déjelo en Auto-detect salvo que la detección de su tema fork falle — entonces fuerce Classic o Hummingbird. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | Cómo se muestran las cantidades de línea en front office, back office, PDF y correos. O **Fixed decimals (e.g. 1.000, 2.500)**. Los campos de formulario usan el mismo formato para los valores por defecto. |
| **Quantity decimal places** | 3 | Dígitos tras el decimal cuando el formato es decimales fijos. Suele ser 3 para B2B o 2 para retail. Se ignora en modo entero. |

### 3.8 Settings — General

![General](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Field | At the start | What it does |
|---|---|---|
| **Module enabled** | **Yes** | Interruptor maestro de toda la función de presupuesto a pedido. Yes: los clientes solicitan presupuestos y el personal gestiona ofertas. No: oculta todos los botones de presupuesto y los enlaces de la cuenta de cliente sin desinstalar. Cuando está desactivado, no hay solicitudes nuevas ni botones en carrito, producto o páginas de categoría. Los presupuestos existentes permanecen en el back office. |
| **Product page quote button** | **Yes** | Muestra **Request a quote** en cada página de producto. Para tiendas B2B donde el comprador pide precio de un solo SKU. El cliente debe estar conectado (o flujo de invitado permitido) y en un grupo permitido. El modo Instant abre el formulario para ese producto. El modo List añade cantidad y combinación a la lista flotante de presupuesto. |
| **Cart quote button** | **Yes** | Muestra **Request a quote** en el carrito. Actívelo cuando los clientes pidan ofertas de varios productos a la vez. Respeta el mínimo de carrito indicado abajo. El contenido actual del carrito pasa a ser la base de una nueva solicitud de presupuesto tras confirmar. |
| **Category / list quote button** | **Yes** | **Request quote** compacto en páginas de listado (categoría, búsqueda, novedades). Mismas reglas de elegibilidad. El modo Instant abre el flujo de presupuesto del producto. El modo List añade el producto (combinación por defecto, cantidad 1) a la lista flotante. |
| **Product quote mode** | **Instant — open form for this product** | Instant: abrir el formulario del producto actual. List: añadir a una cesta de presupuesto; el botón flotante abre un formulario con todos los productos. Las solicitudes desde el carrito siguen siendo independientes. El botón flotante aparece solo en modo List cuando la lista no está vacía. |
| **Floating quote button position** | **Bottom right** | O **Bottom left**. Solo cuando el modo de presupuesto de producto es List. La insignia muestra el número de productos; abre el formulario de solicitud multiproducto. |
| **Allow guests** | **No** | Si los visitantes sin cuenta pueden iniciar una solicitud. Manténgalo desactivado para B2B estricto. Actívelo si los invitados deben ver el botón — aun así se les pide iniciar sesión o registrarse antes de guardar la solicitud. No crea presupuestos anónimos. |

### 3.9 Settings — Quote button visibility

![Visibility](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Field | At the start | What it does |
|---|---|---|
| Customer groups | all groups | Restringe quién puede ver los botones de presupuesto. Todos los grupos, o solo los seleccionados (p. ej. Wholesale). Los clientes fuera de los grupos seleccionados no verán los botones aunque el módulo esté activado. |
| **Enable catalog visibility rules** | **No** | Activa o desactiva las reglas de botones de presupuesto basadas en el catálogo. Actívelas para limitar presupuestos a productos, categorías, marcas o proveedores concretos. Si están desactivadas, cualquier producto puede presupuestarse (siguen aplicando las reglas de grupo). Si están activadas, se aplican whitelist/blacklist y los filtros de abajo. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist: botones solo en productos coincidentes. Blacklist: oculta botones en productos coincidentes. Un producto coincide si está en la lista de productos o pertenece a una categoría, fabricante o proveedor seleccionado. |
| Catalog pickers | empty | Categorías (árbol), productos (búsqueda), fabricantes y proveedores. Déjelos vacíos para aplicar solo filtros auxiliares. Las reglas se combinan con OR — basta una coincidencia. |
| **Minimum product price** | 0 | Oculta botones de presupuesto por debajo de este precio de tienda con impuestos. 0 desactiva. Se aplica cuando las reglas de catálogo están activadas. |
| **Exclude virtual products** | **No** | Impide presupuestar productos descargables / virtuales cuando las reglas de catálogo están activadas. |
| **Exclude out-of-stock products** | **No** | Oculta botones cuando el producto no se puede pedir sin stock (respeta el comportamiento de PrestaShop ante falta de stock). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | Cuando el carrito mezcla productos presupuestables y no presupuestables: Show = botón visible, solo se importan líneas elegibles; Hide = botón oculto hasta que el carrito sea solo presupuestable. Todo elegible → siempre mostrar. Todo excluido → siempre ocultar. |

### 3.10 Settings — Product quote request form

| Field | At the start | What it does |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Casilla de privacidad obligatoria en el modal de solicitud de presupuesto de producto (GDPR). Los clientes deben aceptar antes de enviar. |
| **Privacy policy CMS page** | none | Página CMS enlazada desde la casilla. Si está vacía, el texto de la casilla no tiene enlace. |
| **Enable reCAPTCHA** | **No** | Protege el formulario de solicitud de presupuesto de producto con Google reCAPTCHA v2. Al activarlo, se requieren las claves de sitio y secreta de abajo. |
| **reCAPTCHA site key** | empty | Clave pública de sitio desde la administración de Google reCAPTCHA (casilla v2). |
| **reCAPTCHA secret key** | empty | Clave secreta. Se guarda en la configuración de la tienda. |
| **Minimum cart total** | 0 | Valor mínimo de carrito antes de mostrar el botón de presupuesto del carrito. Moneda predeterminada de la tienda. 0 = sin mínimo. Solo afecta al botón del carrito, no a solicitudes de un solo producto. Los carritos pequeños no mostrarán el botón. |

### 3.11 Settings — Offers & references

| Field | At the start | What it does |
|---|---|---|
| **Default validity** | 30 | Duración predeterminada de validez de un presupuesto tras su creación. Número más unidad: minutos para ofertas flash, horas para decisiones el mismo día, días para B2B estándar. Define valid_until en presupuestos nuevos desde la tienda, el back office y duplicados. Puede anularse por presupuesto en el editor. |
| **Default validity unit** | **Days** | Minutos, horas o días con el número de arriba. Los correos de recordatorio y el estado Expired automático siguen dependiendo del cron para los recordatorios. |
| **Expiry reminder (days before)** | 3 | Correo de recordatorio antes del vencimiento. Lo envía solo el trabajo cron diario. Cada presupuesto elegible recibe como máximo un recordatorio con enlace para ver y aceptar. Sin cron, no hay recordatorios. |
| Cron URL | generated token | Recordatorios automáticos de vencimiento y actualizaciones de estado. Añada la URL a crontab una vez al día (ejemplo 08:00). Regenere el token si queda expuesto. El vencimiento también se aplica al abrir el presupuesto; los correos de recordatorio siguen necesitando cron. |
| **Reference prefix** | Q | Prefijo de los números de presupuesto. El módulo añade año y secuencia, p. ej. Q-2026-00042. Ayuda al personal y a los clientes a reconocer documentos en correo y PDF. |
| **Notify staff on new request** | **Yes** | Correo al personal de la tienda cuando un cliente envía una solicitud. Compruebe que Preferences > Contact e-mail sea correcto. Plantilla: qe-request-staff en la pestaña Emails. |

Aviso amarillo en pantalla: el cron es necesario para la automatización de validez; el vencimiento también se aplica al abrir; los recordatorios usan la URL de cron.

### 3.12 Settings — Checkout

| Field | At the start | What it does |
|---|---|---|
| **Shipping / service tax rule** | shop default tax rule | Regla de IVA para envío y líneas de servicio personalizado cuando introduce importes sin impuestos. Elija un grupo de reglas fiscales en Catalog → Products. Al seleccionarlo, guardar un presupuesto recalcula el envío con impuestos desde el sin impuestos. |
| **Fee product (custom lines)** | created on install | Producto virtual oculto que lleva las líneas de servicio personalizado al checkout. Se crea automáticamente — cámbielo solo si debe apuntar las líneas personalizadas a otro producto. En el checkout, los totales de servicio se convierten en una línea de carrito con el precio bloqueado del presupuesto. |

### 3.13 PDF

Abra la pestaña **PDF**. Leyenda: **PDF documents**. Cuando el PDF está desactivado, los botones de descarga se ocultan y las URL de PDF devuelven no encontrado.

| Field | At the start | What it does |
|---|---|---|
| **Enable PDF** | **Yes** | Interruptor maestro de generación de PDF y enlaces de descarga. Desactívelo si no quiere proformas PDF. Si está desactivado, los botones PDF se ocultan en back office, tienda y detalle de pedido; las URL directas de PDF devuelven no encontrado. Las plantillas de correo siguen recibiendo un marcador de URL de PDF vacío. |
| **Use shop logo on PDF** | **Yes** | Usa el logotipo de la tienda de Preferences > Themes. No: usar solo un logotipo personalizado subido abajo (si hay). El logotipo aparece en la parte superior de los documentos PDF / proforma. |
| **Add negotiation history to PDF** | **No** | Añade un registro breve de comunicación (peticiones de cambio, reenvíos, aceptación, rechazo). Tabla compacta antes de las condiciones. Vacío si no hay actividad de negociación. |
| **Custom PDF logo** | empty | PNG o JPG opcional solo para PDF de presupuestos. Sustituye el logotipo de la tienda cuando existe. |
| **PDF terms & conditions** | empty | Condiciones legales o comerciales al final de cada PDF. |
| **Authorized signature** | empty | Nombre o línea del firmante, p. ej. "John Smith, Sales Director". Déjelo vacío para omitirlo. |

### 3.14 Emails

Abra la pestaña **Emails**. Correos transaccionales del ciclo de vida del presupuesto. Edite asunto y cuerpo por idioma. Use los marcadores de la barra lateral del editor (nombre del cliente, referencia del presupuesto, enlace, totales). Claves integradas: qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Clientes y personal los reciben cuando se solicita, envía, acepta un presupuesto o está a punto de caducar. Pruebe tras los cambios.

### 3.15 API

Abra la pestaña **API**. Conecte CRM, ERP o automatización. Introduzca una etiqueta de clave y **Generate new API key**. Copie la clave. **Revoke** la desactiva (confirme). Vacío: **No API keys yet.** **API documentation** describe las acciones: list, get, pending, stats, update_status. Llame a la URL de API del módulo con la clave.

### 3.16 Notifications

Abra **Notifications** (**Staff digest notifications**). Resumen periódico cuando los presupuestos requieren acción, sin un correo por cada evento.

Qué cuenta como en espera: **Pending review** (solicitud nueva) o **Negotiation** (el cliente pidió cambios). Sent, accepted, expired y converted no se incluyen. El cron se ejecuta según su programación. Cuando el digest está activado, hay al menos un presupuesto en espera y ha transcurrido el intervalo, se envía un mensaje a cada canal configurado. El personal ve un resumen con referencias, estado, nombre del cliente y enlaces al back office (hasta 20 presupuestos listados).

| Field | At the start | What it does |
|---|---|---|
| **Enable digest** | **No** | Interruptor maestro. Actívelo tras configurar al menos un canal. El cron debe estar programado — los digests no se envían por visitas a páginas. Si está desactivado, el cron sigue gestionando recordatorios de vencimiento y actualizaciones de estado, pero no hay digest. |
| **Interval (hours)** | 24 | Tiempo mínimo entre digests (1–168). Ejecute el cron al menos con esa frecuencia. Tras un digest correcto, el siguiente espera hasta que pasen esas horas. |
| **E-mail recipients** | empty | Separados por comas o punto y coma. Vacío usa el correo de la tienda de Preferences > Contact. Plantilla qe-staff-digest. |
| **Slack webhook URL** | empty | URL de webhook entrante. Déjela vacía para omitir Slack. |
| **Teams webhook URL** | empty | URL de webhook del conector. Déjela vacía para omitir Teams. |

**Save** guarda los ajustes. **Send test digest now** envía una prueba cuando hay presupuestos en espera. Misma URL de cron que en Settings.

### 3.17 Updates

Abra **Updates**. **Check Now** comprueba si hay una versión nueva. **Automatic Notifications** activado o desactivado. **Save** guarda los ajustes de actualización.

### 3.18 Quote block on an order

En un pedido creado desde un presupuesto, el back office muestra **Source quote** con un enlace al presupuesto y, opcionalmente, **View quote PDF**.

## 4. Front office

Los clientes ven las herramientas de presupuesto cuando el módulo está activado y su grupo está permitido.

**Product page.** **Request a quote** abre el formulario (instant) o añade a la lista de presupuesto (modo list). La casilla de privacidad y reCAPTCHA se aplican si están activados.

**Product list.** **Request quote** — mismas reglas.

**Cart.** **Request a quote** — respeta el mínimo de carrito y las reglas de carrito mixto. El carrito confirmado se convierte en un presupuesto pendiente.

**List mode.** El botón flotante con contador abre el formulario de solicitud multiproducto.

**Customer account.** Enlace a **My quotes**: historial, estado, valid until, **View**, PDF si está activado, **Checkout** tras aceptar, **Request re-opening** cuando está caducado/bloqueado. Vacío: **You have no quotes yet. Request a quote from a product page or your cart to get started.** Tras enviar: **Your quote request has been submitted. Our team will prepare an offer shortly.**

**Quote view.** Aceptar, rechazar, pedir cambios, descargar PDF, checkout cuando está aceptado. Caducado bloqueado: **Locked — validity expired**.

Los visitantes invitados pueden ver botones si **Allow guests** es **Yes**, pero la solicitud solo se guarda para un cliente conectado.

No hay captura de la tienda en este paquete porque la tienda de prueba no era accesible cuando se terminaron las pantallas.

## 5. Common problems

**No quote button on product or cart.** Compruebe **Module enabled**, el interruptor del botón correspondiente, el grupo de cliente y la visibilidad del catálogo. Para el carrito, compruebe **Minimum cart total** y **Mixed cart**.

**Guest cannot finish a request.** El envío siempre requiere una cuenta.

**Quote is locked / cannot edit.** Desbloquee si está aceptado o caducado (extienda la validez). Los presupuestos convertidos permanecen bloqueados al pedido.

**Customer cannot accept.** El estado debe ser Sent o Negotiation, y valid until debe estar en el futuro.

**Reminder e-mails never arrive.** Programe la URL de cron y mantenga **Expiry reminder** por encima de cero. Abrir un presupuesto puede caducarlo sin cron; los recordatorios siguen necesitando cron.

**PDF buttons missing.** Active **Enable PDF**.

**reCAPTCHA blocks the form.** Desactívelo o introduzca ambas claves.

**Staff digest never arrives.** Active el digest, configure un canal, ejecute el cron al menos con la frecuencia del intervalo.

**Uninstalled and menu is gone.** Reinstale. La desinstalación elimina las tablas de presupuestos. El producto de tarifa puede permanecer en el catálogo.

## 6. Developer guide

### 6.1 Overview

Nombre técnico `quoteenterprise`, versión 1.7.6, clase `quoteenterprise` extends `Module`. Nombre para mostrar mediante `$this->l('Quote Enterprise')`. Autor MyPresta.eu. Pestaña `checkout`. URL del producto en `$this->mypresta_link`.

Flujo: solicitud → fila `quote` → edición/envío del personal → aceptación/negociación del cliente → checkout → pedido. Los textos de campos para comerciantes están en `QuoteSettingDescTrait` y en los métodos `desc*` del editor de presupuestos.

### 6.2 Files

- `quoteenterprise.php` — instalación, hooks, entrada de configuración, URL de cron.
- `classes/QuoteAdmin.php` — pestañas de configuración y formularios de ajustes.
- `classes/QuoteAdminQuoteForm.php` — editor de presupuestos.
- `classes/QuoteQuotesManager.php` — resumen, guardar/enviar/líneas/plantillas.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Controllers

Administración bajo **Orders** (`AdminParentOrders`). Controladores front en `$this->controllers`. El cron espera `QE_CRON_TOKEN`. La API espera una clave activa y un nombre de acción.

### 6.4 Hooks

Registrados: `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. No se exponen hooks personalizados.

### 6.5 Overrides

Este módulo no incluye overrides de clases ni de controladores.

### 6.6 Database

| Table | Contents |
|---|---|
| `quote` | Cabecera del presupuesto. |
| `quote_detail` | Líneas. |
| `quote_revision` | Instantáneas de versión. |
| `quote_audit_log` | Actividad de solo anexión. |
| `quote_api_key` | Claves API. |
| `qe_cart_quote` | Enlace carrito–presupuesto. |

La desinstalación elimina estas tablas. `QuoteSchema::ensure` e `inconsistency()` reparan piezas faltantes al abrir la configuración.

### 6.7 Keys and translations

Claves de configuración `QE_*`. Valores por defecto en `installDefaults()`. Nuevo idioma: `translations/{iso}.php`. Ayuda de campos para el comerciante: `QuoteSettingDescTrait` y métodos `desc*` del editor. Cadenas mediante `$this->l()` y `{l s=... mod='quoteenterprise'}`.

### 6.8 Extending

Sobrescriba las plantillas front bajo `modules/quoteenterprise/` en el tema. Se admiten Classic y Hummingbird. Un diseño PDF distinto implica cambiar la plantilla PDF o el código del módulo.

## 7. Support

Página del módulo: [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

Para escribir sobre este módulo, inicie sesión en su cuenta de cliente en [mypresta.eu](https://mypresta.eu/), abra [Contact](https://mypresta.eu/contact.html) y elija el asunto **Support for paid modules**. El formulario indica que el inicio de sesión es obligatorio. Tras iniciar sesión, elija este módulo en su historial de compras.
