---
title: "Microsoft Advertising UET Tag & Conversions API - documentación y manual de usuario"
description: "Configure el seguimiento, verifique los eventos con diagnósticos en vivo y resuelva problemas después de instalar el módulo."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - documentación y manual de usuario"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Microsoft Advertising UET Tag & Conversions API en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Requisitos

Prepare la tienda, la cuenta de Microsoft Advertising y la tarea programada antes de la configuración.

- Utilice PrestaShop 1.7, 8 o 9.
- Utilice PHP 7.1–8.x, según la versión de PHP requerida por su instalación de PrestaShop.
- Habilite las extensiones PHP cURL, JSON, OpenSSL y hash.
- Tener una cuenta de Microsoft Advertising y un ID de etiqueta UET. Obtenga también un token al portador de la API de conversiones para **Conversions API** o **UET + CAPI**.
- Tener acceso a CRON cuando use CAPI, porque su cola debe ejecutarse regularmente.
- Configure un CMP externo o un módulo de cookies antes de convertir **Require marketing / analytics consent** en **Yes**.
- No se requiere ningún otro módulo de PrestaShop. Un módulo de alimentación de Microsoft Merchant Center es opcional y puede ayudar a alinear los ID del catálogo.

## 2. Instalación

1. Abra **Modules > Module Manager**.
2. Haga clic en **Upload a module** y cargue el archivo ZIP.
3. Instale **Microsoft Advertising UET / Conversions API**.
4. Encuéntrelo en **Module Manager** y haga clic en **Configure**.
5. Complete **Setup Wizard** o configure todas las pestañas manualmente.

El módulo no crea un elemento de menú **Catalog** visible. Su punto final de datos es una pestaña administrativa oculta que se utiliza internamente.

La instalación no borra la caché de PrestaShop. Bórrelo en **Advanced Parameters > Performance** solo si los activos antiguos o una pantalla de configuración antigua permanecen visibles.

La desinstalación elimina el registro de eventos del módulo, las reglas de etiquetas múltiples, la cola CAPI, el punto final oculto y las claves de configuración del módulo. Es posible que queden claves del verificador de actualizaciones. La reinstalación comienza con la configuración predeterminada y no restaura eventos o reglas eliminados.

## 3. Configuración y trabajo back-office

Abra **Modules > Module Manager**, busque **Microsoft Advertising UET / Conversions API** y haga clic en **Configure**.

Siga este proceso:

1. Complete **Setup Wizard**.
2. Confirme el canal y las credenciales en **Tracking mode**.
3. Seleccione señales en **Events**.
4. Haga coincidir los ID de productos del evento con su feed en **Catalog IDs**.
5. Configure **Privacy & consent**.
6. Defina el comportamiento de pago y reembolso en **Order lifecycle**.
7. Agregue **Multi-tag rules** solo para credenciales específicas del contexto.
8. Programe la URL CRON mostrada cada 1 a 5 minutos cuando CAPI esté activo.
9. Explore el escaparate y verifique los eventos en **Live Statistics** y **Health & diagnostics**.
10. Confirme los eventos en Microsoft Advertising.

Las capturas de pantalla de este manual provienen de un back office en inglés.

### 3.1 Asistente de configuración

Utilice el asistente para la configuración por primera vez. Le guía a través de **Mode**, **Tag ID**, **CAPI token**, **Test** y **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Mode** | No seleccionado | Elija **UET Tag** para el seguimiento del navegador, **Conversions API** para el seguimiento del servidor o **UET + CAPI** para ambos. El modo dual utiliza un identificador de evento compartido para la deduplicación. |
| **Tag ID** | Vacío | Pegue el ID de Microsoft Advertising en Etiqueta UET o Seguimiento de conversiones. Es necesario en todos los modos. |
| **CAPI token** | Vacío | En CAPI o modo dual, pegue el token de portador de la sección API de conversiones de la etiqueta de UET. Trátelo como una contraseña. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Sí | Recopile identificadores de visitantes anónimos y de clics de Microsoft en modos compatibles con CAPI sin realizar llamadas de seguimiento de UET. Manténgalo habilitado para una mayor coincidencia y continuidad de la sesión. |
| **Test** | No ejecutar | En el modo UET, valide el ID de la etiqueta y luego verifique la vista de la página del escaparate. En modos compatibles con CAPI, haga clic en **Send test purchase** para enviar una compra de prueba por 1 €. Espere entre 10 y 30 minutos para que Microsoft Advertising lo muestre. |
| **Done** | Incompleto | Finalice la configuración y abra los accesos directos a **Tracking mode**, **Health & Data Quality Coach** o **Live Statistics**. |

