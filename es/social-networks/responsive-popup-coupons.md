---
title: "Cupones popup responsive - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cupones popup responsive' de MyPresta.eu."
sidebar:
  label: "Cupones popup responsive - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Responsive popup coupons en MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/responsive-popup-coupons/)
>
> ---


# Cupones popup responsive

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde configurará todos los parámetros para sus cupones emergentes.

#### Configuración general

-   **Activar módulo:**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar toda la funcionalidad de cupón emergente para su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* La ventana emergente comenzará a aparecer en las páginas seleccionadas según sus otras configuraciones.
        -   *Cuando está desactivado:* La ventana emergente no aparecerá en ninguna parte de su tienda, independientemente de otras configuraciones.
    -   **Valor recomendado:** SÍ (cuando quiera usar el módulo).
    -   **Escenario / ejemplo de comerciante:** Está ejecutando una promoción de vacaciones y quiere activar la ventana emergente por un tiempo limitado. La activa al principio y la desactiva una vez que finaliza la promoción.
-   **Mostrar en:**

    -   **Qué hace este ajuste:** Esto le permite elegir en qué tipos de páginas se mostrará la ventana emergente a sus clientes.
    -   **Efecto de cambiar este ajuste:**
        -   *Página de inicio:* La ventana emergente aparece solo en la página principal de su tienda.
        -   *Páginas de categoría:* La ventana emergente aparece cuando los clientes navegan por categorías de productos.
        -   *Páginas de producto:* La ventana emergente aparece cuando los clientes ven los detalles de productos individuales.
        -   *Páginas CMS:* La ventana emergente aparece en páginas informativas como "Sobre nosotros" o "Contacto".
        -   *Todas las páginas:* La ventana emergente aparece en cada página de su tienda.
    -   **Valor recomendado:** Páginas de producto o Todas las páginas (dependiendo de su estrategia de marketing).
    -   **Escenario / ejemplo de comerciante:** Quiere fomentar las compras directamente en las páginas de producto, por lo que selecciona "Páginas de producto". Si desea la máxima exposición, podría elegir "Todas las páginas".
-   **Retraso (en segundos) antes de que aparezca la ventana emergente:**

    -   **Qué hace este ajuste:** Controla cuánto tiempo después de que se carga una página esperará la ventana emergente antes de aparecer.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 0:* La ventana emergente aparece inmediatamente al cargar la página.
        -   *Establecido en 5:* La ventana emergente aparece 5 segundos después de que se carga la página.
    -   **Valor recomendado:** 3-5 segundos (permite a los clientes ver el contenido primero).
    -   **Escenario / ejemplo de comerciante:** No quiere abrumar a los clientes de inmediato. Establecer un retraso de 3 segundos les da un momento para orientarse antes de que aparezca la oferta.
-   **Mostrar ventana emergente solo una vez por sesión:**

    -   **Qué hace este ajuste:** Determina si un cliente verá la ventana emergente varias veces durante una sola visita a su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Una vez que un cliente ve la ventana emergente (y posiblemente la cierra), no la volverá a ver hasta que cierre su navegador y comience una nueva sesión.
        -   *Cuando está desactivado:* La ventana emergente podría aparecer cada vez que visiten una página donde esté configurada para mostrarse.
    -   **Valor recomendado:** SÍ (para evitar molestar a los clientes).
    -   **Escenario / ejemplo de comerciante:** Un cliente visita varias páginas de producto. Si esto está activado, solo verá la oferta de cupón una vez, evitando irritación.
-   **Mostrar ventana emergente solo una vez por cliente (para siempre):**

    -   **Qué hace este ajuste:** Esta es una configuración más permanente, que evita que un cliente que ha iniciado sesión vuelva a ver la ventana emergente una vez que la ha visto.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo recuerda que un cliente específico (a través de su cuenta) ha visto la ventana emergente y no se la mostrará de nuevo, incluso en futuras sesiones.
        -   *Cuando está desactivado:* Se aplica la regla de "una vez por sesión", o si esa está desactivada, la verán repetidamente.
    -   **Valor recomendado:** SÍ (para una experiencia menos intrusiva para los clientes leales).
    -   **Escenario / ejemplo de comerciante:** Quiere dar a cada cliente la oportunidad de obtener el cupón, pero no recordarles constantemente si ya lo han visto o usado.
