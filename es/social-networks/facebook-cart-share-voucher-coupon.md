---
title: "Compartir carrito en Facebook + cupón de vale - Manual y guía de configuración para el comerciante"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Compartir carrito en Facebook + cupón de vale' de MyPresta.eu."
sidebar:
  label: "Compartir carrito en Facebook + cupón de vale"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook cart share + voucher coupon en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Compartir carrito en Facebook + cupón de vale

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y las interacciones con la API de Facebook.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal para el módulo "Compartir carrito en Facebook + cupón de vale". La encontrará navegando a **Módulos > Gestor de módulos**, buscando "Compartir carrito en Facebook + cupón de vale" y haciendo clic en "Configurar".

#### **Configuración general**

-   **ID de aplicación de Facebook (cshare_appid / cshare_app_id)**
    -   **Qué hace este ajuste:** Es un identificador único para su aplicación de Facebook, que es necesario para que el módulo interactúe con la API de Facebook. Debe crear una aplicación de Facebook en la plataforma de desarrolladores de Facebook (developers.facebook.com) para obtener este ID.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se configura correctamente:* El módulo puede conectarse con éxito a Facebook, permitiendo a los clientes compartir sus carritos y a su tienda rastrear estas acciones.
        -   *Cuando se deja vacío o se configura incorrectamente:* La funcionalidad de compartir en Facebook no funcionará y los clientes no podrán compartir sus carritos.
    -   **Valor recomendado:** Su ID de aplicación de Facebook único.
    -   **Escenario / ejemplo de comerciante:** Ha registrado su tienda PrestaShop como una aplicación en Facebook Developers y ha recibido un ID de aplicación como `123456789012345`. Introduzca este ID aquí.

-   **Mostrar botón de compartir en (cshare_lasttab)**
    -   **Qué hace este ajuste:** Determina dónde aparecerá el botón "Compartir carrito en Facebook" en el front office de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Página del carrito de compras":* El botón aparece en la página donde los clientes revisan el contenido de su carrito antes de proceder al pago.
        -   *Cuando se establece en "Página de confirmación de pedido":* El botón aparece después de que el cliente ha realizado un pedido con éxito.
        -   *Cuando se establece en "Ambos":* El botón aparece en ambas páginas.
    -   **Valor recomendado:** "Ambos" para maximizar la visibilidad y las oportunidades de compartir.
    -   **Escenario / ejemplo de comerciante:** Desea fomentar el uso compartido tanto antes como después de una compra, por lo que selecciona "Ambos".

-   **Estilo del botón de compartir en Facebook (cshare_button_style)**
    -   **Qué hace este ajuste:** Le permite elegir el estilo visual del botón de compartir en Facebook.
    -   **Efecto de cambiar este ajuste:** Cambia la apariencia del botón de compartir para que coincida mejor con el diseño de su tienda o su preferencia por un botón más grande/pequeño.
    -   **Valor recomendado:** Experimente para encontrar lo que mejor se adapte a su tema.
    -   **Escenario / ejemplo de comerciante:** Su tema tiene un diseño minimalista, por lo que podría elegir un botón de compartir simple, basado en texto, en lugar de uno grande y gráfico.

#### **Configuración de vales**

-   **Habilitar generación de vales (cshare_voucher)**
    -   **Qué hace este ajuste:** Activa o desactiva la generación y oferta de un vale de descuento al cliente después de que comparta con éxito su carrito en Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se crea un código de vale único y se muestra al cliente después de compartir.
        -   *Cuando está deshabilitado:* No se genera ni se ofrece ningún vale, eliminando el incentivo directo para compartir.
    -   **Valor recomendado:** "SÍ" para aprovechar el incentivo para compartir y aumentar las conversiones.
    -   **Escenario / ejemplo de comerciante:** Desea recompensar a los clientes por compartir y fomentar las compras repetidas, por lo que habilita esta opción.

