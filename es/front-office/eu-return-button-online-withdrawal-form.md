---
title: "Return Button Pro - documentación y manual de usuario"
description: "Configure el formulario de desistimiento UE, gestione casos en el back office y resuelva problemas habituales si ya usa Return Button Pro."
sidebar:
  label: "Return Button Pro - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo EU Return Button – Online Withdrawal Form en MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Las capturas de este manual muestran el back office en inglés. Utilice los mismos nombres de menú y etiquetas que aparecen aquí.

## 1. Requisitos

Return Button Pro funciona en PrestaShop 1.6, 1.7, 8 y 9. Use el paquete que coincida con su tienda: el build dedicado a PrestaShop 1.6 para tiendas 1.6 y el build para PrestaShop 1.7–9 en tiendas más nuevas. Si en el historial de pedidos de MyPresta.eu hay ambos paquetes, descargue el ZIP correcto.

- PrestaShop: 1.6.x, 1.7.x, 8.x y 9.x
- PHP: las versiones en las que ya funciona su PrestaShop, incluidos entornos antiguos con PrestaShop 1.6 (PHP 5.6 y PHP 7.x) y las versiones exigidas por PrestaShop 1.7–9 (PHP 7.1+ / PHP 8.x según el hosting y la tienda). El módulo también se mantiene para entornos PHP 7.x y el PHP actual de la tienda.
- Extensiones PHP usadas por el módulo: JSON, curl (comprobaciones de actualización), fileinfo (comprobaciones MIME de adjuntos), hash (tokens y seguridad de invitados)
- Otros módulos: no son necesarios. Si el módulo gratuito Return Button está instalado y activado, desactívelo antes de configurar o usar Return Button Pro. Ambos no pueden ejecutarse a la vez.
- Cuentas externas: ninguna. Las comprobaciones opcionales de actualización de MyPresta.eu usan Internet desde la pestaña **Updates**.

## 2. Instalación

1. Suba el ZIP del módulo en **Modules** → **Module Manager**, luego instale y active **Return Button Pro**.
2. Tras la instalación, aparece el elemento **Withdrawals** bajo **Customers**. Abra la configuración desde **Module Manager** → **Return Button Pro** → **Configure** (pestañas: **Dashboard**, **Settings**, **Updates**).
3. La instalación no vacía la caché de PrestaShop. Vacíe la caché usted mismo tras cambios de tema o hooks si el escaparate sigue viéndose mal.

Desinstalación: se elimina la entrada de menú **Withdrawals** y los valores de configuración. Las tablas de desistimiento y los registros de casos permanecen en la base de datos como prueba legal. Reinstalar no borra esos registros; el módulo puede reutilizarlos cuando las tablas ya existen. Los adjuntos del personal subidos en la carpeta del módulo no se eliminan al desinstalar.

Si actualiza desde el módulo gratuito Return Button, Pro puede copiar ajustes compatibles y migrar tablas Pro vacías desde datos del módulo gratuito cuando Pro aún no tiene filas. Desactive primero el módulo gratuito.

## 3. Configuración y trabajo en el back office

### 3.1 Proceso completo de desistimiento

Flujo de extremo a extremo desde el escaparate hasta la gestión del personal:

1. El cliente encuentra la entrada de desistimiento: botón del pie, enlace de Mi cuenta, botón del detalle del pedido o la URL del formulario cuando el acceso de invitados está activo.
2. **Paso 1 – pedido:** los clientes conectados ven sus pedidos con indicaciones de elegibilidad (días restantes, motivos de no disponibilidad). Los invitados introducen referencia del pedido y correo. El cliente selecciona un pedido elegible, elige **Full order** o **Partial** (con cantidades en líneas permitidas), opcionalmente añade un mensaje e IBAN, y continúa.
3. **Paso 2 – confirmación:** el cliente revisa el resumen de la declaración. Cuando **Require legal confirmation checkbox** está activo, debe marcar el texto legal y luego enviar.
4. El módulo guarda el caso, lo pasa a **Registered** y envía la confirmación al cliente (soporte duradero) más una notificación a la tienda (y **Notification email** si está configurado). La página de éxito muestra la referencia de desistimiento.
5. El personal abre **Customers** → **Withdrawals** (o el panel lateral del pedido), abre **View**, establece el estado (**In progress**, **Refunded**, **Rejected**, etc.) e introduce un mensaje al cliente cuando sea obligatorio.
6. El cliente sigue el estado mediante **Track withdrawal status**, la página de estado y **Print / save PDF**. Los mensajes del personal por cambios de estado aparecen en el historial de desistimiento del cliente.

