---
title: "Píxel de seguimiento de conversiones de Fb - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Píxel de seguimiento de conversiones de Fb' de MyPresta.eu."
sidebar:
  label: "Píxel de seguimiento de conversiones de Fb - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Fb conversion tracking pixel en MyPresta.eu](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Píxel de seguimiento de conversiones de Fb

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL para que el módulo funcione correctamente, especialmente para las funciones de la API de Conversiones (CAPI). Estas suelen estar disponibles en todos los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, aterrizará en la página de configuración principal. Aquí es donde conectará su tienda a Facebook y personalizará cómo se rastrean los eventos.

#### Pestaña de Configuración General

-   **ID(s) de Píxel:**

    -   **Qué hace este ajuste:** Este es el identificador único de su Píxel de Facebook. Puede encontrarlo en su Administrador Comercial de Facebook o en el Administrador de Eventos. Puede introducir múltiples ID de Píxel separados por comas si gestiona varios píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está lleno:* El módulo incrustará el código del Píxel de Facebook en el front office de su tienda, enviando datos a los ID de Píxel especificados.
        -   *Cuando está vacío:* No se realizará ningún seguimiento del Píxel de Facebook.
    -   **Valor recomendado:** Su ID de Píxel de Facebook principal.
    -   **Escenario / ejemplo de comerciante:** Tiene un píxel principal para su marca y un píxel secundario para una línea de productos específica. Introduzca ambos aquí: `1234567890,9876543210`.
-   **Token de acceso CAPI:**

    -   **Qué hace este ajuste:** Este token habilita la API de Conversiones de Facebook (CAPI), que envía datos de conversión directamente desde su servidor a Facebook, evitando las limitaciones del navegador (como bloqueadores de anuncios o restricciones de cookies). Esto mejora la precisión de los datos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está lleno:* El módulo intentará enviar eventos del lado del servidor a Facebook usando CAPI, además de o en lugar de los eventos del píxel del lado del navegador, dependiendo de sus otros ajustes.
        -   *Cuando está vacío:* Solo se realizará el seguimiento del píxel del lado del navegador (si el ID del píxel está configurado).
    -   **Valor recomendado:** Muy recomendable usar CAPI para una mejor precisión de los datos. Genere este token en su Administrador de Eventos de Facebook.
    -   **Escenario / ejemplo de comerciante:** Desea garantizar la máxima precisión de los datos para sus eventos de compra, incluso si los clientes usan bloqueadores de anuncios. Genera un token de acceso en el Administrador de Eventos de Facebook y lo pega aquí.
-   **Código de evento de prueba:**

    -   **Qué hace este ajuste:** Este código se utiliza para probar su configuración de CAPI en el Administrador de Eventos de Facebook. Cuando se introduce, el módulo enviará eventos de prueba, lo que le permitirá verificar que su seguimiento del lado del servidor funciona correctamente.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está lleno:* Los eventos CAPI incluirán este código de prueba, haciéndolos visibles en la pestaña "Eventos de prueba" del Administrador de Eventos de Facebook.
        -   *Cuando está vacío:* Los eventos CAPI se enviarán como eventos en vivo.
    -   **Valor recomendado:** Úselo solo cuando esté probando activamente su configuración de CAPI. Elimínelo una vez que la prueba haya finalizado.
    -   **Escenario / ejemplo de comerciante:** Acaba de configurar CAPI y desea confirmar que está enviando datos. Copia el código de prueba del Administrador de Eventos de Facebook, lo pega aquí, realiza una compra de prueba en su sitio y luego verifica la pestaña "Eventos de prueba" en Facebook.
-   **Modo de consentimiento:**

    -   **Qué hace este ajuste:** Esta opción se integra con la solución de consentimiento de cookies de su tienda (por ejemplo, módulos GDPR). Determina si los eventos del Píxel de Facebook se activan solo después de que un cliente haya dado su consentimiento.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los eventos del píxel solo se activarán si el cliente ha aceptado las cookies.
        -   *Cuando está deshabilitado:* Los eventos del píxel se activarán independientemente del consentimiento de las cookies (úselo con precaución, dependiendo de las leyes de privacidad locales).
    -   **Valor recomendado:** "Sí" si opera en regiones con leyes de privacidad estrictas (como el GDPR en Europa).
    -   **Escenario / ejemplo de comerciante:** Su tienda se dirige a clientes de la UE. Habilita este ajuste para cumplir con el GDPR, asegurando que los datos del píxel solo se recopilen de usuarios que aceptan explícitamente el uso de cookies.
-   **Estados pagados:**

    -   **Qué hace este ajuste:** Selecciona qué estados de pedido en PrestaShop deben activar un evento "Purchase" en Facebook. Típicamente, esto incluye estados como "Pago aceptado" o "Entregado".
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* Los pedidos que alcanzan estos estados enviarán un evento "Purchase" a Facebook.
        -   *Cuando no está seleccionado:* Los pedidos no enviarán un evento "Purchase" cuando alcancen estos estados.
    -   **Valor recomendado:** Seleccione todos los estados que representen genuinamente un pedido completado y pagado.
    -   **Escenario / ejemplo de comerciante:** Considera un pedido "pagado" cuando está "Pago aceptado" y "Enviado". Selecciona ambos estados.