-   **Regalo de vale (cshare_gift)**
    -   **Qué hace este ajuste:** Define el tipo y el valor del vale de descuento que reciben los clientes. Esto corresponde a la configuración de "Tipo de descuento" y "Valor" al crear una nueva regla de carrito en PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cantidad fija:* El cliente recibe un descuento monetario específico (por ejemplo, 5 € de descuento).
        -   *Porcentaje:* El cliente recibe un descuento porcentual (por ejemplo, 10% de descuento).
        -   *Envío gratuito:* El cliente recibe envío gratuito en su próximo pedido.
    -   **Valor recomendado:** Un valor lo suficientemente atractivo como para incentivar el uso compartido, pero también sostenible para su negocio.
    -   **Escenario / ejemplo de comerciante:** Decide ofrecer un "10% de descuento" para fomentar nuevas compras, por lo que selecciona "Porcentaje" y establece el valor en el siguiente campo.

-   **Valor del vale (cshare_image)**
    -   **Qué hace este ajuste:** Establece el valor específico del vale, dependiendo del tipo de "Regalo de vale" elegido.
    -   **Efecto de cambiar este ajuste:**
        -   *Si se elige "Cantidad fija":* Este será el valor monetario exacto del descuento.
        -   *Si se elige "Porcentaje":* Este será el porcentaje del descuento.
    -   **Valor recomendado:** Un descuento atractivo (por ejemplo, 5, 10, 15 para porcentaje; 5, 10, 20 para cantidad fija).
    -   **Escenario / ejemplo de comerciante:** Eligió "Porcentaje" para "Regalo de vale", por lo que aquí introduce "10" para un descuento del 10%.

#### **Configuración de contenido compartido**

Estos ajustes controlan qué información sobre el carrito del cliente se incluye en la publicación de Facebook cuando lo comparte.

-   **Mostrar precios (cshare_show_prices)**
    -   **Qué hace este ajuste:** Determina si los precios individuales de los productos en el carrito se muestran en la publicación compartida de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Cada producto listado en el carrito compartido mostrará su precio.
        -   *Cuando está deshabilitado:* Los precios de los productos se omitirán de la publicación compartida.
    -   **Valor recomendado:** "SÍ" para proporcionar transparencia y fomentar los clics, a menos que su estrategia de precios requiera lo contrario.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes potenciales vean el valor de los artículos, por lo que habilita "Mostrar precios".

-   **Mostrar total (cshare_show_total)**
    -   **Qué hace este ajuste:** Determina si el valor total del carrito de compras se muestra en la publicación compartida de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se mostrará el precio total de todos los artículos en el carrito.
        -   *Cuando está deshabilitado:* El total del carrito no se incluirá en la publicación.
    -   **Valor recomendado:** "SÍ" para dar una visión general clara del valor del carrito.
    -   **Escenario / ejemplo de comerciante:** Un cliente tiene un carrito valorado en 250 €, y desea que sus amigos vean esta compra significativa, por lo que habilita "Mostrar total".

-   **Mostrar productos (cshare_show_products)**
    -   **Qué hace este ajuste:** Determina si los nombres y las cantidades de los productos individuales en el carrito se enumeran en la publicación compartida de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Una lista de productos (por ejemplo, "Camiseta x1, Vaqueros x1") aparecerá en la publicación.
        -   *Cuando está deshabilitado:* Solo aparecerá un mensaje general sobre el uso compartido del carrito, sin detalles específicos del producto.
    -   **Valor recomendado:** "SÍ" para mostrar los artículos específicos y generar interés.
    -   **Escenario / ejemplo de comerciante:** Desea destacar los productos específicos que un cliente está comprando, por lo que habilita "Mostrar productos".

-   **Mostrar URL del producto (cshare_show_product_url)**
    -   **Qué hace este ajuste:** Determina si se incluyen enlaces directos a las páginas de productos individuales en la publicación compartida de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Cada producto listado tendrá un enlace clicable a su página en su tienda.
        -   *Cuando está deshabilitado:* Los nombres de los productos se mostrarán, pero sin enlaces directos.
    -   **Valor recomendado:** "SÍ" para dirigir el tráfico directamente a las páginas de productos.
    -   **Escenario / ejemplo de comerciante:** Desea que los amigos del que comparte puedan hacer clic fácilmente y ver los productos, por lo que habilita "Mostrar URL del producto".

#### **Configuración avanzada**