Estados usados por el módulo:

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Pending** | Estado breve cuando la declaración se guarda por primera vez | Caso abierto antes de que termine la confirmación legal del cliente, o cuando el personal fija este estado más tarde. Cuenta para el bloqueo de duplicados junto con otros estados abiertos. |
| **Registered** | Tras la confirmación del cliente en el paso 2 | Declaración registrada; se intentan los correos de confirmación. Estado por defecto tras el envío. |
| **In progress** | Acción del personal | La tienda gestiona el caso (devoluciones, comprobaciones, preparación del reembolso). Sigue bloqueando una segunda solicitud activa si el bloqueo de duplicados está activo. |
| **Refunded** | Acción del personal | Caso cerrado con reembolso. Visible en la página de estado del cliente. |
| **Rejected** | Acción del personal | Caso cerrado sin reembolso. Use un mensaje claro al cliente cuando el ajuste lo exija. |

Alcance en el formulario: **Full order** o **Partial**. Tipo: **Contract withdrawal** (pagado) o **Contract cancellation (unpaid order)** cuando el pedido nunca se pagó.

### 3.2 Dashboard

Abra **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filtre con **From** / **To** y **Apply**, o restablezca con **Last 30 days**. El panel muestra totales de todos los tiempos, backlog pendiente, perfil de tema detectado, hook de pie activo, KPIs (desistimientos en el periodo, tasa vs. pedidos, proporción de confirmación por correo, media de días del pedido al desistimiento, proporción parcial/total, cancelaciones, proporción reembolsada de casos cerrados, tasa de rechazo), un gráfico de envíos diarios, desglose por estado, productos más desistidos y casos pendientes más antiguos con **Open**.

Use **Manage all withdrawals** para la lista bajo Customers, o **Export CSV** para descargar los casos de la tienda actual.

### 3.3 Settings

Abra la pestaña **Settings** y haga clic en **Save** tras los cambios.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Integración con el tema

Adapte el módulo a Classic, Hummingbird o un tema personalizado. Ajuste estos valores si botones o formularios se ven sin estilo tras una actualización del tema.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Elige qué plantillas y CSS de front office carga el módulo (Classic vs Hummingbird). Estilo correcto del botón, diseño del formulario y aspecto del enlace de Mi cuenta. Deje Auto-detect salvo que el botón se vea mal tras un cambio de tema; entonces fuerce Classic-type o Hummingbird-type según su tema activo. Tras el cambio, vacíe la caché de PrestaShop y actualice el escaparate. |
| **Footer button hook** | Auto (by theme profile) | Define dónde se inyecta el botón de desistimiento en el pie. Auto sigue el perfil del tema (Hummingbird → displayFooterBefore, Classic → displayFooter). Si falta el botón o está desalineado, pruebe displayFooterBefore o displayFooter manualmente, guarde, vacíe la caché y revise el pie de la tienda. Para colocación manual, ponga el hook personalizado en una plantilla del tema y seleccione displayRbproButton aquí; mantenga **Footer button** activado para que el botón solo se muestre en esa plantilla. |