-   **Estados de reembolso / cancelación:**

    -   **Qué hace este ajuste:** Selecciona qué estados de pedido indican un reembolso o cancelación. Esto permite que el módulo envíe potencialmente un evento "Refund" o "Cancel" (si es compatible con la API de Facebook y la versión del módulo) o para evitar un seguimiento de compra falso positivo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está seleccionado:* El módulo reconocerá estos pedidos como no compra o reembolsados.
        -   *Cuando no está seleccionado:* Estos pedidos aún podrían contarse como compras si previamente alcanzaron un "Estado pagado".
    -   **Valor recomendado:** Seleccione estados como "Cancelado", "Reembolsado", "Error de pago".
    -   **Escenario / ejemplo de comerciante:** Un cliente cancela un pedido. Desea asegurarse de que esto no se cuente como una compra exitosa. Selecciona "Cancelado" y "Reembolsado" aquí.

#### Pestaña de Configuración Avanzada

-   **Selector CSS de añadir al carrito:**

    -   **Qué hace este ajuste:** Es una configuración técnica que ayuda al módulo a identificar el botón "Añadir al carrito" en las páginas de sus productos. Si su tema utiliza un botón no estándar, es posible que deba especificar su selector CSS.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando es correcto:* El evento "AddToCart" se activará de forma fiable cuando un cliente haga clic en el botón.
        -   *Cuando es incorrecto o está vacío (y la autodetección falla):* El evento "AddToCart" podría no activarse, lo que provocaría la pérdida de datos.
    -   **Valor recomendado:** Déjelo vacío primero; el módulo a menudo lo detecta automáticamente. Si faltan eventos "AddToCart", consulte a su desarrollador de temas o utilice el inspector de su navegador para encontrar el selector CSS correcto (por ejemplo, `.add-to-cart-button`).
    -   **Escenario / ejemplo de comerciante:** Su tema personalizado tiene un botón "Añadir al carrito" único. Inspecciona el botón en su navegador y encuentra que su clase es `my-custom-add-button`. Introduce `.my-custom-add-button` aquí.
-   **Selector CSS de precio del producto:**

    -   **Qué hace este ajuste:** Similar al selector de Añadir al carrito, esto ayuda al módulo a encontrar con precisión el precio del producto en la página, especialmente para precios dinámicos o diseños de temas específicos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando es correcto:* El parámetro "value" para eventos como "ViewContent" y "AddToCart" reflejará con precisión el precio del producto.
        -   *Cuando es incorrecto o está vacío (y la autodetección falla):* El parámetro "value" podría faltar o ser incorrecto, lo que afectaría la optimización de los anuncios.
    -   **Valor recomendado:** Déjelo vacío primero. Si los valores de precio son incorrectos en el Administrador de Eventos de Facebook, encuentre el selector CSS correcto (por ejemplo, `.current-price span[itemprop="price"]`).
    -   **Escenario / ejemplo de comerciante:** La página de su producto muestra los precios de una manera no estándar. Identifica el selector CSS para el elemento de precio para asegurarse de que Facebook reciba el valor correcto.
-   **Identificación del producto:**

    -   **Qué hace este ajuste:** Determina qué identificador de producto (ID) envía su tienda a Facebook. Las opciones suelen incluir `ID` (ID interno del producto de PrestaShop), `Reference` (SKU de su producto) o `EAN13` / `UPC` (números de código de barras). Esto es crucial para hacer coincidir productos en su Catálogo de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* Facebook recibirá el tipo de ID elegido, que debe coincidir con los ID de su Catálogo de productos de Facebook para que los anuncios dinámicos funcionen.
        -   *Cuando no coincide con su catálogo:* Es posible que los anuncios dinámicos no muestren los productos correctos o que no se muestren en absoluto.
    -   **Valor recomendado:** Elija el ID que utiliza de forma consistente en su Catálogo de productos de Facebook. `Reference` (SKU) suele ser una buena opción si es único.
    -   **Escenario / ejemplo de comerciante:** Su Catálogo de productos de Facebook utiliza el SKU de su producto como identificador único. Selecciona "Reference" aquí para garantizar una coincidencia perfecta.
-   **Separador:**

    -   **Qué hace este ajuste:** Si utiliza una combinación de ID de producto e ID de atributo (por ejemplo, para diferentes tamaños/colores), esto define el carácter utilizado para separarlos en el ID de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* El ID de producto enviado a Facebook será `IDProducto` + `Separador` + `IDAtributo`.
        -   *Cuando está vacío:* Solo se podría enviar el ID de producto base, lo que podría causar problemas con el seguimiento de variaciones de producto específicas.
    -   **Valor recomendado:** Un separador común como `-` o `_`.
    -   **Escenario / ejemplo de comerciante:** Vende una camiseta (ID 123) en diferentes tallas (ID de atributo 10 para S, 11 para M). Si establece el separador en `-`, Facebook recibirá `123-10` para una camiseta pequeña.
-   **Prefijo de ID de producto / Sufijo de ID de producto:**

    -   **Qué hace este ajuste:** Le permite añadir texto antes o después del ID de producto enviado a Facebook. Esto es útil si los ID de su Catálogo de productos de Facebook tienen un formato específico que difiere de los ID de su PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* El ID de producto final enviado a Facebook será `Prefijo` + `IDProducto` + `Sufijo`.
        -   *Cuando está vacío:* Solo se envía el ID de producto sin procesar (y el ID de separador/atributo si corresponde).
    -   **Valor recomendado:** Déjelo vacío a menos que su Catálogo de productos de Facebook lo requiera.
    -   **Escenario / ejemplo de comerciante:** Su Catálogo de productos de Facebook requiere que todos los ID de producto comiencen con "PS_". Introduce `PS_` en el campo "Prefijo de ID de producto".