Utilice **Start over** para ejecutar el asistente nuevamente. Las credenciales existentes permanecen precargadas hasta que se cambien.

### 3.2 Modo de seguimiento y credenciales

Seleccione cómo llegan todos los eventos a Microsoft Advertising, complete los campos que se muestran para ese modo y haga clic en **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Tracking mode** | No seleccionado | **UET Tag** envía desde el navegador. **Conversions API** pone en cola los eventos del servidor. **UET + CAPI** envía ambos con el mismo ID de evento para que Microsoft pueda eliminarlos. |
| **Tag ID(s)** | Vacío | Escriba un ID de etiqueta de UET y presione coma o Intro. La identificación es necesaria para UET, CAPI y modo dual. |
| **Conversions API token** | Vacío | Pegue el token al portador de **Microsoft Advertising > UET tag > Use Conversions API > Copy Token**. |
| **CAPI endpoint override (advanced)** | Vacío | Déjelo vacío para usar el destino estándar de Microsoft. Configúrelo solo cuando Microsoft documente un host personalizado para su cuenta. |
| **Ghost collector (CAPI)** | Sí | Capture `msclkid` y el ID de visitante anónimo para realizar coincidencias CAPI. No llama al seguimiento de UET. |
| **Bing ID Sync (remarketing)** | Sí | Cuando UET esté activo, envíe el ID del visitante anónimo a través de Bing ID Sync para mejorar la coincidencia de la audiencia de remarketing. |

Para CAPI o modo dual, copie el **CRON URL** que se muestra a su programador y ejecútelo cada 1 a 5 minutos.

### 3.3 Eventos

Primero seleccione y guarde un modo de seguimiento. Luego habilite solo las señales que necesita y haga clic en **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **PAGE_VIEW** | Sí | Registre cada carga de la página del escaparate. Admite informes y atribución de tráfico; apagarlo no detiene otros eventos. |
| **view_item (+ select_item)** | Sí | Envíe `view_item` en las páginas de productos y `select_item` cuando se haga clic en un producto en categorías, búsquedas o listas de bestsellers. |
| **view_item_list** | Sí | Envíe aproximadamente los primeros 20 productos de categorías, búsquedas y listas de estilo más vendido con ID, nombres, precios y posiciones. Tiene su propio interruptor. |
| **add_to_cart** | Sí | Registre las adiciones al carrito. UET y el modo dual utilizan el evento de carrito nativo más el respaldo de CSS opcional. El modo solo CAPI utiliza la ruta del servidor y no necesita selectores CSS. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Sí | Registre las eliminaciones del carrito como **Other**, porque Microsoft no tiene un tipo nativo de eliminación del carrito. |
| **CHECKOUT** | Sí | Se activa cuando el cliente ingresa al carrito o al flujo de pedidos y marca la intención de compra. |
| **CHECKOUT details** | Sí | Agregue valor, moneda y datos de productos a **CHECKOUT**. Al apagarlo se envían parámetros mínimos. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Sí | Dispare en el paso de pago como **Other**. Úselo como una señal opcional de embudo tardío para Estadísticas en vivo. |
| **purchase** | Sí | Envíe **OffMicrosoftPurchases** con el valor del pedido, la moneda y las líneas de productos. Un ID de deduplicación de cliente estable hace que las actualizaciones sean seguras. Utilice **Order lifecycle** para retrasarlo hasta el pago. |
| **SEARCH** | Sí | Registre las búsquedas de escaparates con el término de búsqueda. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Sí | Registre las adiciones a la lista de deseos como **Other** cuando el tema exponga controles compatibles. |
| **SIGN_UP (Signup)** | Sí | Envíe **Signup** cuando se cree una cuenta de cliente. |
| **LEAD / SUBSCRIBE (newsletter)** | Sí | Envíe **Lead** para suscribirse al boletín. Deshabilítelo si otra herramienta rastrea la misma conversión. |
| **LEAD (legacy product interest)** | No | Preservar el antiguo comportamiento del líder interesado en el producto. Déjalo así a menos que una campaña histórica lo requiera; usarlo con `view_item` puede inflar los cables. |
| **CONTACT** | Sí | Se activa cuando se envía el formulario de contacto, utilizando la detección de respaldo del servidor y del navegador. |
| **REFUND (Microsoft: Other)** | Sí | Se activa cuando un pedido alcanza un estado de reembolso o cancelación configurado. Microsoft lo recibe como **Other** para corrección y estadísticas locales. |
| **Rich product payloads (productId / items)** | Sí | Incluya ID de productos, cantidades y precios. Al desactivarlo, los datos de valor/moneda son mínimos, excepto cuando los eventos de lista o clic requieren ID. Mantenlo encendido para hacer coincidir el catálogo. |
| **Add to cart CSS selector** | `.add-to-cart` | En UET y modo dual, identifique el botón de la página del producto cuando el tema no activa el evento del carrito nativo. |
| **Product price CSS selector** | `.current-price span` | En UET y modo dual, lea el precio de reserva visible. Un selector incorrecto envía cero; combínelo con **Reformat price string** cuando sea necesario. |