#### General y acceso

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Module enabled** | Yes | Interruptor maestro de todo el módulo. Al desactivarlo, botones de desistimiento, formulario, acceso de invitados y seguimiento se ocultan en el escaparate; los registros existentes en el back office permanecen. Úselo para mantenimiento o revisión legal sin desinstalar. |
| **Public status tracking page** | Yes | Activa una página pública donde los clientes consultan el estado del desistimiento con referencia + correo (sin login). Reduce tickets del tipo «¿dónde está mi devolución?». Actívela si quiere un enlace **Track withdrawal status** junto al botón del pie; comunique la referencia del correo de confirmación. Desactívela si gestiona el estado solo por correo de cuenta o teléfono. |
| **Guest access (order ref + email)** | Yes | Permite a clientes no conectados abrir el formulario introduciendo referencia del pedido y correo en el paso 1. Recomendado para ventas a distancia B2C en la UE. Desactívelo si solo los clientes conectados pueden desistir. Las sesiones de invitado usan una cookie firmada. |
| **Block duplicate active requests** | Yes | Impide un segundo desistimiento abierto para el mismo pedido mientras uno ya está Pending, Registered o In progress. Evita casos duplicados y reembolsos conflictivos. Manténgalo activo en producción. Desactívelo solo para pruebas o procesos inusuales de reclamación parcial. |
| **Require legal confirmation checkbox (step 2)** | Yes | Obliga al cliente a marcar una casilla con redacción legal antes de enviar. Registro explícito de consentimiento alineado con las normas de desistimiento de la UE. Edite el texto de la casilla por idioma en Texts & SEO. Si está desactivado, el envío sigue registrándose sin casilla obligatoria. |
| **Require message to customer when changing status** | Yes | El personal debe introducir un mensaje al cliente antes de actualizar el estado de un desistimiento. El mensaje se guarda en la pista de auditoría y se muestra en la página de estado del cliente. Desactívelo solo si necesita cambios de estado rápidos sin escribir cada vez. |
| **Show deadline countdown to customer** | Yes | Muestra cuántos días quedan del plazo legal de desistimiento (lista de pedidos y formulario). Requiere un mapeo correcto de **Order state = delivered** y el periodo de desistimiento. Si las fechas parecen incorrectas, revise el historial del pedido y el estado de entregado. |
| **Optional IBAN field** | No | Añade un campo IBAN opcional en el formulario para reembolsos. Actívelo solo si reembolsa por transferencia y su política de privacidad lo cubre. Déjelo desactivado si solo reembolsa al método de pago original. |
| **Notification email** | Empty | Dirección adicional que recibe notificaciones de nuevos desistimientos (además del contacto de la tienda). Ejemplo: returns@yourshop.com. Déjela vacía para usar solo el flujo de correo por defecto de PrestaShop sin este destinatario. |

#### Reglas de desistimiento

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Días naturales que tienen los clientes para desistir tras considerarse entregado el pedido. Por defecto 14 para contratos a distancia en la UE. Cámbielo solo si la ley o sus condiciones exigen otro valor. La cuenta atrás empieza en la fecha de entrega derivada del historial del pedido y **Order state = delivered**. |
| **Order state = delivered** | Auto | Estado de pedido que marca la mercancía como entregada (inicio del plazo de desistimiento). Elija el estado que fija cuando el paquete se entrega (por ejemplo Delivered, o Shipped si ese es su estado final). Auto usa un valor sensato de su tienda; sobrescriba si los plazos usan la fecha incorrecta. |
| **Allowed order statuses** | All order statuses | Controla cuándo los clientes pueden enviar un desistimiento según el estado actual del pedido. Elija **All order statuses** para omitir el filtro, o **Only selected statuses** y mueva estados de la columna izquierda a **Allowed for withdrawal**. Los pedidos fuera de la lista aparecen como no disponibles en la lista de pedidos de la cuenta. |
| **Excluded products** | Empty | Productos concretos que no pueden desistirse (bienes precintados, a medida, etc.). Busque por nombre o conserve IDs; las líneas excluidas muestran el mensaje de exclusión en el formulario. |
| **Excluded product variants** | Empty | Variantes concretas excluidas del desistimiento. Busque el producto y seleccione la variante. |
| **Excluded categories** | Empty | Todos los productos de estas categorías no son desistibles. |
| **Excluded manufacturers** | Empty | Los productos de estos fabricantes no pueden desistirse. |
| **Excluded suppliers** | Empty | Los productos vinculados a estos proveedores no pueden desistirse. |
| **Excluded customer groups** | Empty | Los clientes de estos grupos no pueden usar el desistimiento en absoluto (sin acceso al formulario, botones ocultos). |