-   **Moneda objetivo:**

    -   **Qué hace este ajuste:** Especifica la moneda en la que se envían los valores de los eventos (como el importe de la compra) a Facebook. Esto es crucial para una elaboración de informes y optimización de anuncios precisas, especialmente para tiendas multimoneda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* Todos los valores de los eventos se convertirán y se enviarán en esta moneda objetivo.
        -   *Cuando está vacío:* El módulo intentará utilizar la moneda del contexto de la tienda actual o la moneda seleccionada por el cliente.
    -   **Valor recomendado:** Su moneda publicitaria principal (por ejemplo, USD, EUR).
    -   **Escenario / ejemplo de comerciante:** Su tienda vende en EUR, USD y GBP, pero todos sus anuncios de Facebook se gestionan en USD. Establece "Moneda objetivo" en "USD" para asegurarse de que todos los valores de conversión se informen de forma consistente en USD.

#### Pestaña de Configuración de Seguimiento de Eventos

Esta sección le permite habilitar o deshabilitar eventos específicos del Píxel de Facebook. Habilite solo los eventos que desea rastrear activamente.

-   **Evento Pageview:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente ve cualquier página de su sitio web.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `PageView` en cada carga de página.
        -   *Cuando está deshabilitado:* No se envían eventos `PageView`.
    -   **Valor recomendado:** Sí. Este es un evento fundamental para todo el seguimiento.
-   **Evento Purchase:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente completa una compra. Este es el evento de conversión más crítico.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `Purchase` en la página de confirmación del pedido y/o a través de CAPI cuando un pedido alcanza un "Estado pagado".
        -   *Cuando está deshabilitado:* No se envían eventos `Purchase`.
    -   **Valor recomendado:** Sí. Absolutamente esencial para la publicidad de comercio electrónico.
-   **Evento ViewContent:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente ve la página de un producto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `ViewContent` cuando se carga la página de un producto.
        -   *Cuando está deshabilitado:* No se envían eventos `ViewContent`.
    -   **Valor recomendado:** Sí. Importante para anuncios de productos dinámicos y remarketing.
-   **Evento AddToCart:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente añade un artículo a su carrito de compras.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `AddToCart` cuando se añade un artículo al carrito.
        -   *Cuando está deshabilitado:* No se envían eventos `AddToCart`.
    -   **Valor recomendado:** Sí. Crucial para campañas de recuperación de carritos abandonados.
-   **Evento RemoveFromCart:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente elimina un artículo de su carrito de compras.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `RemoveFromCart` cuando se elimina un artículo.
        -   *Cuando está deshabilitado:* No se envían eventos `RemoveFromCart`.
    -   **Valor recomendado:** Sí. Puede proporcionar información sobre el comportamiento del cliente y el interés en el producto.
-   **Evento InitiateCheckout:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente inicia el proceso de pago.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `InitiateCheckout` cuando el cliente entra en el primer paso del pago.
        -   *Cuando está deshabilitado:* No se envían eventos `InitiateCheckout`.
    -   **Valor recomendado:** Sí. Útil para comprender el rendimiento del embudo de pago.
-   **Evento Search:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente utiliza la función de búsqueda interna de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `Search` con la consulta de búsqueda.
        -   *Cuando está deshabilitado:* No se envían eventos `Search`.
    -   **Valor recomendado:** Sí. Proporciona datos valiosos sobre lo que buscan los clientes.
-   **Evento AddToWishlist:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente añade un producto a su lista de deseos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `AddToWishlist`.
        -   *Cuando está deshabilitado:* No se envían eventos `AddToWishlist`.
    -   **Valor recomendado:** Sí, si su tienda utiliza una función de lista de deseos.
-   **Evento AddPaymentInfo:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente selecciona un método de pago durante el proceso de pago.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `AddPaymentInfo`.
        -   *Cuando está deshabilitado:* No se envían eventos `AddPaymentInfo`.
    -   **Valor recomendado:** Sí. Ayuda a analizar las preferencias de métodos de pago y las posibles abandonos.
-   **Evento Contact:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente visita su página de contacto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `Contact`.
        -   *Cuando está deshabilitado:* No se envían eventos `Contact`.
    -   **Valor recomendado:** Sí. Útil para rastrear consultas de servicio al cliente.
-   **Evento Lead:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente realiza una acción que indica interés en sus productos o servicios, pero no es una compra directa (por ejemplo, suscripción a un boletín, creación de cuenta).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `Lead` al registrarse en el boletín y/o al crear una cuenta.
        -   *Cuando está deshabilitado:* No se envían eventos `Lead`.
    -   **Valor recomendado:** Sí. Importante para campañas de generación de leads.
-   **Evento CompleteRegistration:**

    -   **Qué hace este ajuste:** Rastrea cuando un cliente crea una cuenta con éxito en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se envía un evento `CompleteRegistration`.
        -   *Cuando está deshabilitado:* No se envían eventos `CompleteRegistration`.
    -   **Valor recomendado:** Sí. Útil para rastrear la adquisición de nuevos clientes.