-   **Forzar HTTPS (cshare_http)**
    -   **Qué hace este ajuste:** Asegura que todas las URL generadas para compartir en Facebook utilicen HTTPS, incluso si la configuración de su PrestaShop a veces podría predeterminar HTTP. Esto es crucial para la seguridad y los requisitos de Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Todos los enlaces compartidos serán seguros (HTTPS).
        -   *Cuando está deshabilitado:* Los enlaces a veces podrían ser HTTP, lo que puede causar problemas con la API de Facebook y advertencias de seguridad.
    -   **Valor recomendado:** "SÍ" si su tienda utiliza HTTPS (¡lo cual debería!).
    -   **Escenario / ejemplo de comerciante:** Toda su tienda funciona con HTTPS, por lo que habilita esto para garantizar la coherencia y evitar advertencias del navegador.

-   **Nombre de la tienda PrestaShop (PS_SHOP_NAME)**
    -   **Qué hace este ajuste:** Este campo normalmente extrae el nombre de su tienda de la configuración general de PrestaShop. Se utiliza en la publicación compartida de Facebook.
    -   **Efecto de cambiar este ajuste:** Asegura que el nombre correcto de la tienda se muestre en la publicación de Facebook.
    -   **Valor recomendado:** Dejar como predeterminado (debería rellenarse automáticamente desde la configuración de su PrestaShop).
    -   **Escenario / ejemplo de comerciante:** Su tienda se llama "Mi Tienda Impresionante", y este campo muestra correctamente "Mi Tienda Impresionante".

-   **Correo electrónico de la tienda PrestaShop (PS_SHOP_EMAIL)**
    -   **Qué hace este ajuste:** Este campo normalmente extrae el correo electrónico de contacto de su tienda de la configuración general de PrestaShop. Podría usarse para operaciones internas del módulo o en contenido generado.
    -   **Efecto de cambiar este ajuste:** Asegura que se utilice el correo electrónico correcto si el módulo necesita referenciarlo.
    -   **Valor recomendado:** Dejar como predeterminado (debería rellenarse automáticamente desde la configuración de su PrestaShop).
    -   **Escenario / ejemplo de comerciante:** El correo electrónico de contacto de su tienda es `info@mitiendaimpresionante.com`, y este campo lo muestra correctamente.

-   **Impuesto de PrestaShop (PS_TAX)**
    -   **Qué hace este ajuste:** Este campo normalmente extrae la configuración de impuestos predeterminada de su tienda. Podría usarse para calcular los precios correctamente en el contenido compartido.
    -   **Efecto de cambiar este ajuste:** Asegura que las consideraciones fiscales se manejen correctamente si se muestran los precios.
    -   **Valor recomendado:** Dejar como predeterminado (debería rellenarse automáticamente desde la configuración de su PrestaShop).
    -   **Escenario / ejemplo de comerciante:** Su tienda opera con un IVA del 20%, y este campo lo refleja.

#### **Configuración interna del módulo (normalmente dejar como predeterminado)**

-   **Actualizaciones de MyPresta.eu (mypresta_updates, update_, updatev_)**
    -   **Qué hace este ajuste:** Son configuraciones internas utilizadas por los módulos de MyPresta.eu para buscar actualizaciones y garantizar la compatibilidad.
    -   **Efecto de cambiar este ajuste:** Modificarlos podría interferir con la capacidad del módulo para recibir actualizaciones o funcionar correctamente.
    -   **Valor recomendado:** Dejar como predeterminado.
    -   **Escenario / ejemplo de comerciante:** Generalmente no necesita interactuar con estos.

-   **Inicio de Facebook (cshare_fbinit)**
    -   **Qué hace este ajuste:** Una bandera interna que indica si el SDK de Facebook ha sido inicializado.
    -   **Efecto de cambiar este ajuste:** Modificar esto podría evitar que la funcionalidad de compartir en Facebook se cargue correctamente.
    -   **Valor recomendado:** Dejar como predeterminado.
    -   **Escenario / ejemplo de comerciante:** Esta es una configuración técnica no destinada a la interacción del comerciante.