#### Pie y apariencia

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Footer button** | Yes | Muestra la llamada a la acción principal de desistimiento en el pie de la tienda (hook configurado arriba). Desactívelo si solo quiere enlaces de Mi cuenta y detalle del pedido. Requiere **Module enabled** y un hook de pie correcto. |
| **Footer theme** | Light footer (dark text) | Esquema de color para texto y enlaces del pie (no el fondo del botón). Elija Light en pies claros, Dark en pies negros/oscuros para que **Track withdrawal status** siga legible. Vacíe la caché tras el cambio. |
| **Footer alignment** | Center | Alineación horizontal del bloque del botón del pie: Left, Center o Right. Afecta solo a la salida del hook de pie. |
| **Button color** | #2563eb | Color de fondo de los botones de desistimiento (pie, detalle del pedido, etc.). Elija un color hex con suficiente contraste respecto al texto blanco. No cambia el color primario del tema de forma global. |
| **Custom CSS** | Empty | CSS adicional en páginas donde aparecen botones del módulo. Úselo para márgenes, tipografías u ocultar elementos sin editar archivos del tema. Pruebe primero en staging. |
| **Link in customer account** | Yes | Añade una entrada de desistimiento en My Account. Recomendado activado. Desactívelo solo si se basa únicamente en enlaces del pie o del pedido. |
| **Link on order detail** | Yes | Muestra la acción de desistimiento en la página de detalle del pedido cuando es elegible. Los pedidos bloqueados muestran un motivo breve en lugar del botón. |

#### Texts & SEO

Complete cada idioma activo de la tienda.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Noindex on form page** | Yes | Añade robots noindex,nofollow en la URL del formulario de desistimiento para que las páginas legales/formulario no salgan en buscadores. Desactívelo solo si quiere indexar el formulario a propósito. |
| **Button label** | Withdraw from contract | Texto de todos los botones y enlaces de desistimiento. Una etiqueta corta funciona mejor en el pie. Frase principal orientada al cliente del módulo. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Se muestra junto a productos excluidos en el formulario. Explique por qué no se puede seleccionar el artículo; mencione sus condiciones si hace falta. |
| **SEO title** | Withdraw from contract | Título HTML de la página del formulario de desistimiento (pestaña del navegador). Manténgalo bajo unos 60 caracteres por idioma. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta descripción del formulario. Suele no usarse para ranking con noindex activo. Déjela en blanco para omitirla. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Etiqueta junto a la casilla obligatoria del paso 2. Use una redacción clara y adecuada al país. Obligatorio cuando **Require legal confirmation checkbox** está activo. |

### 3.4 Updates

Abra la pestaña **Updates**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Manual Check** | — | Comprueba en MyPresta.eu si hay una versión más reciente del módulo. Verá **New version available!** o **Module is up to date!**. Necesita curl y HTTPS saliente. |
| **Automatic Notifications** | Enabled (module default for update prefs) | Cuando está activado, el back office puede mostrar un aviso de que existe una nueva versión. Guarde con **Save**. |
| **Product Page** | Link on form | Abre la página oficial del producto con información de versiones. Use Soporte (§7) para ayuda de módulos de pago tras iniciar sesión. |

Si el módulo gratuito Return Button sigue activado, los ajustes y las acciones de actualización quedan bloqueados hasta que lo desactive.

### 3.5 Lista de desistimientos

Vaya a **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

El orden por defecto es el envío más reciente primero. Columnas:

| Campo | Al inicio | Qué hace |
|---|---|---|
| **ID** | Auto | Id interno del caso. |
| **Submitted** | From form | Fecha y hora del envío del cliente. |
| **Order** | From order | Referencia del pedido PrestaShop. |
| **First name** / **Last name** / **Email** | From customer | Identidad de contacto del caso. |
| **Scope** | Full order or Partial | Si se desistió el pedido completo o líneas seleccionadas. |
| **Type** | Contract withdrawal or cancellation | Desistimiento de pedido pagado vs. cancelación de pedido no pagado. |
| **Status** | Registered after confirm | Estado actual del caso (Pending, Registered, In progress, Refunded, Rejected). |
| **Email** | Yes/No | Si el correo de confirmación se registró como enviado. |

Use búsqueda y ordenación en la lista. Abra un caso con **View**. No hay acción **Add new**: las solicitudes solo las crean los clientes en el escaparate. Si alguien intenta crear un caso en el back office, la advertencia explica que los desistimientos no se pueden crear manualmente y se vuelve a mostrar la lista.

Exporte CSV desde **Dashboard** (**Export CSV**) cuando necesite una hoja de cálculo de los casos de la tienda.

### 3.6 Vista del caso de desistimiento

Abra una fila con **View**.

La cabecera muestra referencia, ID, fecha de envío, estado, tipo, alcance, marca y hora de correo enviado, plazo, IP, user-agent, nombre y correo del cliente, y un enlace al pedido PrestaShop. El bloque de productos lista cada línea desistida con cantidad y precio unitario. El IBAN y el mensaje del cliente aparecen cuando el cliente los proporcionó.

**Update status**

1. Elija **New status**.
2. Escriba **Message to customer** (obligatorio cuando ese ajuste está activo; opcional en caso contrario). El texto de ayuda explica que el mensaje aparece en el historial de desistimiento del escaparate.
3. Haga clic en **Update status**.

Éxito: **Status updated.** Otros mensajes: **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** vuelve a enviar la confirmación al cliente, actualiza la marca de enviado si tiene éxito y registra el evento. Éxito: **Confirmation email sent.** Fallo: **Could not send email.**

**Internal notes** son solo para el personal. Introduzca texto y haga clic en **Add note**. Las notas aparecen bajo **Internal notes** y en la pista de auditoría; no sustituyen el mensaje de estado orientado al cliente.

**Attachments** aceptan subidas del personal (PDF e imágenes habituales, máx. 10 MB). Descargue haciendo clic en el nombre del archivo. Mensajes: **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** lista fecha, evento, empleado y detalles (transiciones de estado y mensajes). Eventos típicos: el cliente envió la declaración, el cliente confirmó la declaración legal, estado actualizado, correo de confirmación enviado, documento añadido, nota interna añadida.

Use **Back to list** para volver a **Withdrawals**.

### 3.7 Panel lateral del pedido en el back office

En PrestaShop 1.7.7 y posteriores, abra un pedido en el back office. Cuando ese pedido tiene casos de desistimiento, un bloque lateral **Withdrawal requests** lista cada referencia, insignia de estado, fecha y **View** (abre el caso). En builds 1.7 antiguos sin el hook lateral de pedido, use **Customers** → **Withdrawals** y filtre por referencia del pedido.

Los casos pendientes también pueden generar una advertencia en el back office con el recuento de solicitudes pendientes de revisión y un enlace a la lista.

## 4. Escaparate

No se incluyen capturas del escaparate; configure el tema y compruebe la tienda en vivo tras guardar Settings y vaciar la caché.

### 4.1 Pie

Con **Footer button** activo y el hook correcto, las páginas muestran el botón de desistimiento (etiqueta de **Button label**) con estilo de **Button color**, más **Track withdrawal status** cuando el seguimiento público está activo. **Footer alignment** y **Footer theme** controlan el diseño y el contraste del texto. Si el tema nunca llama al hook de pie seleccionado, cambie el hook o coloque el hook personalizado en una plantilla y seleccione esa opción en **Footer button hook**.