#### Pestaña de Estadísticas en Vivo

Esta pestaña proporciona información en tiempo real sobre los eventos que se envían desde su tienda a Facebook, lo que le ayuda a supervisar el estado de su píxel.

-   **Mantener eventos durante (días):**

    -   **Qué hace este ajuste:** Determina cuánto tiempo el módulo almacena los datos de eventos localmente para mostrarlos en la pestaña de Estadísticas en Vivo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* Los datos de eventos con más de este número de días se purgarán automáticamente.
        -   *Cuando se establece en 0:* Los eventos no se almacenan localmente (y las Estadísticas en Vivo no mostrarán datos).
    -   **Valor recomendado:** 7-30 días, dependiendo de cuántos datos históricos desee revisar.
    -   **Escenario / ejemplo de comerciante:** Desea revisar los eventos de la última semana. Lo establece en `7`.
-   **Intervalo de sondeo en vivo (segundos):**

    -   **Qué hace este ajuste:** Controla la frecuencia con la que la pestaña de Estadísticas en Vivo se actualiza para mostrar nuevos eventos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* La tabla de Estadísticas en Vivo se actualizará cada X segundos.
        -   *Cuando se establece en 0:* Las Estadísticas en Vivo no se actualizarán automáticamente.
    -   **Valor recomendado:** 5-10 segundos para una monitorización activa.
    -   **Escenario / ejemplo de comerciante:** Está probando activamente su píxel y desea ver los eventos aparecer casi instantáneamente. Lo establece en `5`.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración General | ID(s) de Píxel | Su ID de Píxel de Facebook | Conecta su tienda al Píxel de Facebook para el seguimiento. |
| Configuración General | Token de acceso CAPI | Su Token de acceso CAPI | Habilita el seguimiento del lado del servidor para mejorar la precisión de los datos. |
| Configuración General | Código de evento de prueba | Vacío (usar solo para pruebas) | Envía eventos de prueba al Administrador de Eventos de Facebook. |
| Configuración General | Modo de consentimiento | Sí (para cumplimiento GDPR) | Activa los eventos del píxel solo después del consentimiento del cliente. |
| Configuración General | Estados pagados | Pago aceptado, Entregado | Define qué estados de pedido activan un evento "Purchase". |
| Configuración General | Estados de reembolso / cancelación | Cancelado, Reembolsado | Define qué estados de pedido se consideran no compra. |
| Configuración Avanzada | Selector CSS de añadir al carrito | Vacío (autodetección) | Ayuda a identificar el botón "Añadir al carrito" para el seguimiento. |
| Configuración Avanzada | Selector CSS de precio del producto | Vacío (autodetección) | Ayuda a identificar el precio del producto para los valores de los eventos. |
| Configuración Avanzada | Identificación del producto | Referencia (SKU) | Determina qué ID de producto se envía a Facebook. |
| Configuración Avanzada | Separador | - (guion) | Separador para ID de producto e ID de atributo. |
| Configuración Avanzada | Prefijo de ID de producto | Vacío | Añade un prefijo al ID de producto enviado a Facebook. |
| Configuración Avanzada | Sufijo de ID de producto | Vacío | Añade un sufijo al ID de producto enviado a Facebook. |
| Configuración Avanzada | Moneda objetivo | Su moneda publicitaria principal | Convierte los valores de los eventos a una moneda específica. |
| Seguimiento de Eventos | Evento Pageview | Sí | Rastrea todas las vistas de página. |
| Seguimiento de Eventos | Evento Purchase | Sí | Rastrea las compras completadas. |
| Seguimiento de Eventos | Evento ViewContent | Sí | Rastrea las vistas de página de producto. |
| Seguimiento de Eventos | Evento AddToCart | Sí | Rastrea los artículos añadidos al carrito. |
| Seguimiento de Eventos | Evento RemoveFromCart | Sí | Rastrea los artículos eliminados del carrito. |
| Seguimiento de Eventos | Evento InitiateCheckout | Sí | Rastrea el inicio del pago. |
| Seguimiento de Eventos | Evento Search | Sí | Rastrea las búsquedas internas del sitio. |
| Seguimiento de Eventos | Evento AddToWishlist | Sí (si se usa la lista de deseos) | Rastrea los artículos añadidos a la lista de deseos. |
| Seguimiento de Eventos | Evento AddPaymentInfo | Sí | Rastrea la información de pago añadida durante el pago. |
| Seguimiento de Eventos | Evento Contact | Sí | Rastrea las visitas a la página de contacto. |
| Seguimiento de Eventos | Evento Lead | Sí | Rastrea las suscripciones a boletines/creaciones de cuentas. |
| Seguimiento de Eventos | Evento CompleteRegistration | Sí | Rastrea los registros de cuenta exitosos. |
| Estadísticas en Vivo | Mantener eventos durante (días) | 7-30 | Período de retención para datos de eventos locales. |
| Estadísticas en Vivo | Intervalo de sondeo en vivo (segundos) | 5-10 | Frecuencia de actualización para la visualización de Estadísticas en Vivo. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminFbpixelAjaxController (Back Office > Módulos > Píxel de seguimiento de conversiones de Fb > Pestaña Estadísticas en vivo)

Este controlador alimenta la pestaña "Estadísticas en vivo" dentro de la configuración del módulo. No tiene un elemento de menú separado, pero es una parte integral de la interfaz de configuración del módulo.