### 2.2 Pantallas de administración dedicadas y vistas de controlador
Este módulo no introduce ninguna pantalla de administración o controlador personalizado dedicado más allá de su página de configuración principal. Todas las configuraciones se gestionan directamente dentro de la interfaz de configuración estándar del módulo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Configuración del módulo | ID de aplicación de Facebook | Su ID de aplicación único | Esencial para la conexión a la API de Facebook; compartir no funcionará sin él. |
| Configuración del módulo | Mostrar botón de compartir en | Ambos | Controla dónde aparece el botón de compartir (Carrito, Confirmación de pedido o ambos). |
| Configuración del módulo | Estilo del botón de compartir en Facebook | (Varía) | Cambia la apariencia visual del botón de compartir. |
| Configuración del módulo | Habilitar generación de vales | SÍ | Activa o desactiva la creación y visualización de un vale de descuento después de compartir. |
| Configuración del módulo | Regalo de vale | Porcentaje / Cantidad fija | Define el tipo de descuento (por ejemplo, 10% de descuento, 5 € de descuento, Envío gratuito). |
| Configuración del módulo | Valor del vale | (Su valor deseado) | Establece el valor específico para el tipo de regalo de vale elegido. |
| Configuración del módulo | Mostrar precios | SÍ | Incluye los precios individuales de los productos en la publicación compartida de Facebook. |
| Configuración del módulo | Mostrar total | SÍ | Incluye el valor total del carrito en la publicación compartida de Facebook. |
| Configuración del módulo | Mostrar productos | SÍ | Enumera los nombres y cantidades de los productos individuales en la publicación compartida de Facebook. |
| Configuración del módulo | Mostrar URL del producto | SÍ | Añade enlaces directos a las páginas de productos en la publicación compartida de Facebook. |
| Configuración del módulo | Forzar HTTPS | SÍ | Asegura que todos los enlaces compartidos sean seguros (HTTPS). |
| Configuración del módulo | Nombre de la tienda PrestaShop | (Rellenado automáticamente) | Muestra el nombre de su tienda en la publicación de Facebook. |
| Configuración del módulo | Correo electrónico de la tienda PrestaShop | (Rellenado automáticamente) | Correo electrónico de contacto de la tienda. |
| Configuración del módulo | Impuesto de PrestaShop | (Rellenado automáticamente) | Configuración de impuestos predeterminada de la tienda. |
| Configuración del módulo | Actualizaciones de MyPresta.eu | (Interno) | Configuración interna para actualizaciones del módulo. |
| Configuración del módulo | Inicio de Facebook | (Interno) | Bandera interna para la inicialización del SDK de Facebook. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: El botón de compartir en Facebook no aparece en mi página de carrito/confirmación de pedido.**
*   **R:** Primero, verifique la configuración del módulo en su Back Office (**Módulos > Gestor de módulos > Configurar Compartir carrito en Facebook + cupón de vale**). Asegúrese de que "Mostrar botón de compartir en" esté configurado correctamente (por ejemplo, "Página del carrito de compras", "Página de confirmación de pedido" o "Ambos"). Además, verifique que su ID de aplicación de Facebook esté ingresado correctamente. Si aún no aparece, borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).