### 4.2 Cuenta de cliente

Con **Link in customer account** activo, My Account muestra la entrada de desistimiento (y el enlace de seguimiento donde la plantilla de cuenta lo incluye). Los grupos de clientes excluidos no ven puntos de entrada.

### 4.3 Detalle del pedido

Con **Link on order detail** activo, los pedidos elegibles muestran el botón de desistimiento rellenado para ese pedido. Los casos existentes del pedido se listan con estado. Los pedidos no elegibles muestran un motivo breve en lugar del botón, por ejemplo plazo terminado, estado no permitido, solicitud activa duplicada o sin productos elegibles.

### 4.4 Acceso de invitados

Cuando **Guest access** está activo, un visitante abre el formulario, introduce referencia del pedido y correo, y continúa como un cliente conectado para ese pedido. Cuando el acceso de invitados está desactivado, los invitados ven que deben iniciar sesión (o que usted debe activar el acceso de invitados en Settings). Tokens de seguridad no válidos y demasiados intentos muestran mensajes claros de espera / reintento.

### 4.5 Seguimiento del estado

**Track withdrawal status** pide la referencia de desistimiento (formato tipo RBP-…) y el correo, y luego muestra estado, fecha de envío, alcance, estado del correo de confirmación y enlaces a detalles e impresión. Par incorrecto: **No withdrawal found for these details.**

### 4.6 Página de estado e impresión

Tras el envío, **Withdrawal submitted** muestra la referencia, una lista de comprobación (declaración guardada, correo de confirmación, la tienda procesará), luego **View withdrawal details**, **Track status** y **Print / save PDF**. La página de estado lista productos, cantidades, precios, totales e **Withdrawal history** incluyendo mensajes del personal por actualizaciones de estado. Imprimir abre una página de prueba imprimible con un token seguro del flujo de confirmación.

## 5. Problemas

### 5.1 Return Button gratuito aún activado

**Síntoma:** la configuración está bloqueada; alerta de que el otro módulo de devoluciones está activado; al guardar puede indicar que los cambios no se guardaron hasta desactivar ese módulo.

**Qué hacer:** **Modules** → **Module Manager** → encuentre el módulo gratuito Return Button → **Disable**. Luego abra de nuevo Return Button Pro.

### 5.2 Falta el botón del pie

**Síntoma:** no hay botón de desistimiento en el pie.

**Qué hacer:** confirme que **Module enabled** y **Footer button** están activos. En **Settings**, ponga **Footer button hook** en Auto o pruebe las otras posiciones de pie una a una. Vacíe la caché y recargue en duro la tienda. En temas personalizados, coloque el hook personalizado del módulo en la plantilla y seleccione esa opción en **Footer button hook**. Abra **Dashboard**: muestra el perfil de tema detectado y el nombre del hook de pie activo para compararlo con el tema.

### 5.3 «Return not available — the withdrawal period has ended.»

**Síntoma:** el detalle del pedido o el formulario bloquean el desistimiento con este mensaje.

**Qué hacer:** revise **Withdrawal period** y **Order state = delivered**. Corrija el historial del pedido si la entrega nunca se registró. Amplíe el periodo solo si sus condiciones lo permiten.

### 5.4 «An active withdrawal request already exists for this order.»

**Síntoma:** el cliente no puede abrir un segundo caso.

**Qué hacer:** finalice o cierre el caso existente (**Refunded** / **Rejected**), o desactive temporalmente **Block duplicate active requests** solo si su proceso permite realmente varias reclamaciones abiertas.

### 5.5 «This order status does not allow withdrawal.»

**Síntoma:** el pedido está fuera del filtro de estados permitidos.

**Qué hacer:** en **Settings**, ponga **Allowed order statuses** en **All order statuses**, o añada el estado actual del pedido a **Allowed for withdrawal**.