-   **Nombre de la pantalla y ubicación del menú:** Se accede a través de **Módulos > Gestor de módulos > Píxel de seguimiento de conversiones de Fb > Configurar**, luego haga clic en la pestaña **"Estadísticas en vivo"**.
-   **Acciones y configuraciones disponibles:** Esta pantalla muestra una cuadrícula o tabla de los eventos recientes del Píxel de Facebook que se han activado desde su tienda. Muestra detalles como el nombre del evento (por ejemplo, `PageView`, `AddToCart`, `Purchase`), la marca de tiempo, el ID del píxel asociado y, a menudo, los parámetros enviados con el evento (por ejemplo, ID del producto, valor, moneda).
-   **Efecto de los cambios:** No hay "configuraciones" directas para cambiar en esta pantalla. Es una herramienta de monitoreo. Los datos mostrados están influenciados por las configuraciones "Mantener eventos durante (días)" e "Intervalo de sondeo en vivo (segundos)" en la misma página de configuración.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente esta pestaña, especialmente después de realizar cambios en su tienda o lanzar nuevos productos, para asegurarse de que su Píxel de Facebook se esté activando correctamente y enviando datos precisos. Esta es su primera línea de defensa para solucionar problemas del píxel antes de verificar el Administrador de eventos de Facebook.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mi extensión de Chrome Facebook Pixel Helper no muestra ningún píxel o errores. ¿Qué debo hacer?**

-   **R:** Primero, asegúrese de haber introducido sus "ID(s) de Píxel" correctamente en la configuración del módulo.
-   **R:** Compruebe si el "Modo de consentimiento" está habilitado. Si es así, es posible que deba aceptar las cookies en su tienda para que el píxel se active.
-   **R:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).
-   **R:** Si está utilizando un tema personalizado, podría haber conflictos. Cambie temporalmente al tema predeterminado de PrestaShop para descartar esto.
-   **R:** Utilice la herramienta "Eventos de prueba" de Facebook en el Administrador de eventos para ver si se están recibiendo eventos.

**P2: Mis eventos de compra no aparecen correctamente en el Administrador de eventos de Facebook.**

-   **R:** Verifique que sus "Estados pagados" estén seleccionados correctamente en la configuración del módulo. Solo los pedidos que alcancen estos estados activarán un evento de compra.
-   **R:** Si utiliza CAPI, asegúrese de que su "Token de acceso CAPI" sea correcto y pruébelo utilizando la función "Código de evento de prueba".
-   **R:** Compruebe si su "Moneda objetivo" está configurada correctamente, especialmente para tiendas multimoneda.
-   **R:** Revise la pestaña "Estadísticas en vivo" en la configuración del módulo para ver si el módulo está registrando internamente los eventos de compra.

**P3: Los anuncios de productos dinámicos no muestran los productos correctos o no muestran ningún producto.**

-   **R:** La razón más común es una falta de coincidencia entre la configuración de "Identificación del producto" en el módulo y los ID de su Catálogo de productos de Facebook. Asegúrese de que sean idénticos (por ejemplo, si su catálogo utiliza SKU, configure el módulo en "Referencia").
-   **R:** Asegúrese de que su Catálogo de productos de Facebook esté actualizado y libre de errores.
-   **R:** Verifique que los eventos "ViewContent" y "AddToCart" se estén activando correctamente con el parámetro `content_ids` que coincida con los ID de su catálogo.

**Q4: ¿Cómo garantizo el cumplimiento del GDPR u otras normativas de privacidad con este módulo?**

-   **R:** Habilite la configuración "Modo de consentimiento" en el módulo. Esto se integrará con su módulo de consentimiento de cookies existente (si está configurado correctamente) para activar el píxel solo después del consentimiento explícito del usuario.
-   **R:** Asegúrese de que la política de privacidad de su tienda establezca claramente que utiliza el Píxel de Facebook para publicidad y análisis, y cómo los usuarios pueden optar por no participar o administrar sus preferencias de cookies.

**P5: El evento "Añadir al carrito" no se activa en la página de mi producto.**

-   **R:** Es posible que su tema tenga un botón "Añadir al carrito" personalizado que el módulo no pueda detectar automáticamente. Intente inspeccionar el botón "Añadir al carrito" en la página de su producto utilizando las herramientas de desarrollador de su navegador (clic derecho > Inspeccionar) para encontrar su clase o ID CSS. Luego, introduzca esto en el campo "Selector CSS de añadir al carrito" en la configuración del módulo (por ejemplo, `.my-custom-atc-button` o `#add_to_cart_button`).

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Fb conversion tracking pixel` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los hooks para la inyección de eventos en el front-office y un AdminController para las interacciones AJAX en el back-office (Estadísticas en vivo). Se basa en gran medida en un patrón de fábrica (`FbpixelTrackerFactory`) para gestionar diferentes mecanismos de seguimiento (píxel del lado del navegador, CAPI del lado del servidor). Los datos de los eventos se recopilan y procesan mediante clases dedicadas (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`) y luego se envían. La configuración se almacena en `ps_configuration`. El módulo también incluye herramientas robustas para la depuración y las comprobaciones de estado.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nombre de la clase:** `FbpixelAjaxModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Maneja las solicitudes AJAX del front-office, principalmente para recopilar y registrar datos de eventos en tiempo real para la función de Estadísticas en vivo. También podría usarse para activadores de eventos específicos que no pueden manejarse puramente del lado del cliente (por ejemplo, `RemoveFromCart` después de una actualización del carrito).
    -   `controllers/front/cron.php`
        -   **Nombre de la clase:** `FbpixelCronModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Diseñado para ser llamado por un trabajo cron. Este controlador es probablemente responsable de procesar eventos CAPI en cola, realizar la limpieza de datos (por ejemplo, purgar entradas antiguas de Estadísticas en vivo) u otras tareas programadas.
    -   `controllers/front/index.php`
        -   **Nombre de la clase:** `FbpixelIndexModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Un controlador de marcador de posición o de reserva, a menudo utilizado para evitar la lista de directorios o proporcionar una respuesta predeterminada para rutas específicas del módulo.
    -   `controllers/front/sync.php`
        -   **Nombre de la clase:** `FbpixelSyncModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Potencialmente maneja tareas de sincronización, como enviar actualizaciones del catálogo de productos u otros datos a Facebook, o recibir datos de Facebook.