Para CAPI, habilite **Advanced matching (email / phone)** y **Ghost collector (CAPI)** para una mejor coincidencia.

### 3.4 ID de catálogo y Doctor de ID de catálogo

Haga que los ID de productos del evento coincidan exactamente con su fuente de Microsoft Merchant Center, haga clic en **Save** y luego revise **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Product identification** | `id_product` | Elija el ID del producto, el ID de la combinación o el ID del producto más el separador más el ID de la combinación. Los ID combinados se adaptan a los feeds que enumeran variantes. Un formato de feed diferente impide la coincidencia. |
| **Separator** | `-` | Separe los ID de productos y combinaciones en modo combinado. El producto 12 y la combinación 5 se convierten en `12-5`. Utilice el mismo separador en el pienso. |
| **Product ID prefix** | Vacío por idioma | Agregue un valor específico del idioma antes de cada ID solo cuando el feed también lo use. |
| **Product ID suffix** | Vacío por idioma | Agregue un valor específico del idioma después de cada ID solo cuando el feed también lo use. |
| **Exclude free products** | No | Omita los productos de precio cero del carrito y compre líneas de productos y cálculos de valor. |
| **Force currency conversion** | No | Convierta todos los valores monetarios a una moneda de destino. Habilítelo solo cuando Microsoft Advertising no acepte la moneda de la tienda. |
| **Target currency** | Selección dependiente de la tienda | Seleccione la moneda de destino. Se ignora mientras la conversión forzada está desactivada. |
| **Reformat price string** | No | En UET o modo dual, limpie los precios de los temas formateados antes de que el respaldo CSS para agregar al carrito los lea. No se utiliza en modo solo CAPI. |

**Catalog ID Doctor** muestra ejemplos generados a partir de un producto activo y una combinación, ID recientes encontrados en datos de eventos y sugerencias sobre el ID base, separador, prefijo y sufijo seleccionados. Si informa **No active products found to validate catalog productId values**, active un producto y vuelva a abrir la pestaña.

### 3.5 Privacidad y consentimiento

Primero configure una fuente de consentimiento externa. El módulo no muestra un banner de cookies.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Require marketing / analytics consent** | No | Bloquee UET, CAPI y Ghost hasta que se otorgue el consentimiento. Sin un CMP conectado, el seguimiento permanece silencioso. |
| **Default consent state** | `auto` | `auto` espera el consentimiento de cookies, TCF o eventos del navegador; `grant` permite inmediatamente; `revoke` se bloquea hasta que se conceda. Utilice `auto` con un banner y `grant` únicamente con una base legal adecuada. |
| **IAB TCF 2.x (__tcfapi)** | Sí | Escuche a un CMP certificado. El propósito 1 más uno de los propósitos 2, 3 o 4 desbloquea anuncios y actualiza el consentimiento de almacenamiento de publicidad de Microsoft UET. |
| **Include logged-in customer ID** | No | Agregue la identificación del cliente de PrestaShop al contexto y diagnóstico de inicio de sesión como una señal de identificación externa opcional. Infórmalo en la política de privacidad. |
| **Advanced matching (email / phone)** | No | Envíe correo electrónico y campos de correo electrónico/teléfono con hash disponibles para mejorar la atribución de UET y CAPI. Asegúrese de que la política de privacidad cubra esto. Se recomienda encarecidamente para CAPI. |
| **Ignore admin / employee traffic** | Sí | Omita el seguimiento del escaparate cuando se detecte una sesión de empleado. |
| **Simple bot filter** | No | Omita solicitudes cuya identificación del navegador parezca un bot o un rastreador. Esto es heurístico. |

