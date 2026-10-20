---
title: "Limitar la cantidad de productos en el carrito para usuarios no registrados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Limitar la cantidad de productos en el carrito para usuarios no registrados' de MyPresta.eu."
sidebar:
  label: "Limitar la cantidad de productos en el carrito para usuarios no registrados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Limit quantity of products in cart for unlogged users en MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Limitar la cantidad de productos en el carrito para usuarios no registrados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única del módulo. La encontrará navegando a **Módulos > Gestor de módulos**, buscando "Limitar la cantidad de productos en el carrito para usuarios no registrados" y haciendo clic en "Configurar".

#### **Cantidad máxima de productos en el carrito para usuarios no registrados**

- **Qué hace este ajuste:** Este es el ajuste principal del módulo. Define la cantidad total máxima absoluta de artículos que un cliente no registrado puede tener en su carrito de compras.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en 0:* El módulo se deshabilitará efectivamente, y los usuarios no registrados podrán añadir una cantidad ilimitada de productos a su carrito, al igual que los usuarios registrados.
  - *Si se establece en un número mayor que 0 (por ejemplo, 5):* Un cliente no registrado podrá añadir artículos a su carrito hasta que la cantidad total de todos los artículos alcance este número. Si intentan añadir otro artículo que exceda este límite, el módulo impedirá la adición y mostrará la ventana emergente de advertencia.
- **Valor recomendado:** Esto depende completamente de su estrategia comercial.
  - *Para tiendas B2C que desean fomentar suavemente el inicio de sesión:* Un valor como `3` o `5` puede ser efectivo.
  - *Para tiendas B2B o tiendas con artículos de alto valor:* Un valor más bajo como `1` o `2` podría ser apropiado para asegurar que solo los compradores serios y registrados puedan reservar stock.
  - *Si no desea ningún límite:* Establezca en `0`.
- **Escenario / ejemplo de comerciante:** Vende camisetas personalizadas. Desea que los navegadores ocasionales vean algunos diseños en su carrito, pero para que se comprometan con un pedido más grande, prefiere que inicien sesión. Lo establece en `3`. Un cliente no registrado añade una camiseta (cantidad 1), luego otra (cantidad 1), luego una tercera (cantidad 1). Su carrito ahora tiene 3 artículos. Si intentan añadir una cuarta camiseta, verán el mensaje emergente, pidiéndoles que inicien sesión.

#### **Mensaje para usuarios no registrados**

- **Qué hace este ajuste:** Esto le permite personalizar el texto del mensaje emergente que aparece cuando un usuario no registrado intenta exceder el límite de cantidad de carrito definido.
- **Efecto de cambiar este ajuste:**
  - *Si lo deja como predeterminado:* Se mostrará el mensaje estándar "Como cliente no registrado no puede añadir más productos al carrito. Por favor, inicie sesión para continuar con el proceso de añadir al carrito."
  - *Si lo personaliza:* Se mostrará su mensaje personalizado en su lugar. Esto le permite adaptar el tono, añadir instrucciones específicas o incluso incluir un enlace (aunque los enlaces directos en las ventanas emergentes pueden ser complicados sin una mayor personalización).
- **Valor recomendado:** El mensaje predeterminado es claro y efectivo. Solo cámbielo si tiene una voz de marca específica o instrucciones adicionales que desea transmitir. Manténgalo conciso.
- **Escenario / ejemplo de comerciante:** Desea un tono ligeramente más suave. Cambia el mensaje a: "Para añadir más artículos a su carrito, inicie sesión o cree una cuenta. ¡Nos encantaría que se uniera a nuestra comunidad!"

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | **Cantidad máxima de productos en el carrito para usuarios no registrados** | `0` (deshabilitado) / `3-5` (recomendado para B2C) | Establece el número total de artículos que un cliente no registrado puede añadir a su carrito. Impide adiciones posteriores y muestra una ventana emergente si se excede. |
| Configuración del módulo | **Mensaje para usuarios no registrados** | "Como cliente no registrado no puede añadir más productos al carrito. Por favor, inicie sesión para continuar con el proceso de añadir al carrito." | Personaliza el texto que se muestra en la ventana emergente cuando un usuario no registrado alcanza el límite del carrito. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He establecido un límite, pero los usuarios no registrados aún pueden añadir productos ilimitados. ¿Qué está mal?**
R:

1.  **Verifique la configuración de "Cantidad máxima":** Asegúrese de que esté establecida en un número mayor que `0`. Si es `0`, el módulo está deshabilitado.
2.  **Borre la caché de su navegador:** Su navegador podría estar mostrándole una versión antigua de la página. Intente borrar la caché y las cookies de su navegador, o pruebe en una ventana de navegación de incógnito/privada.
3.  **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
4.  **Asegúrese de que realmente no ha iniciado sesión:** Verifique que no ha iniciado sesión en una cuenta de cliente en su navegador. La forma más fácil de probar es abrir una nueva ventana de navegación de incógnito/privada.

**P: El mensaje emergente no se muestra o se ve extraño.**
R:

1.  **Verifique la configuración de "Mensaje para usuarios no registrados" del módulo:** Asegúrese de que no esté vacío si espera un mensaje personalizado.
2.  **Compatibilidad del tema:** Si bien el módulo está diseñado para ser compatible, los temas muy personalizados a veces pueden interferir con JavaScript o CSS. Si la ventana emergente no aparece en absoluto, verifique la consola de desarrollador de su navegador en busca de errores de JavaScript (tecla F12, luego pestaña Consola). Si se ve extraño, podría ser un conflicto de CSS. Póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema.