-   **Controladores de administración del Back-Office**:

    -   `controllers/admin/AdminFbpixelAjaxController.php`
        -   **Nombre de la clase:** `AdminFbpixelAjaxController` (extiende `ModuleAdminController`)
        -   **Nombre de la pestaña:** No es una pestaña independiente, sino que está integrada en la configuración del módulo.
        -   **Entidad gestionada:** Gestiona las solicitudes AJAX de la página de configuración del back-office del módulo, específicamente para obtener y mostrar los datos de eventos de las "Estadísticas en vivo". Proporciona los datos para la plantilla `recent-events.tpl`.

### 4.3 Clases y modelos principales (`classes/`)

-   `fbpixel/classes/autoload.php`: Maneja la carga de clases personalizadas para el módulo.
-   `fbpixel/classes/FbpixelCapiClient.php`:
    -   **Responsabilidad:** Encapsula la lógica para realizar solicitudes HTTP a la API de Conversiones de Facebook. Maneja la autenticación, el formato de las solicitudes y el manejo de errores.
-   `fbpixel/classes/FbpixelCapiTracker.php`:
    -   **Responsabilidad:** Implementa la `FbpixelTrackerInterface` para el seguimiento de eventos del lado del servidor. Formatea los datos de los eventos según las especificaciones de CAPI y los envía a través de `FbpixelCapiClient`.
-   `fbpixel/classes/FbpixelCatalogDoctor.php`:
    -   **Responsabilidad:** Proporciona herramientas y lógica para diagnosticar problemas relacionados con la coincidencia del catálogo de productos y la coherencia de los datos entre PrestaShop y Facebook.
-   `fbpixel/classes/FbpixelConsent.php`:
    -   **Responsabilidad:** Gestiona y verifica el estado del consentimiento del usuario, integrándose con los mecanismos de consentimiento de cookies de PrestaShop (si están disponibles) para garantizar el cumplimiento del GDPR.
-   `fbpixel/classes/FbpixelCurrencyHelper.php`:
    -   **Responsabilidad:** Clase de utilidad para la conversión y el formato de moneda, asegurando que los valores de los eventos se envíen en la moneda objetivo correcta.
-   `fbpixel/classes/FbpixelEmqCoach.php`:
    -   **Responsabilidad:** Probablemente proporciona orientación o recomendaciones para mejorar la calidad de coincidencia de eventos (EMQ) para los eventos de Facebook.
-   `fbpixel/classes/FbpixelEventId.php`:
    -   **Responsabilidad:** Genera y gestiona ID de eventos únicos, cruciales para la deduplicación entre eventos del lado del navegador y del lado del servidor.
-   `fbpixel/classes/FbpixelEvents.php`:
    -   **Responsabilidad:** Una clase central para definir y gestionar los diversos tipos de eventos del Píxel de Facebook (PageView, Purchase, AddToCart, etc.) y sus parámetros estándar.
-   `fbpixel/classes/FbpixelHealthScore.php`:
    -   **Responsabilidad:** Calcula y muestra una "puntuación de salud" para la configuración del píxel, identificando posibles problemas o áreas de mejora.
-   `fbpixel/classes/FbpixelLiveStats.php`:
    -   **Tabla de base de datos:** `ps_fbpixel_events` (probablemente, según la funcionalidad)
    -   **Extiende:** Probablemente `ObjectModel`
    -   **Responsabilidad:** Almacena y recupera datos de eventos localmente para la función "Estadísticas en vivo" en el back office. Maneja la retención y purga de datos.
-   `fbpixel/classes/FbpixelPixelRules.php`:
    -   **Responsabilidad:** Define reglas y condiciones para cuándo deben activarse eventos de píxel específicos, potencialmente basados en el tipo de página, las acciones del usuario o la configuración.
-   `fbpixel/classes/FbpixelPixelTracker.php`:
    -   **Responsabilidad:** Implementa la `FbpixelTrackerInterface` para el seguimiento de eventos del lado del navegador. Genera el código JavaScript para las llamadas `fbq()` y lo inyecta en el front office.
-   `fbpixel/classes/FbpixelProductIdResolver.php`:
    -   **Responsabilidad:** Resuelve el ID de producto y el ID de atributo correctos basándose en la configuración del módulo (prefijo, sufijo, separador, tipo de ID elegido) para enviarlos a Facebook.