-   **Mostrar ventana emergente solo para invitados (clientes no registrados):**

    -   **Qué hace este ajuste:** Restringe la visibilidad de la ventana emergente solo a los visitantes que no han iniciado sesión en una cuenta de cliente.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Solo los visitantes nuevos o recurrentes que no han iniciado sesión verán la ventana emergente. Los clientes que han iniciado sesión no la verán.
        -   *Cuando está desactivado:* Tanto los invitados como los clientes que han iniciado sesión verán la ventana emergente (sujeto a otras reglas de visualización).
    -   **Valor recomendado:** SÍ (a menudo, desea convertir nuevos visitantes, no necesariamente ofrecer descuentos a clientes leales existentes).
    -   **Escenario / ejemplo de comerciante:** Su objetivo es atraer nuevos clientes o fomentar las compras por primera vez. Activa esto para enfocar su oferta en clientes potenciales nuevos.
-   **Mostrar ventana emergente solo para grupos de clientes seleccionados:**

    -   **Qué hace este ajuste:** Le permite dirigir la ventana emergente a grupos específicos de clientes (por ejemplo, "Visitantes", "Clientes", "Invitados" o grupos personalizados que haya creado).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan grupos específicos:* Solo los clientes que pertenecen a esos grupos verán la ventana emergente.
        -   *Cuando no se seleccionan grupos (o se seleccionan todos):* Todos los clientes verán la ventana emergente (sujeto a otras reglas).
    -   **Valor recomendado:** Seleccione "Invitados" y "Visitantes" si su objetivo es la adquisición de nuevos clientes.
    -   **Escenario / ejemplo de comerciante:** Quiere ofrecer un descuento especial solo a su grupo de clientes VIP. Seleccionaría solo ese grupo aquí.
-   **Mostrar ventana emergente solo para países seleccionados:**

    -   **Qué hace este ajuste:** Restringe la aparición de la ventana emergente según la ubicación geográfica del cliente.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan países específicos:* Solo los clientes de esos países verán la ventana emergente.
        -   *Cuando no se seleccionan países (o se seleccionan todos):* Todos los clientes verán la ventana emergente.
    -   **Valor recomendado:** Seleccione países específicos si tiene promociones geo-dirigidas, de lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Está ejecutando una promoción exclusiva para clientes en Francia y Alemania. Seleccionaría solo estos dos países.
-   **Mostrar ventana emergente solo para monedas seleccionadas:**

    -   **Qué hace este ajuste:** Controla la visibilidad de la ventana emergente según la moneda que el cliente esté utilizando actualmente en su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan monedas específicas:* Solo los clientes que utilizan esas monedas verán la ventana emergente.
        -   *Cuando no se seleccionan monedas (o se seleccionan todas):* Todos los clientes verán la ventana emergente.
    -   **Valor recomendado:** Seleccione monedas específicas si su promoción depende de la moneda, de lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Tiene una oferta especial para clientes que pagan en USD. Seleccionaría solo USD aquí.
-   **Mostrar ventana emergente solo para idiomas seleccionados:**

    -   **Qué hace este ajuste:** Determina si la ventana emergente aparece según el idioma que el cliente ha seleccionado para su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan idiomas específicos:* Solo los clientes que ven su tienda en esos idiomas verán la ventana emergente.
        -   *Cuando no se seleccionan idiomas (o se seleccionan todos):* Todos los clientes verán la ventana emergente.
    -   **Valor recomendado:** Seleccione idiomas específicos si el contenido de su ventana emergente solo está traducido para ciertos idiomas, de lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Su mensaje emergente solo está disponible en inglés y español. Seleccionaría estos dos idiomas para asegurarse de que los clientes vean un mensaje relevante.

#### Configuración de cupones

-   **Valor del vale:**

    -   **Qué hace este ajuste:** Define el monto o porcentaje de descuento ofrecido por el cupón.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 10:* El cupón proporcionará un descuento de 10 unidades (por ejemplo, $10, €10).
        -   *Establecido en 15%:* El cupón proporcionará un descuento del 15%.
    -   **Valor recomendado:** Un descuento atractivo (por ejemplo, 10%, $5, €10).
    -   **Escenario / ejemplo de comerciante:** Quiere ofrecer un 10% de descuento, por lo que introduce "10%" aquí.
-   **Tipo de vale:**

    -   **Qué hace este ajuste:** Especifica si el vale es una cantidad fija o un porcentaje.
    -   **Efecto de cambiar este ajuste:**
        -   *Porcentaje:* El "Valor del vale" se tratará como un porcentaje del total del pedido.
        -   *Cantidad:* El "Valor del vale" se tratará como una deducción monetaria fija.
    -   **Valor recomendado:** Porcentaje (a menudo más atractivo para diferentes tamaños de pedido).
    -   **Escenario / ejemplo de comerciante:** Quiere dar un 10% de descuento, por lo que selecciona "Porcentaje". Si quiere dar un descuento fijo de $5, selecciona "Cantidad".