Para una configuración de la UE, configure el CMP, use `auto`, habilite el consentimiento requerido y mantenga habilitado el TCF cuando sea compatible. Pruebe aceptar y rechazar en un navegador privado. La guía reconoce cookies de marketing/estadísticas comunes, su propia cookie de consentimiento y su resultado TCF. Las devoluciones de llamadas de Cookiebot se admiten directamente; otros CMP pueden enviar el evento de consentimiento del módulo.

### 3.6 Ciclo de vida del pedido

Controle cuándo las ventas y los reembolsos ingresan en los informes de conversión.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Purchase only when paid** | No | Retrasar la compra hasta que se pague el estado del pedido. Habilítelo cuando las transferencias bancarias impagas o los pedidos contra reembolso inflen las conversiones. |
| **Paid statuses** | Vacío | Seleccione una lista blanca opcional de estados pagos. Déjelo vacío para usar la bandera de pago incorporada de PrestaShop. Se utiliza una lista completa cuando el seguimiento de pago está activado. |
| **Refund / cancel statuses** | Vacío | Seleccione los estados que activan el reembolso. Vacío utiliza la detección automática de nombres de estados que contienen reembolso o cancelación. El evento Reembolso también debe estar habilitado. |

Para pagos retrasados, habilite el seguimiento solo de pago, mueva un pedido de prueba a un estado pagado y verifique que la compra aparezca una vez.

### 3.7 Reglas de etiquetas múltiples

Utilice reglas cuando una tienda, idioma, país o moneda necesite credenciales diferentes. La primera regla activa coincidente gana en orden ascendente **Position**. Sin coincidencia, se utilizan credenciales globales.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

La lista **Active rules** muestra **Tag ID**, fuente de token CAPI, **Shop**, **Language**, **Country**, **Currency**, **Active** y **Actions**. Haga clic en **Delete** y confirme para eliminar una regla. No hay edición ni acciones masivas; recrear una regla para cambiarla.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Tag ID (UET)** | Vacío | Configure la etiqueta UET para el tráfico coincidente. Puede estar vacío solo para una anulación de CAPI de solo token. |
| **Conversions API token** | Vacío | Anule el token global. Vacío hereda el token de **Tracking mode**. |
| **Shop** | **All shops** | Limite la regla a una tienda multitienda o a todas las tiendas. |
| **Language** | **All languages** | Limítelo a un idioma de escaparate o a todos los idiomas. |
| **Country** | **All countries** | Limitarlo al contexto actual del país-cliente. |
| **Currency** | **All currencies** | Limitarlo a la moneda actual. |
| **Active** | Sí | Habilite o deshabilite la regla. Las reglas inactivas se ignoran. |
| **Position** | `0` | Establecer orden de evaluación. Los números más bajos ganan cuando coinciden varias reglas. |

Haga clic en **Add rule**. **Property rule saved** confirma el éxito. Si aparece **Could not save rule — provide a valid Tag ID and/or Conversions API token.**, corrija el ID de etiqueta o proporcione un token.

### 3.8 Estadísticas en vivo

Abra esta pestaña en una ventana y explore la tienda en otra. Los eventos aparecen en una línea de tiempo de 30 minutos en tiempo real.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** muestra compras sin agregar al carrito, agregar al carrito sin vistas de detalles del producto, reembolsos versus compras y recuperación CAPI/Ghost. Utilice casillas de verificación de eventos para filtrar la línea de tiempo; PageView está oculto de forma predeterminada. **Pause** detiene el sondeo sin detener el seguimiento y **Refresh** recupera los datos actuales.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Enable live dashboard** | Sí | Activa o desactiva el sondeo de la línea de tiempo. Al desactivarlo se detiene la transmisión, mientras continúan el seguimiento y los registros de salud/radar. |
| **Also log PageView into the event database** | No | Agregue filas de PageView ruidosas al registro local. No controla la activación de Microsoft PageView ni otros registros de eventos. Habilite solo para depuración. |
| **Keep events for (days)** | `14` | Purgue las filas que tengan más de esta edad. Los valores aceptados son 1–365; 7-30 es típico. |
| **Live poll interval (seconds)** | `5` | Encuesta cada 2 a 60 segundos. Los valores más bajos son más rápidos pero generan más solicitudes de back-office. |