**P2: Cuando los clientes hacen clic en el botón de compartir, no sucede nada o reciben un error.**
*   **R:** Esto casi siempre apunta a un problema con su ID de aplicación de Facebook o la configuración de la aplicación de Facebook en sí.
    1.  **Vuelva a verificar su ID de aplicación de Facebook:** Asegúrese de que esté ingresado correctamente en la configuración del módulo.
    2.  **Verifique la configuración de la aplicación de Facebook:** Inicie sesión en [developers.facebook.com](https://developers.facebook.com/). Asegúrese de que su aplicación esté "Activa" (no en modo de desarrollo). Verifique la sección "Configuración > Básica" de su aplicación: los campos "Dominios de la aplicación" y "Sitio web" deben listar con precisión el dominio de su tienda (por ejemplo, `sutienda.com` y `https://www.sutienda.com`).
    3.  **Forzar HTTPS:** Asegúrese de que la opción "Forzar HTTPS" en la configuración del módulo esté establecida en "SÍ" si su tienda utiliza HTTPS.

**P3: Los vales no se generan después de una compartición exitosa.**
*   **R:**
    1.  **Verifique "Habilitar generación de vales":** En la configuración del módulo, asegúrese de que este ajuste esté establecido en "SÍ".
    2.  **Regalo y valor del vale:** Asegúrese de haber seleccionado un tipo de "Regalo de vale" (por ejemplo, Porcentaje, Cantidad fija) y de haber ingresado un "Valor del vale" válido.
    3.  **Límites de reglas de carrito de PrestaShop:** PrestaShop tiene límites en el número de reglas de carrito. Aunque es poco probable para este módulo, si tiene un volumen extremadamente alto de comparticiones, asegúrese de que su servidor pueda manejar la creación de nuevas reglas de carrito.
    4.  **Registros de errores:** Verifique los registros de errores de su PrestaShop (generalmente en `var/logs/` o `app/logs/` para PS 1.7+) para cualquier error relacionado durante el proceso de generación de vales.

**P4: El contenido compartido en Facebook no se ve bien (por ejemplo, faltan precios, imagen incorrecta).**
*   **R:**
    1.  **Configuración del módulo:** Revise la "Configuración de contenido compartido" en la configuración del módulo (Mostrar precios, Mostrar total, Mostrar productos, Mostrar URL del producto). Asegúrese de que todos estén configurados en "SÍ" si desea el máximo detalle.
    2.  **Open Graph de Facebook:** Facebook utiliza las etiquetas Open Graph (OG) de las páginas de sus productos para generar vistas previas. Asegúrese de que su tema de PrestaShop y otros módulos estén generando correctamente estas etiquetas OG (especialmente `og:image`, `og:title`, `og:description`). Puede usar el [Depurador de compartición](https://developers.facebook.com/tools/debug/) de Facebook para ver cómo Facebook rastrea sus URL.
    3.  **Caché:** Borre la caché de su PrestaShop y la caché de su navegador. Facebook también almacena en caché el contenido compartido, así que use el Depurador de compartición para "Volver a rastrear" si ha realizado cambios.

**P5: El módulo no se ve bien con mi tema personalizado.**
*   **R:** El módulo utiliza su propio CSS (`css.css`, `ps16.css`). Su tema personalizado podría estar anulando o entrando en conflicto con estos estilos.
    1.  **Inspeccionar elemento:** Utilice las herramientas de desarrollador de su navegador (F12) para inspeccionar el botón de compartir y la visualización del vale. Identifique las clases CSS aplicadas por el módulo y su tema.
    2.  **CSS personalizado:** Puede añadir CSS personalizado al archivo `custom.css` (o equivalente) de su tema para anular los estilos del módulo y hacer que coincida mejor con su tema. Diríjase a las clases específicas del módulo para evitar afectar otras partes de su tienda.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura
El módulo "Compartir carrito en Facebook + cupón de vale" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` y `ModuleFrontController` para las interacciones del front office. Se integra con el SDK de JavaScript de Facebook para la funcionalidad de compartir y utiliza el objeto `CartRule` de PrestaShop para la generación de vales. La configuración se gestiona a través del método `getContent()` en el archivo principal del módulo, almacenando la configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front Office**:
    *   `cartshare/controllers/front/cartshare.php`
        *   **Nombre de la clase y clase padre:** `CartshareCartshareModuleFrontController` extiende `ModuleFrontController`.
        *   **Responsabilidad:** Este controlador es probablemente responsable de manejar la llamada de retorno AJAX de Facebook después de una compartición, o de renderizar la página dedicada de compartición de carrito si el módulo tiene una. Procesaría el evento de compartición y activaría la lógica de generación de vales. También podría ser responsable de renderizar la plantilla `cartsharepage.tpl`.
    *   `cartshare/controllers/front/index.php`
        *   **Nombre de la clase y clase padre:** Este es típicamente un archivo vacío o una simple redirección para evitar la lista de directorios, común en los módulos de PrestaShop. No contiene una clase de controlador específica.
        *   **Responsabilidad:** Medida de seguridad para evitar el acceso directo al directorio `front`.

-   **Controladores de administración del Back Office**:
    *   Ninguno. Toda la administración se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)
Este módulo no parece definir ninguna clase personalizada u `ObjectModel` dentro del directorio `classes/`. Su lógica central para la generación de vales probablemente interactúa directamente con la clase `CartRule` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Alcance:** Front Office.
    *   **Detalles:** Este script es crucial para la interacción del lado del cliente. Probablemente inicializa el SDK de JavaScript de Facebook utilizando el `cshare_appid` de la configuración del módulo. Vincula los oyentes de eventos al botón "Compartir en Facebook", maneja el diálogo de compartir de Facebook y, al compartir con éxito, realiza una llamada AJAX al controlador frontal `cartshare.php` para activar la generación de vales y mostrar el código de vale al usuario. También podría manejar la visualización dinámica del código de vale en la página.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `cartshare/css.css`
    *   **Alcance:** Front Office.
    *   **Detalles:** Contiene el estilo general para los elementos del módulo, como el botón de compartir, el área de visualización del vale y cualquier otro componente de la interfaz de usuario introducido por el módulo.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Alcance:** Front Office.
    *   **Detalles:** Probablemente contiene ajustes de estilo específicos o anulaciones adaptadas para temas de PrestaShop 1.6, asegurando la compatibilidad y la representación adecuada en versiones anteriores.
-   `cartshare/views/css/css/css.css`
    *   **Alcance:** Front Office.
    *   **Detalles:** Esta ruta parece redundante (`css/css/`). Es posible que sea un duplicado o una versión anterior de `cartshare/css.css`, o que contenga un estilo muy específico para ciertos elementos. Los desarrolladores deben verificar su contenido para comprender su propósito.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de gancho (`views/templates/hook/`)**:
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Gancho:** `displayHeader`
        *   **Salida:** Esta plantilla es responsable de incluir el código de inicialización del SDK de JavaScript de Facebook y, potencialmente, los archivos JavaScript (`script.js`) y CSS principales del módulo. Asegura que la API de Facebook esté lista antes de que se renderice el botón de compartir.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Gancho:** `displayShoppingcart`, `displayOrderConfirmation` (dependiendo de la configuración del módulo)
        *   **Salida:** Renderiza el botón "Compartir carrito en Facebook" y el contenedor para mostrar el código de vale después de una compartición exitosa. Este es el componente visual principal con el que interactúan los clientes.

-   **Plantillas del Front Office (`views/templates/front/`)**:
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Propósito:** Esta plantilla es probablemente renderizada por `CartshareCartshareModuleFrontController` y podría ser una página dedicada o una vista parcial para mostrar el contenido del carrito a compartir, o el código de vale.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Propósito:** Esta plantilla genera dinámicamente el contenido que se pasará al diálogo de compartir de Facebook. Construye el título, la descripción, la imagen y las URL basándose en el carrito del cliente y la configuración del módulo (por ejemplo, `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Propósito:** Esta plantilla podría ser una anulación o un bloque adicional diseñado específicamente para ser incluido dentro de la página estándar del carrito de compras de PrestaShop, potencialmente para renderizar el botón de compartir u otro contenido específico del módulo directamente dentro del resumen del carrito.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:
    *   Este módulo no crea tablas SQL personalizadas.
    *   La configuración se almacena en la tabla `ps_configuration`, utilizando claves como `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES`, etc.
    *   Los vales se generan como entradas estándar de `CartRule` de PrestaShop, almacenadas en `ps_cart_rule` y tablas relacionadas.

-   **Tabla de ganchos registrados**:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
|---|---|---|
| `displayHeader` | En la sección `<head>` de cada página. | Inicializa el SDK de Facebook, carga los activos JS/CSS del módulo. |
| `displayShoppingcart` | En la página de resumen del carrito de compras. | Renderiza el botón "Compartir carrito en Facebook" y el área de visualización del vale. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Renderiza el botón "Compartir carrito en Facebook" y el área de visualización del vale. |
| `displayShoppingCart` | (Duplicado de `displayShoppingcart` en la información del módulo, probablemente se refiere al mismo gancho) | Renderiza el botón "Compartir carrito en Facebook" y el área de visualización del vale. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Compartir carrito en Facebook + cupón de vale", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.