**P: ¿Este módulo afecta a los clientes que han iniciado sesión?**
R: No, este módulo se dirige específicamente a los usuarios *no registrados*. Una vez que un cliente inicia sesión en su cuenta, el límite de cantidad impuesto por este módulo ya no se aplica a ellos.

**P: ¿Puedo establecer diferentes límites para diferentes categorías de productos?**
R: No, este módulo aplica un único límite de cantidad global para todos los productos en el carrito para usuarios no registrados. No admite límites específicos de categoría o producto.

**P: ¿Qué sucede si un usuario no registrado añade 3 artículos, luego inicia sesión y luego intenta añadir más?**
R: Una vez que el usuario inicia sesión, ya no se le considera "no registrado". La restricción del módulo se levanta y puede seguir añadiendo productos a su carrito sin ningún límite de cantidad de este módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Limitar la cantidad de productos en el carrito para usuarios no registrados" (`lqfu`) es un módulo ligero de PrestaShop implementado principalmente a través de una clase de módulo principal (`lqfu/index.php`) y un archivo JavaScript personalizado (`lqfu/views/js/lqfu.js`). Aprovecha el sistema de hooks de PrestaShop para inyectar su JavaScript en el front office y utiliza AJAX para comunicarse con la lógica del lado del servidor para verificar y aplicar el límite de cantidad del carrito para usuarios invitados. El módulo almacena su configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front Office**: Ninguno. La lógica del front office del módulo se maneja directamente a través del archivo principal del módulo `hookDisplayHeader` y las solicitudes AJAX, que son procesadas por el `CartController` o `ProductController` principal de PrestaShop e interceptadas por la lógica del módulo.
- **Controladores de administración de Back Office**: Ninguno. Toda la configuración se maneja dentro del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

- No se definen clases personalizadas que extiendan `ObjectModel` en este módulo. Toda la lógica reside dentro de la clase principal `Lqfu` en `index.php`.

### 4.4 Activos JavaScript (`views/js/`)

- **`lqfu/views/js/lqfu.js`**
  - **Alcance:** Front office.
  - **Propósito:** Este script es responsable de interceptar las acciones de "Añadir al carrito", verificar la cantidad actual del carrito para usuarios no registrados y mostrar el mensaje emergente personalizado si se excede el límite.
  - **Funcionalidad clave:**
    - Vincula oyentes de eventos a los botones (o formularios) de "Añadir al carrito" en toda la tienda (por ejemplo, página de producto, listados de categorías).
    - En un intento de "Añadir al carrito", primero verifica si el usuario ha iniciado sesión.
    - Si el usuario no ha iniciado sesión, recupera la cantidad actual del carrito (ya sea de un elemento oculto o haciendo una llamada AJAX si es necesario).
    - Compara la cantidad actual del carrito + la cantidad que se está añadiendo con el límite máximo configurado.
    - Si se excede el límite, evita la acción predeterminada de "Añadir al carrito", muestra un modal/ventana emergente personalizado con el mensaje configurado y, potencialmente, deshabilita temporalmente el botón "Añadir al carrito".
    - Es probable que el script utilice jQuery para la manipulación del DOM y el manejo de eventos, algo común en el front office de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`lqfu/views/css/lqfu.css`**
  - **Alcance:** Estilo del cliente del front office.
  - **Propósito:** Proporciona un estilo básico para el mensaje emergente que aparece cuando un usuario no registrado excede el límite de cantidad del carrito.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden esperar clases relacionadas con el contenedor emergente, el texto del mensaje y, posiblemente, los botones de cierre. Estos se pueden anular en el `custom.css` o `theme.css` de un tema personalizado para que coincidan con la marca de la tienda.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**: Ninguna explícitamente listada, pero el módulo podría renderizar contenido implícitamente a través de `displayHeader` o hooks similares si necesita inyectar datos ocultos o variables JS iniciales.
- **Plantillas de administración (`views/templates/admin/`)**:
  - **`lqfu/views/templates/admin/json.tpl`**: Esta plantilla se utiliza probablemente para renderizar datos JSON de forma estructurada dentro del Back Office, posiblemente para depuración o respuestas AJAX específicas de la página de configuración del módulo, aunque su uso directo para la configuración principal es menos común. Podría ser un remanente o utilizarse para una función interna específica del módulo.
- **Plantillas de Front Office (`views/templates/front/`)**: Ninguna. La ventana emergente probablemente se genera dinámicamente a través de JavaScript.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración se almacena en la tabla `ps_configuration`:
    - `PS_LQFU_MAX_QUANTITY`: Almacena el valor entero para la cantidad máxima de productos para usuarios no registrados.
    - `PS_LQFU_MESSAGE`: Almacena el valor de cadena para el mensaje personalizado que se muestra en la ventana emergente.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front office. | Inyecta los archivos CSS (`lqfu.css`) y JavaScript (`lqfu.js`) del módulo en el front office. También puede pasar variables de configuración (como la cantidad máxima y el mensaje) al JavaScript. |
| `actionCartSave` | Después de guardar un carrito (por ejemplo, producto añadido/eliminado). | Es probable que el módulo intercepte este hook (o uno similar como `actionObjectCartAddAfter`) para reevaluar la cantidad del carrito y, potencialmente, evitar la adición de artículos si se excede el límite para un usuario no registrado. Aquí es donde se produciría la validación del lado del servidor antes de que se active la ventana emergente de JS. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Limitar la cantidad de productos en el carrito para usuarios no registrados", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