Utilice **Purge older than retention**, **Delete failed only** o **Clear entire event log** para una limpieza inmediata. Borrar todo requiere confirmación y no se puede deshacer. **Export recent events (CSV)** descarga registros recientes que no son PageView.

### 3.9 Salud y diagnóstico

Utilice esta pestaña después de la configuración y siempre que falten conversiones.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

**Health Score** modo de auditoría, credenciales, actualización de la cola, Ghost, PageView, consentimiento, TCF, compra, deduplicación, errores recientes, formato de catálogo y calidad de los datos. Lea cada verificación fallida, no solo la etiqueta **Excellent**, **Good**, **Fair** o **Needs work**.

Para CAPI, programe **CAPI CRON URL** cada 1 a 5 minutos. Revise **Last CAPI flush**, procesado, enviado, pendiente, fallido, totales de cola y filas con más de 10 minutos.

**Data Quality Coach** estima una cobertura coincidente a partir de cargas útiles de servidor recientes o una muestra de compra actual. Enumera identificadores presentes y faltantes, aumentos esperados, promedios por evento y correcciones a nivel de tienda. Mejore la identificación anónima, `msclkid`, la coincidencia avanzada de correo electrónico/teléfono y la identificación de cliente opcional cuando corresponda. Confirma el diagnóstico final en Microsoft Advertising.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Enable front debug inspector** | No | Muestre una superposición de escaparate flotante con eventos, cargas útiles, destino CAPI, estado de la cola y errores. Apáguelo después de realizar la prueba. Agregue temporalmente `?mybing_debug=1` a la URL de una tienda para habilitarlo sin guardar. |

Bajo **Test & queue**:

- **Send test purchase** envía una conversión de prueba; consulte Microsoft Advertising después de 10 a 30 minutos.
- **Test CAPI token** comprueba que el ID de etiqueta y el token estén presentes.
- **Process CAPI queue** ejecuta la misma ruta de cola que CRON.

**Recent events log** muestra evento, ID, canal, estado, respuesta/error, fecha y resultado. Utilice **Re-send** para un intento inmediato o **Re-add to queue** para la siguiente ejecución CRON.

**Recent queue rows** muestra detalles del evento, estado, intentos, último error y hora de actualización. Utilice acciones por fila o **Re-send all failed now** y **Re-add all failed to queue**.

### 3.10 Actualizaciones

Busque una versión más reciente del módulo aquí.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Manual Check** | Sin resultados | Haga clic en **Check Now** para comunicarse con el servicio de actualización una vez. Muestra **Module is up to date!** o **New version available!**. |
| **Automatic Notifications** | Preferencia de actualización compartida existente | **Enabled** realiza comprobaciones aproximadamente cada tres días y puede advertir a los empleados. **Disabled** deja manual de gestión de actualizaciones. |
| **Product Page** | Enlace mostrado | Abra la página oficial del módulo para obtener información sobre la versión, documentación y acceso a soporte. |

Haga clic en **Save** después de cambiar las notificaciones.

## 4. Escaparate

El módulo no agrega ningún bloque de escaparate, formulario, botón o página de cuenta de cliente visible. Los clientes utilizan las pantallas normales de producto, carrito, pago, registro, boletín informativo, contacto y confirmación.

Las páginas de productos contienen un bloque de datos de productos oculto que se utiliza en el seguimiento. No altera el tema visible. Cuando la depuración está habilitada, se hace visible un inspector flotante; deshabilítelo después de la prueba porque expone detalles de seguimiento.

Para CAPI, copie **CAPI CRON URL** de **Tracking mode** o **Health & diagnostics** en el programador de alojamiento y ejecútelo cada 1 a 5 minutos. La URL protegida procesa eventos en cola y retención. No lo publiques porque contiene una clave de acceso.

El punto final de datos del escaparate se llama automáticamente para dar consentimiento, ID de visitante, carrito, vista de página, pago, contacto y acciones de depuración. No lo construyas ni lo abras manualmente.

| Mensaje visible | Qué hacer |
|---|---|
| El inspector de depuración muestra el consentimiento denegado | Aceptar el consentimiento de marketing a través del CMP o reparar la conexión del CMP. |
| El inspector de depuración muestra en cola | Ejecute CRON o **Process CAPI queue**, luego verifique **Health & diagnostics**. |
| El inspector de depuración muestra un error | Lea la respuesta en **Health & diagnostics**, corrija las credenciales o la conectividad y haga clic en **Re-send**. |

## 5. Problemas