-   `fbpixel/classes/FbpixelTrackerFactory.php`:
    -   **Responsabilidad:** Una clase de fábrica que instancia el rastreador apropiado (por ejemplo, `FbpixelPixelTracker` para el navegador, `FbpixelCapiTracker` para el servidor) basándose en la configuración y el contexto del módulo.
-   `fbpixel/classes/FbpixelTrackerInterface.php`:
    -   **Responsabilidad:** Define una interfaz común para todas las clases de seguimiento, asegurando firmas de métodos consistentes para el envío de eventos.
-   `fbpixel/classes/FbpixelUserData.php`:
    -   **Responsabilidad:** Recopila y formatea datos de usuario (por ejemplo, correo electrónico, teléfono, dirección IP) para enviarlos con eventos CAPI, crucial para la calidad de coincidencia de eventos.
-   `fbpixel/classes/index.php`: Archivo vacío, típicamente utilizado para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

-   `fbpixel/lib/searchTool/views/js/autocomplete.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Proporciona funcionalidad de autocompletado para campos de entrada, probablemente utilizada en la configuración del módulo para seleccionar productos, categorías u otras entidades.
-   `fbpixel/views/js/fbpixel-admin.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Maneja la lógica administrativa general para la página de configuración del módulo, incluidas las envíos de formularios, el cambio de pestañas y, potencialmente, las llamadas AJAX a `AdminFbpixelAjaxController`.
-   `fbpixel/views/js/fbpixel-debug.js`:
    -   **Alcance:** Front-office (condicional).
    -   **Detalles:** Proporciona información de depuración en la consola del navegador o una superposición visual, mostrando qué eventos de píxel se están activando y sus parámetros. Activado por una configuración de modo de depuración.
-   `fbpixel/views/js/fbpixel-ghost.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** Probablemente un script del lado del cliente que ayuda a detectar y rastrear eventos que de otro modo podrían pasarse por alto con la observación DOM estándar, como la carga dinámica de contenido o interacciones AJAX específicas.
-   `fbpixel/views/js/fbpixel-live.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Impulsa la pestaña "Estadísticas en vivo", realizando solicitudes AJAX a `AdminFbpixelAjaxController` para obtener y mostrar datos de eventos en tiempo real, y manejando el intervalo de sondeo.
-   `fbpixel/views/js/fbpixel-wizard.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Gestiona el asistente de configuración paso a paso, guiando al comerciante a través de la configuración inicial.
-   `fbpixel/views/js/fbpixel.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** El JavaScript principal del lado del cliente para el Píxel de Facebook. Inicializa la función `fbq()`, maneja los oyentes de eventos para `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout`, etc., y envía eventos a Facebook. También gestiona los selectores CSS para elementos dinámicos.
-   `fbpixel/views/js/mp-collect.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** Probablemente un script de utilidad para recopilar puntos de datos específicos del front-office, posiblemente relacionados con el comportamiento del usuario o factores ambientales, para mejorar los parámetros del evento.
-   `fbpixel/views/js/mp-front.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** Utilidades JavaScript generales del front-office o funciones de ayuda utilizadas por el módulo.
-   `fbpixel/views/js/mp-inspect.js`:
    -   **Alcance:** Front-office (condicional).
    -   **Detalles:** Proporciona una herramienta de inspección, posiblemente una superposición visual, para ayudar a depurar y verificar los eventos del píxel directamente en la tienda.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `fbpixel/lib/searchTool/views/css/autocomplete.css`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Estilos para los desplegables de autocompletado y los campos de entrada utilizados en la interfaz de administración.
-   `fbpixel/views/css/fbpixel-admin.css`:
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Detalles:** Estiliza la página de configuración del módulo, las pestañas, los campos de entrada y la tabla de Estadísticas en vivo.
-   `fbpixel/views/css/fbpixel-debug.css`:
    -   **Alcance:** Front-office (condicional).
    -   **Detalles:** Estilos para la superposición de depuración o la salida de la consola, haciendo que la información de depuración sea más legible.