### 5.6 «No products in this order are eligible for withdrawal.» / mensaje de exclusión en líneas

**Síntoma:** todas las líneas excluidas, o líneas parciales seleccionadas no válidas.

**Qué hacer:** revise productos, variantes, categorías, fabricantes y proveedores excluidos. Ajuste **Exclusion message** para que los clientes entiendan el motivo.

### 5.7 «Withdrawal is not available for your customer account.»

**Síntoma:** formulario o botones ocultos para un cliente conectado.

**Qué hacer:** quite el grupo del cliente de **Excluded customer groups**, o mueva al cliente a un grupo permitido.

### 5.8 «Please enter a message for the customer when changing the status.»

**Síntoma:** falla la actualización de estado en la vista del caso.

**Qué hacer:** rellene **Message to customer**, o desactive **Require message to customer when changing status** si su proceso permite mensajes vacíos.

### 5.9 Correo de confirmación no enviado

**Síntoma:** el caso muestra correo no enviado; el cliente no tiene confirmación duradera.

**Qué hacer:** corrija los ajustes de correo de PrestaShop, revise el spam, use **Resend confirmation email**. Configure **Notification email** para copias al personal. Confirme que funciona el correo de contacto de la tienda.

### 5.10 El invitado no encuentra el pedido

**Síntoma:** **No order found for the given details.** o espera por límite de intentos.

**Qué hacer:** coincida exactamente la referencia del pedido y el correo del pedido. Espere si hay demasiados intentos. Confirme que **Guest access** está activo.

### 5.11 La comprobación de actualizaciones falla o no responde

**Síntoma:** la comprobación manual no informa de una versión.

**Qué hacer:** asegúrese de que curl funciona y el servidor puede alcanzar MyPresta.eu. Desactive el módulo gratuito si Pro está bloqueado. Reintente **Manual Check** en la pestaña **Updates**.

## 6. Para desarrolladores

### 6.1 Resumen

- Nombre técnico: `rbpro`
- Versión: paquete actual 1.7–9 (p. ej. 1.4.6); PrestaShop 1.6 como paquete aparte (p. ej. 1.4.5) con `ps_versions_compliancy` min `1.6.0.0`
- Nombre mostrado: Return Button Pro
- Autor: MyPresta.eu
- Tab: `front_office_features`
- Clase principal: `Rbpro`
- `ps_versions_compliancy` en el paquete 1.7–9: min `1.7.0.0`; en el paquete 1.6: min `1.6.0.0`
- Capa de servicio: `RbpWithdrawalService`; seguridad: `RbpSecurity`; tema/hooks: `RbpCompatibility`; analytics: `RbpStatsService`
- Flujo: claves de configuración → hooks / controladores front → tablas `rbp_withdrawal*` → admin `AdminRbpWithdrawal` → estado/seguimiento/impresión del cliente

### 6.2 Archivos importantes

| Ruta | Función |
|---|---|
| `rbpro.php` | Bootstrap del módulo, install/uninstall, pestañas de configure, hooks, defaults |
| `classes/RbpWithdrawal.php` | Modelo de objeto del caso y estados |
| `classes/RbpWithdrawalService.php` | Elegibilidad, plazos, create/confirm, correos, actualizaciones de estado |
| `classes/RbpSecurity.php` | CSRF, grant de invitado, rate limit, sanitizado de IBAN |
| `classes/RbpCompatibility.php` | Perfil de tema, resolución del hook de pie, URLs de admin, hooks requeridos |
| `controllers/admin/AdminRbpWithdrawalController.php` | Lista y vista del caso |
| `controllers/front/form.php` | Formulario en dos pasos |
| `controllers/front/confirm.php` | Página de éxito |
| `controllers/front/track.php` | Seguimiento público |
| `controllers/front/status.php` | Detalles del caso para el cliente |
| `controllers/front/print.php` | Prueba imprimible |
| `sql/install.sql` | Crea tablas `rbp_*` |
| `sql/uninstall.sql` | Solo comentario — se conservan las tablas |
| `lib/updateChecker.php` | UI de actualización MyPresta (`rbproUpdate`) |
| `views/templates/admin/*` | Dashboard, shell de configure, vista del caso, aviso lateral del pedido |
| `views/templates/front/*` | Formulario, confirm, track, status, print, error |
| `views/templates/hook/*` | Botones de pie/cuenta/pedido (classic / hummingbird) |
| `mails/*` | Plantillas `rbf_withdrawal_customer` / `rbf_withdrawal_admin` |
| `translations/*.php` | Traducciones del paquete |