| Síntoma | Causa y acción |
|---|---|
| Asistente sigue incompleto | Guarde un modo válido, una ID de etiqueta y un token cuando corresponda; ejecute **Test** y finalice **Done**. |
| No aparecen eventos de UET | Guarde una ID de etiqueta válida, incluya UET en el modo, habilite el evento, revise el consentimiento y pruebe en una sesión privada del cliente. |
| **Missing Tag ID and/or Conversions API token** | Ingrese ambos en **Tracking mode**, guarde y ejecute **Test CAPI token** nuevamente. |
| Los eventos de CAPI siguen en cola | Programe **CAPI CRON URL** cada 1 a 5 minutos, haga clic en **Process CAPI queue** una vez e inspeccione **Last CAPI flush**. |
| La prueba CAPI o el reenvío fallan | Lea **Response / error**, corrija el ID de etiqueta/token/conectividad, deje la anulación del punto final vacía a menos que Microsoft haya proporcionado una y vuelva a intentarlo. |
| El seguimiento se detiene después de que se requiere el consentimiento | Configure el CMP externo, use `auto`, conecte TCF o sus devoluciones de llamada, luego acepte el consentimiento de marketing y vuelva a realizar la prueba. |
| Los productos del catálogo no coinciden | Alinee **Product identification**, separador, prefijo y sufijo con el feed y revise **Catalog ID Doctor**. |
| Las compras aparecen antes del pago | Habilite **Purchase only when paid** y, opcionalmente, seleccione estados pagados exactos. |
| Los pedidos pagados no generan compra | Habilite **purchase** y asegúrese de que el estado del pedido esté pagado o incluido en **Paid statuses**. |
| No aparecen reembolsos | Habilite Reembolso y seleccione el **Refund / cancel statuses** correcto. |
| Sus pruebas son ignoradas | Utilice un navegador privado sin una sesión de empleado o desactive temporalmente **Ignore admin / employee traffic**. |
| Falta tráfico de prueba tipo bot | Deshabilite **Simple bot filter** para la prueba y luego restáurelo según sea necesario. |
| El complemento al carrito de UET no está disponible | Actualice los selectores CSS de botones y precios para que coincidan con el tema. |
| El valor para agregar al carrito es cero o está mal formado | Corrija el selector de precios y habilite **Reformat price string** cuando sea necesario. |
| Paso de pago Otro evento está ausente aunque su alternancia es Sí | El tema o el paso de pago no activaron la ruta del módulo. Trate esta señal como opcional y verifique el embudo restante. |
| Estadísticas en vivo espera eventos | Habilite el panel, reanúdelo, borre los filtros, haga clic en **Refresh** y explore el escaparate como cliente. |
| PageView llega a Microsoft pero está ausente localmente | Habilite el registro de PageView local temporalmente; está desactivado de forma predeterminada. |
| Se utiliza una credencial de etiquetas múltiples incorrecta | Elimine/recree reglas superpuestas y dé a la más específica la posición más baja. |
| La regla no se puede guardar | Proporcione un ID de etiqueta y/o token válido y luego haga clic en **Add rule**. |
| Sanidad alerta sobre la calidad de los datos | Siga **Highest-impact fixes**, habilite la coincidencia Ghost y Advanced cuando sea legal y recopile datos telefónicos de pago válidos. |
| La pantalla del módulo parece obsoleta | Borre el caché en **Advanced Parameters > Performance** y vuelva a cargar. |

## 6. Referencia del desarrollador

### 6.1 Arquitectura

El nombre técnico es `mybing`, versión `1.4.0`. La clase principal es `mybing extends Module`; El nombre de la lista es **Microsoft Advertising UET / Conversions API**, autor `MyPresta.eu`, categoría `front_office_features`.

`MybingTrackerFactory` selecciona `MybingUetTracker`, `MybingCapiTracker` o `MybingHybridTracker`. `MybingEvents` crea eventos; `MybingEventId` genera y conserva los ID de deduplicación. `MybingProductIdResolver`, `MybingCurrencyHelper` y `MybingUserData` normalizan los datos de identidad, dinero y catálogo. `MybingCapiClient` genera solicitudes, las envía y gestiona los reintentos. Diagnóstico de energía `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach` y `MybingCatalogDoctor`.

El modo dual comparte un ID de evento entre los canales del navegador y del servidor. El punto final predeterminado es `https://capi.uet.microsoft.com/v1/{tagId}/events`. Cada llamada CRON procesa hasta 50 filas de cola y aplica retención.