-   `fbpixel/views/css/mp-inspect.css`:
    -   **Alcance:** Front-office (condicional).
    -   **Detalles:** Estilos para la herramienta de inspección del front-office, si está habilitada.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `fbpixel/views/templates/hook/capi-pageview.tpl`: Renderizado en un hook (probablemente `displayHeader` o `actionFrontControllerSetMedia`) para activar un evento `PageView` del lado del servidor a través de CAPI.
    -   `fbpixel/views/templates/hook/debug.tpl`: Renderiza la superposición de depuración o la salida de la consola para la depuración del front-office.
    -   `fbpixel/views/templates/hook/displayOrderConfirmation.tpl`: Renderiza el evento `Purchase` del lado del navegador en la página de confirmación del pedido.
    -   `fbpixel/views/templates/hook/ghost.tpl`: Renderiza un elemento o script oculto para la funcionalidad de `fbpixel-ghost.js`.
    -   `fbpixel/views/templates/hook/header.tpl`: Renderiza el código de inicialización base del Píxel de Facebook (`fbq('init', ...)` y `fbq('track', 'PageView')`) dentro de la sección `<head>`, típicamente a través de `displayHeader` o `actionFrontControllerSetMedia`.
    -   `fbpixel/views/templates/hook/payment.tpl`: Potencialmente utilizado para rastrear eventos `AddPaymentInfo` u otras interacciones relacionadas con el pago.
    -   `fbpixel/views/templates/hook/product-details.tpl`: Renderiza scripts o datos específicos de las páginas de productos, principalmente para eventos `ViewContent` y `AddToCart`, probablemente inyectados a través de `displayProductFooter` o `displayProductAdditionalInfo`.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `fbpixel/lib/searchTool/views/scripts.tpl`: Incluye JavaScript para la herramienta de búsqueda/autocompletado en la administración.
    -   `fbpixel/views/templates/admin/configure.tpl`: La plantilla principal para la página de configuración del módulo, orquestando todas las demás plantillas de administración.
    -   `fbpixel/views/templates/admin/doctor.tpl`: Muestra los resultados de `FbpixelCatalogDoctor` para diagnosticar problemas del catálogo.
    -   `fbpixel/views/templates/admin/emq.tpl`: Muestra información o recomendaciones de `FbpixelEmqCoach` con respecto a la calidad de coincidencia de eventos.
    -   `fbpixel/views/templates/admin/health.tpl`: Muestra la puntuación de salud del píxel de `FbpixelHealthScore`.
    -   `fbpixel/views/templates/admin/live-maintain.tpl`: Plantilla para gestionar la configuración de estadísticas en vivo (retención, intervalo de sondeo).
    -   `fbpixel/views/templates/admin/live.tpl`: La plantilla contenedora para la pestaña "Estadísticas en vivo".
    -   `fbpixel/views/templates/admin/mode-context.tpl`: Muestra información específica del contexto basada en el modo de funcionamiento del píxel.
    -   `fbpixel/views/templates/admin/mode-note-capi.tpl`: Muestra notas o advertencias específicas de la configuración de CAPI.
    -   `fbpixel/views/templates/admin/mode-note-pixel.tpl`: Muestra notas o advertencias específicas de la configuración del píxel del lado del navegador.
    -   `fbpixel/views/templates/admin/mode-picker.tpl`: Permite al comerciante seleccionar el modo de funcionamiento del píxel (por ejemplo, estándar, depuración).
    -   `fbpixel/views/templates/admin/pixels-list.tpl`: Muestra una lista de ID de píxeles configurados.
    -   `fbpixel/views/templates/admin/recent-events.tpl`: Renderiza la tabla de eventos recientes para la pestaña "Estadísticas en vivo", poblada por `AdminFbpixelAjaxController`.
    -   `fbpixel/views/templates/admin/tabs.tpl`: Renderiza la navegación por pestañas para la página de configuración del módulo.
    -   `fbpixel/views/templates/admin/wizard.tpl`: Renderiza la interfaz del asistente de configuración paso a paso.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   `ps_configuration`: Almacena todas las configuraciones del módulo (por ejemplo, `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
    -   `ps_fbpixel_events` (probablemente): Una tabla personalizada creada por el módulo para almacenar registros de eventos locales para la función "Estadísticas en vivo". Las columnas típicamente incluirían `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent`.
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice, para añadir JS/CSS. | Inyecta el JS principal del Píxel de Facebook, scripts de seguimiento de eventos y CAPI PageView. |
| `displayContactContent` | En la página de contacto. | Activa el evento `Contact`. |
| `displayOrderConfirmation` | En la página de confirmación del pedido. | Activa el evento `Purchase` del lado del navegador. |
| `actionNewsletterRegistrationAfter` | Después de una suscripción al boletín. | Activa el evento `Lead` (y potencialmente `CompleteRegistration` si se combina). |
| `displayProductFooter` | En la parte inferior de las páginas de productos. | Inyecta datos específicos del producto y el evento `ViewContent`. |
| `displayHeader` | En la sección `<head>` de todas las páginas del front-office. | Inyecta el código base del Píxel de Facebook y el evento `PageView`. |
| `DisplayProductButtons` | Cerca de los botones de acción del producto (por ejemplo, Añadir al carrito). | Puede inyectar JS para el oyente de eventos `AddToCart`. |
| `ActionObjectProductInCartDeleteBefore` | Antes de que se elimine un producto del carrito. | Potencialmente activa el evento `RemoveFromCart`. |
| `DisplayProductAdditionalInfo` | En el bloque de información del producto. | Inyección de datos adicionales del producto o activadores de eventos. |
| `ActionCronJob` | Durante la ejecución de un cron programado. | Activa el procesamiento de eventos CAPI, la limpieza de datos. |
| `ActionObjectProductInCartDeleteAfter` | Después de que se elimina un producto del carrito. | Activa el evento `RemoveFromCart`. |
| `ActionValidateOrder` | Después de que un pedido se valida con éxito. | Activa el evento `Purchase` del lado del servidor a través de CAPI. |
| `DisplayLeftColumnProduct` | En la columna izquierda de las páginas de productos. | Menos común para el píxel, posiblemente para eventos específicos relacionados con el producto. |
| `displayExtraLeft` | En la columna extra izquierda. | Menos común para el píxel, posiblemente para eventos específicos relacionados con el producto. |
| `ActionCartUpdateQuantityBefore` | Antes de que se actualice la cantidad del carrito. | Potencialmente utilizado para rastrear cambios que podrían conducir a `RemoveFromCart`. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "Píxel de seguimiento de conversiones de Fb".