-   **Importe mínimo del vale:**

    -   **Qué hace este ajuste:** Establece un valor mínimo de pedido que un cliente debe alcanzar para poder usar el cupón.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 50:* El cupón solo se puede usar si el total del carrito es de $50 o más.
        -   *Establecido en 0 (o vacío):* No se requiere un importe mínimo de pedido.
    -   **Valor recomendado:** Un mínimo razonable para proteger sus márgenes, o 0 si desea fomentar cualquier compra.
    -   **Escenario / ejemplo de comerciante:** Quiere asegurarse de que el descuento solo se aplique a pedidos superiores a $50, por lo que introduce "50".
-   **Caducidad del vale (en días):**

    -   **Qué hace este ajuste:** Define cuántos días será válido el código de cupón generado desde el momento en que se emite.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 7:* El cupón caducará 7 días después de que el cliente lo reciba.
        -   *Establecido en 0 (o vacío):* El cupón no caducará.
    -   **Valor recomendado:** 7-30 días (crea urgencia sin ser demasiado restrictivo).
    -   **Escenario / ejemplo de comerciante:** Quiere que los clientes usen el cupón rápidamente, por lo que establece una caducidad de 7 días.
-   **Descripción del vale:**

    -   **Qué hace este ajuste:** Proporciona un nombre descriptivo para el cupón en su back office de PrestaShop (por ejemplo, en la sección "Reglas de carrito"). Esto es para su referencia interna.
    -   **Efecto de cambiar este ajuste:** Este texto aparecerá en su panel de administración de PrestaShop cuando vea las reglas de carrito generadas, ayudándole a identificar su origen. No aparece para el cliente.
    -   **Valor recomendado:** "Cupón Popup - [Fecha]" o "Descuento por Me gusta en Facebook".
    -   **Escenario / ejemplo de comerciante:** Introduce "Descuento Popup por Me gusta en Facebook" para saber exactamente de dónde provienen estos cupones al revisar sus reglas de carrito.
-   **Envío gratuito con vale:**

    -   **Qué hace este ajuste:** Determina si el cupón también otorga envío gratuito en el pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Al cliente no se le cobrará el envío al usar este cupón.
        -   *Cuando está desactivado:* Se aplicarán los costos de envío estándar.
    -   **Valor recomendado:** NO (a menos que quiera ofrecer envío gratuito como un fuerte incentivo).
    -   **Escenario / ejemplo de comerciante:** Quiere ofrecer una oferta muy atractiva, por lo que activa el envío gratuito junto con el descuento.
-   **Vale aplicable a productos específicos:**

    -   **Qué hace este ajuste:** Le permite restringir el uso del cupón solo a ciertos productos de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan productos específicos:* El cupón solo funcionará si esos productos están en el carrito.
        -   *Cuando no se seleccionan productos:* El cupón se aplica a todos los productos del carrito.
    -   **Valor recomendado:** Déjelo vacío a menos que tenga una promoción de producto específica.
    -   **Escenario / ejemplo de comerciante:** Está promocionando una nueva línea de zapatos. Selecciona solo esos zapatos aquí, para que el cupón solo funcione para ellos.
-   **Vale aplicable a categorías específicas:**

    -   **Qué hace este ajuste:** Le permite restringir el uso del cupón a productos dentro de categorías específicas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan categorías específicas:* El cupón solo funcionará si los productos de esas categorías están en el carrito.
        -   *Cuando no se seleccionan categorías:* El cupón se aplica a todos los productos.
    -   **Valor recomendado:** Déjelo vacío a menos que tenga una promoción de categoría específica.
    -   **Escenario / ejemplo de comerciante:** Quiere liquidar existencias antiguas en su categoría "Colección de Verano". Selecciona esa categoría aquí.
-   **Vale aplicable a fabricantes específicos:**

    -   **Qué hace este ajuste:** Le permite restringir el uso del cupón a productos de marcas/fabricantes específicos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se seleccionan fabricantes específicos:* El cupón solo funcionará si los productos de esos fabricantes están en el carrito.
        -   *Cuando no se seleccionan fabricantes:* El cupón se aplica a todos los productos.
    -   **Valor recomendado:** Déjelo vacío a menos que tenga una promoción de marca específica.
    -   **Escenario / ejemplo de comerciante:** Tiene una asociación con una marca específica y quiere ofrecer un descuento solo en sus productos.

#### Diseño y contenido del popup