### 6.2 Archivos y clases

| Archivo o clase | Responsabilidad |
|---|---|
| `mybing.php` | Instalar/desinstalar, valores predeterminados, formularios, acciones, CRON, configuración frontal y ganchos. |
| `classes/MybingTrackerInterface.php` | Contrato de seguimiento. |
| `classes/MybingTrackerFactory.php` | Resolución de cambio de modo y evento. |
| `classes/MybingUetTracker.php` | Cargas útiles del navegador y registros UET locales. |
| `classes/MybingCapiTracker.php` | Entrega de servidores y colas. |
| `classes/MybingHybridTracker.php` | Salida dual y deduplicación. |
| `classes/MybingCapiClient.php` | Cargas útiles, cURL, respuestas, colas, reintentos y resúmenes de vaciado. |
| `classes/MybingEvents.php` | Implementación de eventos comerciales. |
| `classes/MybingEventMap.php` | Mapa de eventos internos de Microsoft. |
| `classes/MybingEventId.php` | ID de eventos, deduplicación y curación de tablas de eventos. |
| `classes/MybingUserData.php` | ID de clics/visitantes, datos de clientes, normalización y hash. |
| `classes/MybingConsent.php` | Requisito de consentimiento, valores predeterminados, cookies y TCF. |
| `classes/MybingPropertyRules.php` | Esquema de reglas de contexto, coincidencia y resolución de credenciales. |
| `classes/MybingProductIdResolver.php` | Generación de ID de catálogo. |
| `classes/MybingCurrencyHelper.php` | Contexto y conversión de divisas. |
| `classes/MybingLiveStats.php` | Feed, resúmenes, radar, retención y limpieza. |
| `classes/MybingHealthScore.php` | Comprobaciones de estado ponderadas y diagnósticos de colas. |
| `classes/MybingDataQualityCoach.php` | Estimaciones de cobertura de identidad. |
| `classes/MybingCatalogDoctor.php` | Identificaciones de producto recientes y de muestra. |
| `controllers/admin/AdminMybingAjaxController.php` | Puente back-office JSON autenticado. |
| `controllers/front/ajax.php` | Punto final JSON de seguimiento protegido por token. |
| `controllers/front/cron.php` | Punto final JSON de cola protegida por clave. |
| `views/js/mybing.js` | Encuadernaciones frontales principales y despacho. |
| `views/js/mybing-tcf.js` | Puente de consentimiento TCF. |
| `views/js/mybing-ghost.js` | Sincronización de visitante/ID de clic. |
| `views/js/mybing-debug.js` | Inspector frontal. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Formularios administrativos, asistente y panel en vivo. |
| `views/templates/hook/header.tpl` | UET, consentimiento, coincidencia, vista de página, eventos, secuencia de comandos y sincronización de ID. |
| `views/templates/hook/product-details.tpl` | Producto oculto JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Salida de compra del navegador. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | Vista de página CAPI, Ghost y salida del inspector. |
| `views/templates/hook/payment.tpl` | Plantilla de evento de pago no invocada por un controlador de gancho en 1.4.0. |
| `sql/install.php`, `sql/uninstall.php` | Crear/curar y soltar tablas personalizadas. |
| `lib/updateChecker.php` | Comprobaciones de actualizaciones manuales y periódicas. |

### 6.3 Controladores

`AdminMybingAjaxController extends ModuleAdminController` se instala como pestaña oculta `AdminMybingAjax` con el padre `-1`. Requiere un empleado y emite JSON. Acciones: `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport` y `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` es SSL y JSON únicamente. Acepta la clave segura o el token frontal generado. Acciones: `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping` y `inspect` de solo depuración. Los errores incluyen `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off` y `unknown_action`.

`MybingCronModuleFrontController` acepta `key` o `secure_key`, devuelve JSON, emite HTTP 403 con `access_denied` para acceso no válido y llama a `runCapiCron()`.

`controllers/front/index.php` solo envía encabezados sin caché y redirecciona hacia arriba.

### 6.4 Ganchos