### 6.3 Controladores

| Controlador | Padre / entrada | Notas |
|---|---|---|
| Configure (`getContent`) | Module Manager | Pestañas `rbp_tab`: `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false; ruta de creación solo lectura; export CSV; descarga de adjuntos |
| Front `form` | Module link | Pasos 1–2; búsqueda de invitado; cookie de borrador |
| Front `confirm` | Module link | Éxito tras el envío |
| Front `track` | Module link | Referencia + correo |
| Front `status` | Module link | Línea temporal + productos |
| Front `print` | Module link | Token HMAC sobre la referencia |

Los permisos siguen la pestaña de administración. Los controladores front requieren el módulo activado para el formulario; el seguimiento respeta `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hooks

Registrados: `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton`; en PS ≥ 1.7.7 también `displayBackOfficeHeader`, `displayAdminOrderSide`.

Ejecutados por el módulo: `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (y hooks relacionados con el estado desde el servicio donde estén definidos).

La salida del pie solo se ejecuta para el nombre de hook resuelto por `RbpCompatibility::getFooterHookName()`.

### 6.5 Overrides

Sin overrides de clase o controlador. La integración con el tema usa solo hooks y plantillas seleccionables.

### 6.6 Base de datos

| Tabla | Contenido |
|---|---|
| `PREFIX_rbp_withdrawal` | Cabecera del caso: tienda, pedido, cliente, referencia, alcance, tipo, estado, IBAN, mensaje, IP, UA, idioma, flags de correo, plazo, fechas |
| `PREFIX_rbp_withdrawal_product` | Líneas seleccionadas y cantidades |
| `PREFIX_rbp_withdrawal_note` | Notas internas del personal |
| `PREFIX_rbp_withdrawal_attachment` | Metadatos de subidas del personal |
| `PREFIX_rbp_withdrawal_history` | Eventos de auditoría |

La desinstalación **no** elimina estas tablas. `ensureDatabase()` crea tablas faltantes y puede migrar desde `rbf_*` cuando las tablas Pro están vacías y las del gratuito tienen filas.

### 6.7 Claves de configuración y traducciones

Defaults de `Rbpro::CONFIG`:

| Clave | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Multidioma (no en el array `CONFIG`, instalados por defaults): `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime: `RBP_ADMIN_FOLDER`. Las preferencias de actualización usan claves del comprobador de MyPresta. La migración del módulo gratuito mapea `RBF_*` → `RBP_*` cuando las claves Pro están vacías.

Traducciones: `translations/{iso}.php`. Las cadenas `desc` de campos viven en `renderConfigurationForm()` mediante `$this->l()`.

Estados: `pending`, `confirmed` (etiqueta Registered), `processing`, `refunded`, `rejected`.

### 6.8 Extensión

Sobrescriba TPL/CSS de hooks en el tema para `modules/rbpro/...` sin editar el módulo. Coloque `{hook h='displayRbproButton'}` para ubicación personalizada del botón. Escuche `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed`. No dependa de overrides: no hay ninguno que cascada.

## 7. Soporte

Página del producto: https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

Ayuda con este módulo de pago: inicie sesión en su cuenta de cliente en mypresta.eu, abra Contact y elija **Support for paid modules**. El formulario requiere login para módulos de pago; tras iniciar sesión, seleccione Return Button Pro en su historial de compras.