-   **Ancho del popup (en píxeles):**

    -   **Qué hace este ajuste:** Controla el tamaño horizontal de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Un número mayor hace que la ventana emergente sea más ancha, un número menor la hace más estrecha.
    -   **Valor recomendado:** 600px - 800px (para una buena visibilidad en escritorio, el diseño responsivo se encargará del móvil).
    -   **Escenario / ejemplo de comerciante:** Quiere que la ventana emergente sea prominente pero no demasiado ancha, por lo que la establece en 700px.
-   **Color de fondo del popup:**

    -   **Qué hace este ajuste:** Establece el color de fondo de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Cambia la apariencia visual de la ventana emergente para que coincida con su marca o destaque.
    -   **Valor recomendado:** Un color que contraste bien con su texto y marca (por ejemplo, #FFFFFF para blanco, #F0F0F0 para gris claro).
    -   **Escenario / ejemplo de comerciante:** Su marca usa mucho azul, por lo que elige un código hexadecimal azul claro como #E0F2F7.
-   **Color del texto del popup:**

    -   **Qué hace este ajuste:** Establece el color del texto que se muestra dentro de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Asegura la legibilidad contra el color de fondo elegido.
    -   **Valor recomendado:** Un color que proporcione un buen contraste (por ejemplo, #000000 para negro, #333333 para gris oscuro).
    -   **Escenario / ejemplo de comerciante:** Con un fondo claro, elige un color de texto oscuro como #333333 para una legibilidad óptima.
-   **Color del borde del popup:**

    -   **Qué hace este ajuste:** Establece el color del borde alrededor de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Agrega un marco visual a la ventana emergente.
    -   **Valor recomendado:** Un color sutil que complemente su diseño o un color fuerte para que destaque (por ejemplo, #CCCCCC para gris claro, o el color de acento de su marca).
    -   **Escenario / ejemplo de comerciante:** Quiere un aspecto limpio, por lo que elige un borde gris sutil #DDDDDD.
-   **Ancho del borde del popup (en píxeles):**

    -   **Qué hace este ajuste:** Controla el grosor del borde de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Un número mayor hace que el borde sea más grueso.
    -   **Valor recomendado:** 1-3px.
    -   **Escenario / ejemplo de comerciante:** Quiere un borde delgado y elegante, por lo que lo establece en 1px.
-   **Radio del borde del popup (en píxeles):**

    -   **Qué hace este ajuste:** Controla la redondez de las esquinas de la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 0:* Esquinas afiladas y cuadradas.
        -   *Establecido en 10:* Esquinas ligeramente redondeadas.
        -   *Establecido en 50 (o más):* Esquinas muy redondeadas, tipo píldora.
    -   **Valor recomendado:** 5-10px (para un aspecto moderno y suave).
    -   **Escenario / ejemplo de comerciante:** Prefiere una estética más suave, por lo que establece el radio del borde en 8px.
-   **Sombra del popup:**

    -   **Qué hace este ajuste:** Agrega un efecto de sombra alrededor de la ventana emergente, haciéndola parecer que flota sobre la página.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* La ventana emergente tendrá una sombra sutil, dándole profundidad.
        -   *Cuando está desactivado:* La ventana emergente no tendrá sombra.
    -   **Valor recomendado:** SÍ (agrega un toque profesional y moderno).
    -   **Escenario / ejemplo de comerciante:** Quiere que la ventana emergente destaque visualmente del fondo, por lo que activa la sombra.
-   **Color del botón de cierre del popup:**

    -   **Qué hace este ajuste:** Establece el color del botón 'X' que los clientes usan para cerrar la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Asegura que el botón de cierre sea visible y coincida con su diseño.
    -   **Valor recomendado:** Un color contrastante para la visibilidad (por ejemplo, #000000, #FF0000).
    -   **Escenario / ejemplo de comerciante:** Quiere que el botón de cierre sea claramente visible, por lo que lo establece en negro #000000.
-   **Contenido del popup (se permite HTML):**

    -   **Qué hace este ajuste:** Aquí es donde introduce el mensaje principal y el contenido de su ventana emergente. Puede usar HTML para formatear texto, agregar imágenes e incluir sus botones de redes sociales.
    -   **Efecto de cambiar este ajuste:** Este texto y HTML se mostrarán dentro de la ventana emergente.
    -   **Valor recomendado:** Mensaje claro y conciso con una fuerte llamada a la acción. Incluya el código de su botón de "Me gusta" de Facebook o un widget de redes sociales similar.
    -   **Escenario / ejemplo de comerciante:** Podría introducir: `<p>¡Danos "Me gusta" en Facebook y obtén un <strong>10% DE DESCUENTO</strong> en tu próximo pedido!</p><div class="fb-like" data-href="URL_DE_TU_PAGINA_DE_FACEBOOK" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (Recuerde reemplazar `URL_DE_TU_PAGINA_DE_FACEBOOK`).
-   **Mensaje del cupón del popup (se permite HTML):**

    -   **Qué hace este ajuste:** Este es el mensaje que se muestra *después* de que el cliente realiza la acción requerida (por ejemplo, le da "Me gusta" a su página) y recibe su código de cupón.
    -   **Efecto de cambiar este ajuste:** Este mensaje aparecerá en la ventana emergente, típicamente encima del código de cupón generado.
    -   **Valor recomendado:** Un mensaje de agradecimiento e instrucciones sobre cómo usar el cupón.
    -   **Escenario / ejemplo de comerciante:** Podría introducir: `<p>¡Gracias por darnos "Me gusta"! Aquí tienes tu código de descuento exclusivo:</p><p>Usa el código <strong>{coupon_code}</strong> al finalizar la compra.</p>` (El marcador de posición `{coupon_code}` se reemplazará automáticamente).

#### Configuración avanzada

-   **Código CSS personalizado:**

    -   **Qué hace este ajuste:** Le permite agregar sus propias reglas CSS personalizadas para estilizar aún más la ventana emergente o anular los estilos predeterminados.
    -   **Efecto de cambiar este ajuste:** Cualquier CSS que introduzca aquí se aplicará a la ventana emergente, dándole un control preciso sobre su apariencia.
    -   **Valor recomendado:** Déjelo vacío a menos que tenga necesidades de estilo específicas.
    -   **Escenario / ejemplo de comerciante:** Quiere cambiar el tamaño de fuente del código de cupón. Podría agregar: `.coupon-code { font-size: 24px !important; }`
-   **Código JavaScript personalizado:**

    -   **Qué hace este ajuste:** Le permite agregar su propio código JavaScript personalizado para interactuar con la ventana emergente o integrarse con otros servicios.
    -   **Efecto de cambiar este ajuste:** Cualquier JavaScript que introduzca aquí se ejecutará cuando se muestre o se interactúe con la ventana emergente.
    -   **Valor recomendado:** Déjelo vacío a menos que tenga necesidades de scripting específicas (por ejemplo, seguimiento de eventos de Google Analytics).
    -   **Escenario / ejemplo de comerciante:** Quiere enviar un evento a Google Analytics cuando se muestra la ventana emergente. Podría agregar: `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activar módulo | SÍ | Interruptor maestro para la funcionalidad del popup. |
| | Mostrar en | Páginas de producto / Todas las páginas | Selecciona dónde aparece el popup (Página de inicio, Categoría, Producto, CMS, Todas). |
| | Retraso (en segundos) antes de que aparezca el popup | 3-5 segundos | Tiempo antes de que el popup se muestre después de cargar la página. |
| | Mostrar popup solo una vez por sesión | SÍ | Evita que el popup se muestre varias veces en una sesión del navegador. |
| | Mostrar popup solo una vez por cliente (para siempre) | SÍ | Evita que los clientes registrados vuelvan a ver el popup. |
| | Mostrar popup solo para invitados | SÍ | Dirigido a visitantes no registrados. |
| | Mostrar popup solo para grupos de clientes seleccionados | Invitados, Visitantes | Restringe el popup a grupos de clientes específicos. |
| | Mostrar popup solo para países seleccionados | Dejar vacío | Restringe el popup a países específicos. |
| | Mostrar popup solo para monedas seleccionadas | Dejar vacío | Restringe el popup a monedas específicas. |
| | Mostrar popup solo para idiomas seleccionados | Dejar vacío | Restringe el popup a idiomas específicos. |
| | Valor del vale | Ej., 10% | El monto o porcentaje de descuento. |
| | Tipo de vale | Porcentaje / Cantidad | Define si el vale es % o cantidad fija. |
| | Importe mínimo del vale | 0 (o valor razonable) | Valor mínimo del pedido para usar el cupón. |
| | Caducidad del vale (en días) | 7-30 días | Período de validez del cupón generado. |
| | Descripción del vale | "Descuento Popup por Me gusta en Facebook" | Nombre interno del cupón en el BO. |
| | Envío gratuito con vale | NO | Otorga envío gratuito con el cupón. |
| | Vale aplicable a productos específicos | Dejar vacío | Restringe el cupón a productos específicos. |
| | Vale aplicable a categorías específicas | Dejar vacío | Restringe el cupón a categorías específicas. |
| | Vale aplicable a fabricantes específicos | Dejar vacío | Restringe el cupón a fabricantes específicos. |
| | Ancho del popup (en píxeles) | 600px - 800px | Tamaño horizontal del popup. |
| | Color de fondo del popup | #FFFFFF (blanco) | Color de fondo del popup. |
| | Color del texto del popup | #000000 (negro) | Color del texto dentro del popup. |
| | Color del borde del popup | #DDDDDD (gris claro) | Color del borde del popup. |
| | Ancho del borde del popup (en píxeles) | 1-3px | Grosor del borde del popup. |
| | Radio del borde del popup (en píxeles) | 5-10px | Redondez de las esquinas del popup. |
| | Sombra del popup | SÍ | Agrega un efecto de sombra al popup. |
| | Color del botón de cierre del popup | #000000 (negro) | Color del botón de cierre 'X'. |
| | Contenido del popup (se permite HTML) | Mensaje atractivo + Widget social | Contenido principal mostrado en el popup. |
| | Mensaje del cupón del popup (se permite HTML) | Mensaje de agradecimiento + {coupon\_code} | Mensaje mostrado después de generar el cupón. |
| | Código CSS personalizado | Dejar vacío | Añadir estilos CSS personalizados. |
| | Código JavaScript personalizado | Dejar vacío | Añadir JavaScript personalizado. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La ventana emergente no aparece en mi tienda. ¿Qué debo revisar primero?**
R1:

-   **¿Está el módulo activado?** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Cupones popup responsive" esté instalado y activado.
-   **Verifique la configuración "Activar módulo":** En la configuración del módulo, asegúrese de que el interruptor "Activar módulo" esté en SÍ.
-   **Verifique la configuración "Mostrar en":** Asegúrese de haber seleccionado los tipos de página correctos (por ejemplo, Página de inicio, Páginas de producto) donde espera que aparezca la ventana emergente.
-   **Borre su caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Es posible que también deba borrar la caché del navegador (Ctrl+F5 o Cmd+Shift+R).
-   **Verifique si hay conflictos:** Desactive temporalmente otros módulos que puedan interactuar con ventanas emergentes o el contenido de la página para descartar conflictos.

**P2: La ventana emergente aparece, pero el botón de "Me gusta" de Facebook (u otro widget social) no funciona o no se muestra correctamente.**
R2:

-   **HTML incorrecto:** Vuelva a verificar el código HTML que ha introducido en el campo "Contenido del popup". Incluso un pequeño error tipográfico puede romperlo. Asegúrese de que la URL de su página de Facebook sea correcta.
-   **SDK de Facebook:** Para que los botones de "Me gusta" de Facebook funcionen, el SDK de JavaScript de Facebook debe estar cargado. Los temas de PrestaShop a menudo incluyen esto, pero si no, es posible que deba agregarlo a través de código personalizado o asegurarse de que su tema lo admita.
-   **Bloqueadores de anuncios:** Algunos bloqueadores de anuncios pueden impedir que se carguen los widgets sociales. Pruebe en una ventana de incógnito sin extensiones.

**P3: El código de cupón se genera, pero no funciona al finalizar la compra.**
R3:

-   **Verifique la configuración del cupón:** Revise todas las configuraciones de "Vale" en la configuración del módulo:
    -   **Importe mínimo:** ¿El valor del carrito del cliente está por encima del "Importe mínimo del vale"?
    -   **Caducidad:** ¿Ha pasado la fecha de "Caducidad del vale"?
    -   **Productos/categorías/fabricantes específicos:** ¿El carrito del cliente contiene los artículos requeridos si se utilizan estas configuraciones?
    -   **Grupos de clientes/países/monedas/idiomas:** ¿El cliente cumple los criterios establecidos para estas restricciones?
-   **Reglas de carrito de PrestaShop:** El módulo crea una "Regla de carrito" en PrestaShop. Vaya a **Catálogo > Descuentos > Reglas de carrito** (o **Reglas de precios > Reglas de carrito** en versiones anteriores) y busque el código de cupón. Verifique sus detalles para ver si se aplicaron restricciones incorrectamente.

**P4: El diseño del popup no coincide perfectamente con el tema de mi tienda.**
R4:

-   **Utilice la configuración de diseño del módulo:** Ajuste el "Color de fondo del popup", "Color del texto del popup", "Color del borde del popup", "Ancho del borde del popup" y "Radio del borde del popup" para que coincidan mejor con su tema.
-   **CSS personalizado:** Para un estilo más avanzado, utilice el campo "Código CSS personalizado" en la configuración del módulo. Puede inspeccionar los elementos del popup utilizando las herramientas de desarrollador de su navegador (F12) para encontrar los selectores CSS correctos a los que dirigirse.
-   **Sobreescrituras de tema:** Si se siente cómodo con la codificación, también puede anular el CSS del módulo en el archivo `custom.css` o `theme.css` de su tema.

**P5: ¿Cómo traduzco el contenido del popup a varios idiomas?**
R5:

-   Los campos "Contenido del popup" y "Mensaje del cupón del popup" suelen estar diseñados para introducirse una sola vez. Para la compatibilidad con varios idiomas, necesitaría utilizar el sistema de traducción de PrestaShop.
-   Vaya a **Internacional > Traducciones**. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Cupones popup responsive". Debería encontrar los campos de texto para traducir allí.
-   Si los campos no son directamente traducibles a través de la interfaz estándar de PrestaShop, es posible que deba crear ventanas emergentes separadas para cada idioma (si el módulo admite múltiples instancias) o utilizar una solución personalizada que involucre variables Smarty y lógica condicional dentro del contenido HTML, lo que requiere asistencia de un desarrollador.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Cupones popup responsive" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo "Cupones popup responsive" (`popcoupon`) es un módulo estándar de PrestaShop implementado principalmente dentro de su archivo PHP principal, `ajax_popcoupon.php`. Aprovecha el sistema de hooks de PrestaShop para la visualización en el front-office y la clase `Configuration` para el almacenamiento de la configuración. La funcionalidad principal del módulo implica mostrar una ventana emergente, manejar la interacción del usuario (por ejemplo, acción en redes sociales) y generar dinámicamente códigos de `CartRule` (vale) de PrestaShop. Utiliza JavaScript del lado del cliente para la lógica de visualización y el estilo de la ventana emergente, y una plantilla mínima para renderizar la estructura de la ventana emergente.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de administración de Front-Office o Back-Office dedicado en archivos separados. Toda la lógica de configuración del back-office se maneja dentro del método `getContent()` de la clase principal del módulo. La visualización del front-office se gestiona a través de hooks y JavaScript del lado del cliente.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase `ObjectModel` personalizada ni otras clases PHP principales en un directorio `classes/`. Toda la lógica está contenida dentro del archivo principal del módulo `ajax_popcoupon.php`. El módulo interactúa directamente con la clase `Configuration` de PrestaShop para la configuración y la clase `CartRule` para la generación de vales.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript:

-   **`popcoupon/jscolor/jscolor.js`**

    -   **Alcance:** Back-office.
    -   **Propósito:** Esta es una biblioteca JavaScript de terceros para un selector de color. Se utiliza en el formulario de configuración del back-office del módulo para permitir a los comerciantes seleccionar fácilmente los colores para el fondo, el texto, el borde y el botón de cierre de la ventana emergente. Se vincula a campos de entrada con clases específicas para proporcionar una interfaz visual de selección de color.
-   **`popcoupon/lib/voucherengine/script.js`**

    -   **Alcance:** Front-office.
    -   **Propósito:** Este es el archivo JavaScript principal responsable de la funcionalidad de la ventana emergente del front-office.
        -   **Escuchadores de eventos:** Escucha los eventos de carga de la página para activar la ventana emergente después del retraso configurado. También maneja eventos relacionados con el cierre de la ventana emergente (por ejemplo, haciendo clic en el botón 'X' o fuera de la ventana emergente).
        -   **Manipulación del DOM:** Inyecta dinámicamente la estructura HTML de la ventana emergente en la página, gestiona su visibilidad (mostrar/ocultar) y actualiza su contenido (por ejemplo, mostrando el código de cupón después de una acción social).
        -   **Llamadas AJAX:** Probablemente realiza llamadas AJAX a `ajax_popcoupon.php` del módulo (o un punto de entrada similar) para:
            1.  Verificar si la ventana emergente debe mostrarse para el usuario/sesión actual.
            2.  Generar un código de cupón único después de que el usuario complete la acción requerida (por ejemplo, "Me gusta" en Facebook).
            3.  Almacenar datos de usuario/sesión (por ejemplo, una cookie) para evitar la visualización repetida de la ventana emergente según la configuración ("una vez por sesión", "una vez por cliente").
        -   **SDK de terceros:** Si el "Contenido del popup" incluye un botón de "Me gusta" de Facebook, este script podría interactuar con el SDK de JavaScript de Facebook (si lo carga el tema) para detectar cuándo se completa la acción de "Me gusta".
-   **`popcoupon/trusted.js`**

    -   **Alcance:** Front-office.
    -   **Propósito:** El propósito exacto de este archivo no está explícitamente definido en la información proporcionada, pero basándose en las prácticas comunes de los módulos, podría ser:
        -   Un pequeño script de utilidad para seguimiento o análisis.
        -   Un script relacionado con insignias de confianza o características de seguridad.
        -   Un script de respaldo o complementario para el `script.js` principal.
        -   Podría contener lógica relacionada con el manejo de cookies o el almacenamiento local para las funciones de "mostrar una vez".

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye los siguientes archivos CSS:

-   **`popcoupon/css.css`**

    -   **Alcance:** Front-office.
    -   **Propósito:** Esta es la hoja de estilo principal para la ventana emergente.
        -   **Componentes de la interfaz de usuario:** Estiliza el contenedor general de la ventana emergente, su superposición, el botón de cierre y, potencialmente, el área de contenido.
        -   **Selectores clave:** Los desarrolladores pueden esperar selectores como `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close`, etc. Estos pueden ser anulados en el `custom.css` de un tema personalizado o utilizando la configuración "Código CSS personalizado" del módulo.
        -   **Responsividad:** Contiene consultas de medios o propiedades de caja flexible/cuadrícula para asegurar que la ventana emergente se adapte bien a diferentes tamaños de pantalla.
-   **`popcoupon/lib/voucherengine/ps16.css`**

    -   **Alcance:** Front-office.
    -   **Propósito:** Esta hoja de estilo probablemente contiene ajustes de estilo específicos o anulaciones adaptadas para temas de PrestaShop 1.6. Podría abordar diferencias de diseño o estilos de elementos predeterminados prevalentes en PS 1.6 para asegurar que la ventana emergente se vea consistente en diferentes versiones de PrestaShop. Para PS 1.7/8, algunos de estos estilos podrían ser anulados por `css.css` o el propio tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty:

-   **`popcoupon/views/header.tpl`**
    -   **Hook:** `displayHeader` (o similar, dependiendo de cómo esté registrado en `ajax_popcoupon.php`).
    -   **Propósito:** Esta plantilla es probablemente responsable de inyectar la estructura HTML necesaria para la ventana emergente (que inicialmente está oculta) y, potencialmente, los activos JavaScript y CSS en el `<head>` o `<body>` de la página del front-office. Podría contener:
        -   El esqueleto HTML básico para el modal de la ventana emergente y su superposición.
        -   Lógica condicional para incluir los archivos JavaScript y CSS solo cuando el módulo está activado.
        -   Marcadores de posición para contenido dinámico que será rellenado por JavaScript.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos:**

    -   Este módulo no crea tablas SQL personalizadas.
    -   Almacena su configuración en la tabla `ps_configuration` de PrestaShop. Las claves de configuración normalmente comenzarán con `POPCOUPON_` (por ejemplo, `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
    -   Aprovecha las tablas `ps_cart_rule` y `ps_cart_rule_lang` de PrestaShop para generar y gestionar los códigos de cupón únicos.
    -   Para las funciones de "mostrar una vez por cliente/sesión", probablemente utiliza cookies o entradas de configuración específicas de `ps_customer`.
-   **Tabla de Hooks registrados:**

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyección de CSS, JavaScript y la estructura HTML inicial (oculta) para la ventana emergente. |
| `displayFooter` | Al final de la sección `<body>` de cada página del front-office. | Hook alternativo para inyectar JS/CSS o el HTML de la ventana emergente, a menudo preferido por rendimiento. |
| `displayLeftColumn` | En la columna izquierda del front-office. | Menos común para ventanas emergentes, pero podría usarse para activar o mostrar un elemento emergente más pequeño. |
| `displayRightColumn` | En la columna derecha del front-office. | Similar a `displayLeftColumn`. |
| `displayProductButtons` | En la página del producto, cerca del botón de añadir al carrito. | Podría usarse para activar una ventana emergente específica del producto o mostrar una pequeña oferta de cupón. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal establece sus medios (JS/CSS). | Una forma más robusta de registrar activos JS/CSS, asegurando que se carguen correctamente. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | (Menos probable para este módulo, pero podría usarse para acciones post-compra relacionadas con cupones). |

*Nota: Los hooks exactos utilizados están determinados por los métodos `hook` implementados en `ajax_popcoupon.php` (por ejemplo, `hookDisplayHeader()`). La descripción del módulo menciona "Cabecera, Columnas, Producto o Pie de página", lo que indica que se registra para al menos uno de estos hooks de visualización.*

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Cupones popup responsive", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