| Gancho registrado | Implementación |
|---|---|
| `displayHeader` | Filtra el tráfico; envía señales de página, lista, producto, pago, búsqueda, contacto y boletín informativo; genera salida UET/Ghost/CAPI. |
| `displayOrderConfirmation` | Resuelve el pedido, rastrea la compra permitida y muestra la salida del navegador. |
| `actionValidateOrder` | Realiza un seguimiento de la compra en el momento de la creación, a menos que el pago solo la retrase. |
| `actionOrderStatusPostUpdate` | Realiza un seguimiento de las transiciones de compras pagadas retrasadas y reembolsos/cancelación. |
| `actionCustomerAccountAdd` | Realiza un seguimiento del registro y almacena los resultados del navegador para la página siguiente. |
| `actionFrontControllerSetMedia` | Agrega configuración frontal y activos principales, TCF, Ghost y de depuración. |
| `displayPaymentTop` | Registrado, pero `hookDisplayPaymentTop()` no está implementado en 1.4.0. |
| `displayFooter` | Representa el inspector de depuración y el arranque de cola cuando está habilitado. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Realice un seguimiento de los cambios en la cantidad del carrito del servidor; el último delega en el primero. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Realice una instantánea y luego realice un seguimiento de la eliminación completa de la línea del carrito. |
| `displayProductAdditionalInfo` | Muestra detalles ocultos del producto. |
| `actionNewsletterRegistrationAfter` | Realiza un seguimiento del cliente potencial del boletín. |
| `displayContactContent` | Agrega el marcador de contacto oculto. |

No existen métodos personalizados `enable()` o `disable()`.

### 6.5 Base de datos

El prefijo PrestaShop real reemplaza a `ps_`.

| Mesa | Contenidos |
|---|---|
| `ps_mybing_events` | Nombre/ID del evento, pedido/carrito/tienda, canal, carga útil, estado, código HTTP, respuesta, fecha, índices de búsqueda y clave única de deduplicación de evento/nombre/tienda. |
| `ps_mybing_properties` | Selectores de etiqueta, token, tienda/idioma/país/moneda, activo, posición y fecha. |
| `ps_mybing_queue` | Carga útil, intentos, estado, último error, fechas de creación/actualización. |

Se reintenta la instalación con `utf8` si falla `utf8mb4`. `MybingPropertyRules::ensureSchema()` puede agregar `tag_id` y `access_token` cuando se abre la configuración y migrar un token de actualización heredado. El esquema de eventos agrega suavemente su índice único. La desinstalación elimina las tres tablas.

### 6.6 Teclas de configuración

| Claves | Valores predeterminados y finalidad |
|---|---|
| `MYBING_MODE` | Vacío; modo rastreador. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Vacío; credenciales/destino globales. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1`; vida útil de ID de clic y sincronización de ID. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | Todos `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | Todos `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | Todos `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, vacío por idioma, vacío por idioma. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | ID de estado vacíos separados por comas. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Diagnóstico de instalación en tiempo de ejecución. |
| `MYBING_LAST_FLUSH` | Resumen de descarga de JSON en tiempo de ejecución; no en la lista de claves de desinstalación. |

La instalación/desinstalación también elimina los modelos heredados `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS` y `MYBING_ADS_ID`. `MYBING_DEBUG_MODE` se elimina durante la instalación pero no aparece en la lista de desinstalación.

El actualizador utiliza `mypresta_updates`, `update_mybing` y `updatev_mybing`; Estos pueden permanecer después de la desinstalación. `mypresta_updates` se comparte.

### 6.7 Desinstalación, traducciones y extensión

`uninstall()` elimina la pestaña oculta, descarta todas las tablas de módulos, elimina los valores de `getConfigurationKeys()` y los diagnósticos de instalación y luego llama a `parent::uninstall()`. No elimina las claves de actualización ni `MYBING_LAST_FLUSH`.

No hay anulaciones de PrestaShop. Las traducciones se encuentran en `translations/{iso}.php`; la mayoría de las cadenas de UI usan `$this->l()` o Smarty `{l}`, mientras que los nombres de eventos y algunos diagnósticos de clases permanecen en inglés.

Los temas pueden reposicionar los ganchos compatibles y diseñar el inspector, pero el bloque de producto está oculto intencionalmente. Conserve los atributos de datos y los scripts al anular las plantillas de enlace. Un CMP personalizado puede enviar `mybing.consent` con la concesión `1` o `0`, o proporcionar una señal reconocida por `MybingConsent`.

## 7. Ayuda

Abra la página del módulo: https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Inicie sesión en su cuenta de cliente en mypresta.eu, abra la página de contacto y elija **Support for paid modules**. Es necesario iniciar sesión; luego seleccione este módulo de su historial de compras e incluya el modo de seguimiento, el error visible y el resultado del diagnóstico.
